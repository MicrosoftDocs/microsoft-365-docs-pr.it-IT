---
title: Visualizzare report di sicurezza delle e-mail
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come trovare e usare i report di sicurezza della posta elettronica disponibili nel portale di Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3dcf533c232a89adf0dc1ff3fcc7c2ca4fc5d8f
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022935"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="abbc4-103">Visualizzare i report di sicurezza della posta elettronica nel portale di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abbc4-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="abbc4-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="abbc4-104">**Applies to**</span></span>
- [<span data-ttu-id="abbc4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="abbc4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="abbc4-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="abbc4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="abbc4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abbc4-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="abbc4-108">Nel portale di Microsoft 365 Defender sono disponibili diversi report che consentono di vedere come le funzionalità di sicurezza della posta elettronica, ad esempio la protezione da posta indesiderata, antimalware e crittografia <https://security.microsoft.com> in Microsoft 365, proteggono l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abbc4-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="abbc4-109">Se si dispone delle autorizzazioni [necessarie,](#what-permissions-are-needed-to-view-these-reports)è possibile visualizzare questi report nel  portale di Microsoft 365 Defender andando a Rapporti e-mail & \> **collaborazione** \> **E-mail**& rapporti di collaborazione .</span><span class="sxs-lookup"><span data-stu-id="abbc4-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="abbc4-110">Per passare direttamente alla pagina Rapporti di **collaborazione &** e-mail, aprire <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="abbc4-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Pagina dei & di collaborazione tramite posta elettronica nel portale di Microsoft 365 Defender](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="abbc4-112">Alcuni dei report nella pagina Rapporti di **collaborazione &** e-mail richiedono Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="abbc4-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="abbc4-113">Per informazioni su questi report, vedere [View Defender for Office 365 reports in the Microsoft 365 Defender portal.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="abbc4-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="abbc4-114">I report correlati al flusso di posta sono ora disponibili nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="abbc4-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="abbc4-115">Per ulteriori informazioni su questi report, vedere [Mail flow reports in the new Exchange admin center.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="abbc4-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="abbc4-116">Report utenti compromessi</span><span class="sxs-lookup"><span data-stu-id="abbc4-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="abbc4-117">Questo report è disponibile nelle organizzazioni di Microsoft 365 con cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="abbc4-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="abbc4-118">Non è disponibile nelle organizzazioni autonome di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="abbc4-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="abbc4-119">Il **report Utenti compromessi** mostra il numero di  account  utente contrassegnati come sospetti o con restrizioni negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="abbc4-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="abbc4-120">Gli account in uno di questi stati sono problematici o addirittura compromessi.</span><span class="sxs-lookup"><span data-stu-id="abbc4-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="abbc4-121">Con un uso frequente, è possibile utilizzare il report per individuare picchi e persino tendenze in account sospetti o con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="abbc4-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="abbc4-122">Per ulteriori informazioni sugli utenti compromessi, vedere [Risposta a un account di posta elettronica compromesso.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="abbc4-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Utenti compromessi nella pagina Report & e-mail](../../media/compromised-users-report-widget.png)

<span data-ttu-id="abbc4-124">La visualizzazione aggregata mostra i dati degli ultimi 90 giorni e la visualizzazione dettagli mostra i dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="abbc4-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="abbc4-125">Per visualizzare il report nel portale di Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="abbc4-126">Nella pagina **Rapporti di &** e-mail individuare Utenti **compromessi** e quindi fare clic **su Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="abbc4-127">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="abbc4-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="abbc4-128">Nella pagina **Utenti compromessi** è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="abbc4-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="abbc4-129">**Date (UTC)**: **Data di inizio** e Data di **fine**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="abbc4-130">**Attività**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-130">**Activity**:</span></span>
  - <span data-ttu-id="abbc4-131">**Sospetto:** l'account utente ha inviato messaggi di posta elettronica sospetti ed è a rischio di essere limitato a inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="abbc4-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="abbc4-132">**Con restrizioni**: all'account utente è stato limitato l'invio di posta elettronica a causa di modelli altamente sospetti.</span><span class="sxs-lookup"><span data-stu-id="abbc4-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="abbc4-133">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![Visualizzazione report nel report Utenti compromessi](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="abbc4-135">Nella tabella dei dettagli sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="abbc4-136">**Ora creazione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-136">**Creation time**</span></span>
- <span data-ttu-id="abbc4-137">**ID utente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-137">**User ID**</span></span>
- <span data-ttu-id="abbc4-138">**Azione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="abbc4-139">Report delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="abbc4-139">Exchange transport rule report</span></span>

<span data-ttu-id="abbc4-140">Il **rapporto sulle regole di trasporto** di Exchange mostra l'effetto delle regole del flusso di posta (note anche come regole di trasporto) sui messaggi in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abbc4-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="abbc4-141">Per visualizzare il report nel portale di Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="abbc4-142">Nella pagina **Rapporti di & e-mail** individuare la regola di trasporto **di Exchange** e quindi fare clic su **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="abbc4-143">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="abbc4-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Widget regola di trasporto di Exchange nella pagina Rapporti di collaborazione & e-mail](../../media/transport-rule-report-widget.png)

<span data-ttu-id="abbc4-145">Nella pagina **Rapporto regole di trasporto di Exchange,** i grafici e i dati disponibili sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="abbc4-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="abbc4-146">Suddivisione del grafico per direzione</span><span class="sxs-lookup"><span data-stu-id="abbc4-146">Chart breakdown by Direction</span></span>

![Visualizzazione della direzione per le regole di trasporto di Exchange nel report delle regole di trasporto di Exchange](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="abbc4-148">Se si seleziona **Suddivisione grafico per direzione**, sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="abbc4-149">**Visualizzare i dati in base alle regole di trasporto di Exchange**: numero di messaggi in  **ingresso** e in uscita interessati dalle regole del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="abbc4-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="abbc4-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span><span class="sxs-lookup"><span data-stu-id="abbc4-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="abbc4-151">Nella tabella dei dettagli sotto il grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="abbc4-152">**Data**</span><span class="sxs-lookup"><span data-stu-id="abbc4-152">**Date**</span></span>
- <span data-ttu-id="abbc4-153">**Criterio DLP** (**Visualizzare i dati solo in base alle regole di trasporto di Exchange DLP)**</span><span class="sxs-lookup"><span data-stu-id="abbc4-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="abbc4-154">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-154">**Transport rule**</span></span>
- <span data-ttu-id="abbc4-155">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-155">**Subject**</span></span>
- <span data-ttu-id="abbc4-156">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-156">**Sender address**</span></span>
- <span data-ttu-id="abbc4-157">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="abbc4-157">**Recipient address**</span></span>
- <span data-ttu-id="abbc4-158">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="abbc4-158">**Severity**</span></span>
- <span data-ttu-id="abbc4-159">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-159">**Direction**</span></span>

<span data-ttu-id="abbc4-160">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="abbc4-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="abbc4-161">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-162">**Direzione**: **In uscita** e **in ingresso**</span><span class="sxs-lookup"><span data-stu-id="abbc4-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="abbc4-163">**Gravità**: **Gravità elevata,** **Gravità media** e **Gravità bassa**</span><span class="sxs-lookup"><span data-stu-id="abbc4-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="abbc4-164">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="abbc4-165">Suddivisione del grafico per gravità</span><span class="sxs-lookup"><span data-stu-id="abbc4-165">Chart breakdown by Severity</span></span>

![Visualizzazione gravità per le regole di trasporto di Exchange nel report delle regole di trasporto di Exchange](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="abbc4-167">Se si seleziona **Scomposizione grafico per gravità**, sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="abbc4-168">**Visualizzare i dati in base alle regole di** trasporto di Exchange : numero di messaggi di gravità elevata, gravità media e **gravità** bassa.  </span><span class="sxs-lookup"><span data-stu-id="abbc4-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="abbc4-169">Il livello di gravità viene impostato come azione nella regola **(** Controlla questa regola con livello di gravità o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="abbc4-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="abbc4-170">Per ulteriori informazioni, vedere [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="abbc4-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="abbc4-171">**Visualizzare i dati in base alle** regole di trasporto di  Exchange DLP : numero di messaggi di gravità **elevata,** di gravità **media** e di gravità bassa interessati dalle regole del flusso di posta DLP.</span><span class="sxs-lookup"><span data-stu-id="abbc4-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="abbc4-172">Nella tabella dei dettagli sotto il grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="abbc4-173">**Data**</span><span class="sxs-lookup"><span data-stu-id="abbc4-173">**Date**</span></span>
- <span data-ttu-id="abbc4-174">**Criterio DLP** (**Visualizzare i dati solo in base alle regole di trasporto di Exchange DLP)**</span><span class="sxs-lookup"><span data-stu-id="abbc4-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="abbc4-175">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-175">**Transport rule**</span></span>
- <span data-ttu-id="abbc4-176">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-176">**Subject**</span></span>
- <span data-ttu-id="abbc4-177">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-177">**Sender address**</span></span>
- <span data-ttu-id="abbc4-178">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="abbc4-178">**Recipient address**</span></span>
- <span data-ttu-id="abbc4-179">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="abbc4-179">**Severity**</span></span>
- <span data-ttu-id="abbc4-180">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-180">**Direction**</span></span>

<span data-ttu-id="abbc4-181">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="abbc4-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="abbc4-182">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-183">**Direzione**: **In uscita** e **in ingresso**</span><span class="sxs-lookup"><span data-stu-id="abbc4-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="abbc4-184">**Gravità**: **Gravità elevata,** **Gravità media** e **Gravità bassa**</span><span class="sxs-lookup"><span data-stu-id="abbc4-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="abbc4-185">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="abbc4-186">Rapporto di inoltro</span><span class="sxs-lookup"><span data-stu-id="abbc4-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="abbc4-187">Il **report di inoltro** è ora disponibile nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="abbc4-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="abbc4-188">Per ulteriori informazioni, vedere [Report messaggi inoltrati automaticamente nel nuovo interfaccia di amministrazione di Exchange.](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)</span><span class="sxs-lookup"><span data-stu-id="abbc4-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="abbc4-189">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="abbc4-189">Mailflow status report</span></span>

<span data-ttu-id="abbc4-190">Il **rapporto** sullo stato del flusso di posta è un report intelligente che mostra informazioni sulla posta elettronica in arrivo e in uscita, sui rilevamenti di posta indesiderata, sul malware, sulla posta elettronica identificata come "buona" e sulle informazioni sulla posta elettronica consentita o bloccata sul perimetro.</span><span class="sxs-lookup"><span data-stu-id="abbc4-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="abbc4-191">Questo è l'unico report che contiene informazioni sulla protezione perimetrale e mostra la quantità di posta elettronica bloccata prima di essere consentita al servizio per la valutazione da Parte di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="abbc4-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="abbc4-192">È importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="abbc4-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="abbc4-193">Per visualizzare il report nel portale di Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="abbc4-194">Nella pagina **E-mail & rapporti di collaborazione,** trovare Riepilogo stato **flusso** di posta e quindi fare clic **su Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="abbc4-195">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="abbc4-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Widget Riepilogo stato flusso di posta nella pagina Rapporti di collaborazione & posta elettronica](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="abbc4-197">Visualizzazione tipo per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="abbc4-197">Type view for the Mailflow status report</span></span>

<span data-ttu-id="abbc4-198">Quando si apre il report, la **scheda Tipo** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="abbc4-198">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="abbc4-199">Per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dei dettagli configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-199">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="abbc4-200">**Data (UTC)** Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="abbc4-200">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="abbc4-201">**Direzione della posta**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-201">**Mail direction**:</span></span>
  - <span data-ttu-id="abbc4-202">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="abbc4-202">**Inbound**</span></span>
  - <span data-ttu-id="abbc4-203">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="abbc4-203">**Outbound**</span></span>
  - <span data-ttu-id="abbc4-204">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="abbc4-204">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="abbc4-205">mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da **In ingresso** e **In uscita)**</span><span class="sxs-lookup"><span data-stu-id="abbc4-205">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="abbc4-206">**Digitare**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-206">**Type**:</span></span>
  - <span data-ttu-id="abbc4-207">**Posta buona**</span><span class="sxs-lookup"><span data-stu-id="abbc4-207">**Good mail**</span></span>
  - <span data-ttu-id="abbc4-208">**Malware**</span><span class="sxs-lookup"><span data-stu-id="abbc4-208">**Malware**</span></span>
  - <span data-ttu-id="abbc4-209">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="abbc4-209">**Spam**</span></span>
  - <span data-ttu-id="abbc4-210">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="abbc4-210">**Edge protection**</span></span>
  - <span data-ttu-id="abbc4-211">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="abbc4-211">**Rule messages**</span></span>
  - <span data-ttu-id="abbc4-212">**Posta di phishing**</span><span class="sxs-lookup"><span data-stu-id="abbc4-212">**Phishing email**</span></span>
- <span data-ttu-id="abbc4-213">**Domain**: **All**</span><span class="sxs-lookup"><span data-stu-id="abbc4-213">**Domain**: **All**</span></span>

<span data-ttu-id="abbc4-214">Il grafico è organizzato in base ai **valori Type.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-214">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="abbc4-215">È possibile modificare questi filtri facendo clic **su Filtro** o su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="abbc4-215">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="abbc4-216">Nella tabella dei dettagli sotto il grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-216">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="abbc4-217">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-217">**Direction**</span></span>
- <span data-ttu-id="abbc4-218">**Type**</span><span class="sxs-lookup"><span data-stu-id="abbc4-218">**Type**</span></span>
- <span data-ttu-id="abbc4-219">**24 ore**</span><span class="sxs-lookup"><span data-stu-id="abbc4-219">**24 hours**</span></span>
- <span data-ttu-id="abbc4-220">**3 giorni**</span><span class="sxs-lookup"><span data-stu-id="abbc4-220">**3 days**</span></span>
- <span data-ttu-id="abbc4-221">**7 giorni**</span><span class="sxs-lookup"><span data-stu-id="abbc4-221">**7 days**</span></span>
- <span data-ttu-id="abbc4-222">**15 giorni**</span><span class="sxs-lookup"><span data-stu-id="abbc4-222">**15 days**</span></span>
- <span data-ttu-id="abbc4-223">**30 giorni**</span><span class="sxs-lookup"><span data-stu-id="abbc4-223">**30 days**</span></span>

<span data-ttu-id="abbc4-224">Se si fa **clic su Scegli una categoria per ulteriori dettagli,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-224">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="abbc4-225">**Posta elettronica di phishing**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="abbc4-225">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="abbc4-226">**Malware nella posta elettronica**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="abbc4-226">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="abbc4-227">**Rilevamenti di posta indesiderata:** questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="abbc4-227">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="abbc4-228">**Posta indesiderata bloccata** perimetrali : questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="abbc4-228">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="abbc4-229">Esportare dalla visualizzazione Tipo</span><span class="sxs-lookup"><span data-stu-id="abbc4-229">Export from Type view</span></span>

<span data-ttu-id="abbc4-230">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="abbc4-230">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="abbc4-231">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="abbc4-231">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="abbc4-232">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="abbc4-232">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="abbc4-233">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="abbc4-233">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione tipo nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="abbc4-235">Visualizzazione della direzione per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="abbc4-235">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="abbc4-236">Se si fa clic **sulla scheda Direzione,** vengono utilizzati gli stessi filtri predefiniti della **visualizzazione** Tipo.</span><span class="sxs-lookup"><span data-stu-id="abbc4-236">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="abbc4-237">Il grafico è organizzato in base **ai valori di** Direzione.</span><span class="sxs-lookup"><span data-stu-id="abbc4-237">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="abbc4-238">È possibile modificare questi filtri facendo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-238">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="abbc4-239">Vengono utilizzati gli stessi filtri **della** visualizzazione Tipo.</span><span class="sxs-lookup"><span data-stu-id="abbc4-239">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="abbc4-240">La tabella dei dettagli contiene le stesse informazioni della **visualizzazione Tipo.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-240">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="abbc4-241">**L'opzione Scegliere una categoria per ulteriori dettagli** le selezioni e il comportamento disponibili sono gli stessi della visualizzazione **Tipo.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-241">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="abbc4-242">Esportare dalla visualizzazione Direzione</span><span class="sxs-lookup"><span data-stu-id="abbc4-242">Export from Direction view</span></span>

<span data-ttu-id="abbc4-243">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="abbc4-243">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="abbc4-244">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="abbc4-244">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="abbc4-245">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="abbc4-245">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="abbc4-246">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="abbc4-246">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione direzione nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="abbc4-248">Visualizzazione imbuto per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="abbc4-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="abbc4-249">La **visualizzazione Imbuto** mostra come le funzionalità di protezione dalle minacce di posta elettronica di Microsoft filtrano la posta elettronica in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abbc4-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="abbc4-250">Fornisce informazioni dettagliate sul conteggio totale della posta elettronica e sul modo in cui le funzionalità di protezione dalle minacce configurate, tra cui protezione perimetrale, antimalware, anti-phishing, protezione da posta indesiderata e anti-spoofing influiscono su questo conteggio.</span><span class="sxs-lookup"><span data-stu-id="abbc4-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="abbc4-251">Se si fa clic sulla scheda **Imbuto,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dei dettagli configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-251">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="abbc4-252">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="abbc4-252">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="abbc4-253">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-253">**Direction**:</span></span>
  - <span data-ttu-id="abbc4-254">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="abbc4-254">**Inbound**</span></span>
  - <span data-ttu-id="abbc4-255">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="abbc4-255">**Outbound**</span></span>
  - <span data-ttu-id="abbc4-256">**Intra-org:** questo conteggio è per i messaggi inviati all'interno di un tenant; Ad esempio, il mittente abc@domain.com inviato al destinatario xyz@domain.com (conteggiato separatamente da Inbound e Outbound).</span><span class="sxs-lookup"><span data-stu-id="abbc4-256">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="abbc4-257">La visualizzazione aggregata e la tabella dei dettagli consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="abbc4-257">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="abbc4-258">È possibile modificare questi filtri facendo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-258">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="abbc4-259">Vengono utilizzati gli stessi filtri **della** visualizzazione Tipo.</span><span class="sxs-lookup"><span data-stu-id="abbc4-259">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="abbc4-260">Questo grafico mostra il numero di messaggi di posta elettronica organizzati per:</span><span class="sxs-lookup"><span data-stu-id="abbc4-260">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="abbc4-261">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="abbc4-261">**Total email**</span></span>
- <span data-ttu-id="abbc4-262">**Posta elettronica dopo la protezione edge**</span><span class="sxs-lookup"><span data-stu-id="abbc4-262">**Email after edge protection**</span></span>
- <span data-ttu-id="abbc4-263">**Regola di posta elettronica dopo il trasporto** (regola del flusso di posta)</span><span class="sxs-lookup"><span data-stu-id="abbc4-263">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="abbc4-264">**Posta elettronica dopo antimalware, reputazione file, blocco del tipo di file**</span><span class="sxs-lookup"><span data-stu-id="abbc4-264">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="abbc4-265">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="abbc4-265">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="abbc4-266">**Posta elettronica dopo la posta indesiderata, filtro posta in blocco**</span><span class="sxs-lookup"><span data-stu-id="abbc4-266">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="abbc4-267">**Posta elettronica dopo la rappresentazione di utenti e domini**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abbc4-267">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="abbc4-268">**Posta elettronica dopo la detonazione di file e URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abbc4-268">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="abbc4-269">**Email detected as benign after post-delivery protection (URL click time protection)**</span><span class="sxs-lookup"><span data-stu-id="abbc4-269">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="abbc4-270"><sup>\*</sup>Defender solo per Office 365</span><span class="sxs-lookup"><span data-stu-id="abbc4-270"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="abbc4-271">Per visualizzare il messaggio di posta elettronica filtrato da EOP o Defender per Office 365 separatamente, fare clic sul valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="abbc4-271">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="abbc4-272">La tabella dei dettagli contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="abbc4-272">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="abbc4-273">**Data**</span><span class="sxs-lookup"><span data-stu-id="abbc4-273">**Date**</span></span>
- <span data-ttu-id="abbc4-274">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="abbc4-274">**Total email**</span></span>
- <span data-ttu-id="abbc4-275">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="abbc4-275">**Edge protection**</span></span>
- <span data-ttu-id="abbc4-276">**Antimalware, reputazione file, blocco del tipo di file**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-276">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="abbc4-277">**Reputazione file:** messaggi filtrati a causa dell'identificazione di un file allegato da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="abbc4-277">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="abbc4-278">**Blocco del tipo di** file : Messaggi filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="abbc4-278">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="abbc4-279">**Anti-phish, reputazione URL, rappresentazione del marchio, anti-spoofing**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-279">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="abbc4-280">**Reputazione URL**: Messaggi filtrati a causa dell'identificazione dell'URL da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="abbc4-280">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="abbc4-281">**Rappresentazione del marchio**: messaggi filtrati a causa del messaggio proveniente da mittenti noti che rappresentano il marchio.</span><span class="sxs-lookup"><span data-stu-id="abbc4-281">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="abbc4-282">**Anti-spoof**: messaggi filtrati a causa del tentativo di spoofing di un dominio a cui appartiene il destinatario o di un dominio di cui il mittente non è proprietario.</span><span class="sxs-lookup"><span data-stu-id="abbc4-282">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="abbc4-283">**Protezione da posta indesiderata, filtro posta in blocco**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-283">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="abbc4-284">**Filtro posta in blocco**: Messaggi filtrati in base alla soglia del livello di reclamo in blocco (BCL) in un criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="abbc4-284">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="abbc4-285">**Rappresentazione utente e dominio (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-285">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="abbc4-286">**Rappresentazione utente**: messaggi filtrati a causa di un tentativo di rappresentazione di un utente (mittente del messaggio) definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="abbc4-286">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="abbc4-287">**Rappresentazione di dominio**: messaggi filtrati a causa di un tentativo di rappresentare un dominio definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="abbc4-287">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="abbc4-288">**Detonazione di file e URL (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-288">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="abbc4-289">**Detonazione file:** messaggi filtrati da un criterio Safe allegati.</span><span class="sxs-lookup"><span data-stu-id="abbc4-289">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="abbc4-290">**Detonazione URL:** messaggio filtrato in base a un Safe dei collegamenti.</span><span class="sxs-lookup"><span data-stu-id="abbc4-290">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="abbc4-291">**Protezione post-recapito e ZAP (ATP) o ZAP (EOP):** eliminazione automatica a zero ore (ZAP) per malware, posta indesiderata e phishing.</span><span class="sxs-lookup"><span data-stu-id="abbc4-291">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="abbc4-292">Se si seleziona una riga nella tabella dei dettagli, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="abbc4-292">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="abbc4-293">Esportare dalla visualizzazione Imbuto</span><span class="sxs-lookup"><span data-stu-id="abbc4-293">Export from Funnel view</span></span>

<span data-ttu-id="abbc4-294">Dopo aver fatto **clic su** Esporta **in Opzioni,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-294">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="abbc4-295">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="abbc4-295">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="abbc4-296">**Dettagli (con dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="abbc4-296">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="abbc4-297">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-297">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="abbc4-298">I dati per i filtri correnti verranno esportati in un .csv file.</span><span class="sxs-lookup"><span data-stu-id="abbc4-298">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="abbc4-299">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="abbc4-299">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="abbc4-300">Se i dati contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="abbc4-300">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione Imbuto nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="abbc4-302">Visualizzazione tecnica per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="abbc4-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="abbc4-303">La **visualizzazione Tech** è simile alla visualizzazione **Imbuto,** fornendo dettagli più dettagliati per le funzionalità di protezione dalle minacce configurate.</span><span class="sxs-lookup"><span data-stu-id="abbc4-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="abbc4-304">Dal grafico è possibile vedere come i messaggi vengono categorizzati nelle diverse fasi della protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="abbc4-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="abbc4-305">Se si fa clic **sulla scheda Visualizzazione tecnica,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dei dettagli configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="abbc4-306">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="abbc4-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="abbc4-307">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-307">**Direction**:</span></span>
  - <span data-ttu-id="abbc4-308">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="abbc4-308">**Inbound**</span></span>
  - <span data-ttu-id="abbc4-309">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="abbc4-309">**Outbound**</span></span>
  - <span data-ttu-id="abbc4-310">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="abbc4-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="abbc4-311">mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da in ingresso e in uscita)</span><span class="sxs-lookup"><span data-stu-id="abbc4-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="abbc4-312">La visualizzazione aggregata e la tabella dei dettagli consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="abbc4-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="abbc4-313">È possibile modificare questi filtri facendo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="abbc4-314">Vengono utilizzati gli stessi filtri **della** visualizzazione Tipo.</span><span class="sxs-lookup"><span data-stu-id="abbc4-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="abbc4-315">Questo grafico mostra i messaggi organizzati nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="abbc4-316">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="abbc4-316">**Total email**</span></span>
- <span data-ttu-id="abbc4-317">**Edge allow** e **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="abbc4-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="abbc4-318">**Regola di trasporto consentita** **e regola di trasporto filtrata** (regole del flusso di posta)</span><span class="sxs-lookup"><span data-stu-id="abbc4-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="abbc4-319">**Non malware,** **Safe allegati e** rilevamento motore <sup>\*</sup> **antimalware**</span><span class="sxs-lookup"><span data-stu-id="abbc4-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="abbc4-320">**Not phish,** **DMARC failure,** **Impersonation detection,** <sup>\*</sup> Spoof **detection** e **Phish detection**</span><span class="sxs-lookup"><span data-stu-id="abbc4-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="abbc4-321">**Nessun rilevamento con detonazione URL e** **rilevamento detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abbc4-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="abbc4-322">**Non posta indesiderata** e  **posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="abbc4-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="abbc4-323">**Posta elettronica non dannosa,** **rilevamento Safe** <sup>\*</sup> collegamenti e **ZAP**</span><span class="sxs-lookup"><span data-stu-id="abbc4-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="abbc4-324"><sup>\*</sup>Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="abbc4-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="abbc4-325">Quando si passa il mouse su una categoria nel grafico, è possibile visualizzare il numero di messaggi in tale categoria.</span><span class="sxs-lookup"><span data-stu-id="abbc4-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="abbc4-326">La tabella dei dettagli contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="abbc4-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="abbc4-327">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="abbc4-327">**Date (UTC)**</span></span>
- <span data-ttu-id="abbc4-328">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="abbc4-328">**Total email**</span></span>
- <span data-ttu-id="abbc4-329">**Edge filtrato**</span><span class="sxs-lookup"><span data-stu-id="abbc4-329">**Edge filtered**</span></span>
- <span data-ttu-id="abbc4-330">**Messaggi delle regole**: Messaggi filtrati a causa delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="abbc4-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="abbc4-331">**Motore antimalware**, **Safe allegati** <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="abbc4-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="abbc4-332">**DMARC, impersonation,** <sup>\*</sup> **spoof,** **phish filtered**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="abbc4-333">**DMARC**: Messaggi filtrati a causa dell'errore del messaggio nel controllo di autenticazione DMARC.</span><span class="sxs-lookup"><span data-stu-id="abbc4-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="abbc4-334">**Rilevamento detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abbc4-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="abbc4-335">**Protezione da posta indesiderata filtrata**</span><span class="sxs-lookup"><span data-stu-id="abbc4-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="abbc4-336">**ZAP rimosso**</span><span class="sxs-lookup"><span data-stu-id="abbc4-336">**ZAP removed**</span></span>
- <span data-ttu-id="abbc4-337">**Rilevamento da Safe collegamenti**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abbc4-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="abbc4-338"><sup>\*</sup>Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="abbc4-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="abbc4-339">Se si seleziona una riga nella tabella dei dettagli, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="abbc4-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="abbc4-340">Esportare da tech view</span><span class="sxs-lookup"><span data-stu-id="abbc4-340">Export from Tech view</span></span>

<span data-ttu-id="abbc4-341">Facendo clic **su Esporta,** in **Opzioni** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="abbc4-342">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="abbc4-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="abbc4-343">**Dettagli (con dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="abbc4-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="abbc4-344">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="abbc4-345">I dati per i filtri correnti verranno esportati in un .csv file.</span><span class="sxs-lookup"><span data-stu-id="abbc4-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="abbc4-346">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="abbc4-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="abbc4-347">Se i dati contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="abbc4-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione tecnica nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="abbc4-349">Report rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="abbc4-349">Malware detections report</span></span>

<span data-ttu-id="abbc4-350">Il **report Rilevamenti malware** mostra informazioni sui rilevamenti di malware nei messaggi di posta elettronica in arrivo e in uscita (malware rilevato da Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="abbc4-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="abbc4-351">Per ulteriori informazioni sulla protezione da malware in EOP, vedere [Protezione antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="abbc4-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="abbc4-352">Il filtro di visualizzazione aggregata consente 90 giorni, mentre il filtro della tabella dei dettagli consente solo 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="abbc4-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="abbc4-353">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="abbc4-354">Nella pagina **Rapporti di collaborazione &** posta elettronica individuare Malware rilevato **nella** posta elettronica e quindi fare clic su **Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="abbc4-355">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="abbc4-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Rilevamenti di malware nel widget di posta elettronica nella pagina & report di collaborazione](../../media/malware-detections-widget.png)

<span data-ttu-id="abbc4-357">Nella pagina **report Rilevamenti malware** è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="abbc4-358">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-359">**Direzione**: **In ingresso** e **In uscita**</span><span class="sxs-lookup"><span data-stu-id="abbc4-359">**Direction**: **Inbound** and **Outbound**</span></span>

![Visualizzazione report nel report Rilevamento malware nei messaggi di posta elettronica](../../media/malware-detections-report-view.png)

<span data-ttu-id="abbc4-361">Nella tabella dei dettagli sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="abbc4-362">**Data**</span><span class="sxs-lookup"><span data-stu-id="abbc4-362">**Date**</span></span>
- <span data-ttu-id="abbc4-363">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-363">**Sender address**</span></span>
- <span data-ttu-id="abbc4-364">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="abbc4-364">**Recipient address**</span></span>
- <span data-ttu-id="abbc4-365">**ID messaggio**: Disponibile nel **campo di intestazione Message-ID** nell'intestazione del messaggio e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="abbc4-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="abbc4-366">Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="abbc4-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="abbc4-367">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-367">**Subject**</span></span>
- <span data-ttu-id="abbc4-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="abbc4-368">**Filename**</span></span>
- <span data-ttu-id="abbc4-369">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="abbc4-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="abbc4-370">Rapporto latenza della posta</span><span class="sxs-lookup"><span data-stu-id="abbc4-370">Mail latency report</span></span>

<span data-ttu-id="abbc4-371">Il **report Latenza della posta** in Defender per Office 365 contiene informazioni sulla latenza di recapito e detonazione della posta riscontrata all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abbc4-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="abbc4-372">Per ulteriori informazioni, vedere [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="abbc4-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="abbc4-373">Report sui rilevamenti della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="abbc4-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="abbc4-374">Il **rapporto Rilevamenti posta indesiderata** andrà infine via.</span><span class="sxs-lookup"><span data-stu-id="abbc4-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="abbc4-375">Le stesse informazioni sono disponibili nella relazione [sullo stato di Threat Protection.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="abbc4-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="abbc4-376">Report rilevamenti di spoofing</span><span class="sxs-lookup"><span data-stu-id="abbc4-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="abbc4-377">Il report dei rilevamenti di spoofing migliorato, come descritto in questo articolo, è in Anteprima, è soggetto a modifiche e non è disponibile in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="abbc4-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="abbc4-378">La versione precedente del report mostra solo **Posta buona** e Posta indesiderata rilevata come **posta indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="abbc4-379">Il **report Rilevamenti di** spoofing mostra informazioni sui messaggi bloccati o consentiti a causa dello spoofing.</span><span class="sxs-lookup"><span data-stu-id="abbc4-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="abbc4-380">Per ulteriori informazioni sullo spoofing, vedere [Protezione anti-spoofing in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="abbc4-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="abbc4-381">La visualizzazione aggregata del report consente 45 giorni di filtro, mentre la visualizzazione dettagli consente solo <sup>\*</sup> dieci giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="abbc4-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="abbc4-382"><sup>\*</sup> Infine, sarà possibile utilizzare fino a 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="abbc4-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="abbc4-383">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="abbc4-384">Nella pagina **Rapporti di collaborazione &** posta elettronica individuare **Rilevamenti spoofing** e quindi fare clic **su Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="abbc4-385">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="abbc4-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget Rilevamenti di spoofing nella pagina Report & di collaborazione tramite posta elettronica](../../media/spoof-detections-widget.png)

<span data-ttu-id="abbc4-387">Il grafico mostra le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-387">The chart shows the following information:</span></span>

- <span data-ttu-id="abbc4-388">**Pass**</span><span class="sxs-lookup"><span data-stu-id="abbc4-388">**Pass**</span></span>
- <span data-ttu-id="abbc4-389">**Fail**</span><span class="sxs-lookup"><span data-stu-id="abbc4-389">**Fail**</span></span>
- <span data-ttu-id="abbc4-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="abbc4-390">**SoftPass**</span></span>
- <span data-ttu-id="abbc4-391">**Nessuna**</span><span class="sxs-lookup"><span data-stu-id="abbc4-391">**None**</span></span>
- <span data-ttu-id="abbc4-392">**Altro**</span><span class="sxs-lookup"><span data-stu-id="abbc4-392">**Other**</span></span>

<span data-ttu-id="abbc4-393">Quando si passa il mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti messaggi falsificati sono stati rilevati e perché.</span><span class="sxs-lookup"><span data-stu-id="abbc4-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="abbc4-394">Nella pagina **Spoofing mail report** è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="abbc4-395">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-396">**Risultato**:</span><span class="sxs-lookup"><span data-stu-id="abbc4-396">**Result**:</span></span>
  - <span data-ttu-id="abbc4-397">**Pass**</span><span class="sxs-lookup"><span data-stu-id="abbc4-397">**Pass**</span></span>
  - <span data-ttu-id="abbc4-398">**Fail**</span><span class="sxs-lookup"><span data-stu-id="abbc4-398">**Fail**</span></span>
  - <span data-ttu-id="abbc4-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="abbc4-399">**SoftPass**</span></span>
  - <span data-ttu-id="abbc4-400">**Nessuna**</span><span class="sxs-lookup"><span data-stu-id="abbc4-400">**None**</span></span>
  - <span data-ttu-id="abbc4-401">**Altro**</span><span class="sxs-lookup"><span data-stu-id="abbc4-401">**Other**</span></span>
- <span data-ttu-id="abbc4-402">**Tipo spoof**: **interno** ed **esterno**</span><span class="sxs-lookup"><span data-stu-id="abbc4-402">**Spoof type**: **Internal** and **External**</span></span>

![Pagina di report di posta contraffatta nel portale Microsoft 365 Defender posta](../../media/spoof-detections-report-page.png)

<span data-ttu-id="abbc4-404">Nella tabella dei dettagli sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="abbc4-405">**Data**</span><span class="sxs-lookup"><span data-stu-id="abbc4-405">**Date**</span></span>
- <span data-ttu-id="abbc4-406">**Utente contraffatto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-406">**Spoofed user**</span></span>
- <span data-ttu-id="abbc4-407">**Infrastruttura di invio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="abbc4-408">**Tipo spoofing**</span><span class="sxs-lookup"><span data-stu-id="abbc4-408">**Spoof type**</span></span>
- <span data-ttu-id="abbc4-409">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="abbc4-409">**Result**</span></span>
- <span data-ttu-id="abbc4-410">**Codice risultato**</span><span class="sxs-lookup"><span data-stu-id="abbc4-410">**Result code**</span></span>
- <span data-ttu-id="abbc4-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="abbc4-411">**SPF**</span></span>
- <span data-ttu-id="abbc4-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="abbc4-412">**DKIM**</span></span>
- <span data-ttu-id="abbc4-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="abbc4-413">**DMARC**</span></span>
- <span data-ttu-id="abbc4-414">**Conteggio messaggi**</span><span class="sxs-lookup"><span data-stu-id="abbc4-414">**Message count**</span></span>

<span data-ttu-id="abbc4-415">Per ulteriori informazioni sui codici dei risultati dell'autenticazione composita, vedere Intestazioni dei messaggi di posta indesiderata [in Microsoft 365](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="abbc4-416">Report Invii</span><span class="sxs-lookup"><span data-stu-id="abbc4-416">Submissions report</span></span>

<span data-ttu-id="abbc4-417">Il **report Invii** mostra informazioni sugli elementi che gli amministratori hanno segnalato a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="abbc4-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="abbc4-418">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="abbc4-419">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="abbc4-420">Nella pagina **E-mail & rapporti di collaborazione,** trovare **Invii** e quindi fare clic **su Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="abbc4-421">Per passare direttamente al report, aprire <https://security.microsoft.com/adminSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="abbc4-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="abbc4-422">Per passare agli [invii di amministratore](admin-submission.md)nel portale Microsoft 365 Defender, fare clic **su Vai a Invii.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget Invii nella pagina Report di & e-mail](../../media/submissions-report-widget.png)

<span data-ttu-id="abbc4-424">Il grafico mostra le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-424">The chart shows the following information:</span></span>

- <span data-ttu-id="abbc4-425">**In sospeso**</span><span class="sxs-lookup"><span data-stu-id="abbc4-425">**Pending**</span></span>
- <span data-ttu-id="abbc4-426">**Operazione completata**</span><span class="sxs-lookup"><span data-stu-id="abbc4-426">**Completed**</span></span>

<span data-ttu-id="abbc4-427">Nella pagina **Invii** è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="abbc4-428">**Data riportata**: **Ora inizio** **e Ora fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="abbc4-429">**Tipo di invio:** **Posta** elettronica, **URL** o **File**</span><span class="sxs-lookup"><span data-stu-id="abbc4-429">**Submission type**: **Email**, **URL**, or **File**</span></span>
- <span data-ttu-id="abbc4-430">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-430">**Submission ID**</span></span>
- <span data-ttu-id="abbc4-431">**ID messaggio di rete**</span><span class="sxs-lookup"><span data-stu-id="abbc4-431">**Network Message ID**</span></span>
- <span data-ttu-id="abbc4-432">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-432">**Sender**</span></span>
- <span data-ttu-id="abbc4-433">**Nome**</span><span class="sxs-lookup"><span data-stu-id="abbc4-433">**Name**</span></span>
- <span data-ttu-id="abbc4-434">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="abbc4-434">**Submitted by**</span></span>
- <span data-ttu-id="abbc4-435">**Motivo dell'invio:** **Non posta indesiderata,** **Phish,** **Malware** o **Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="abbc4-435">**Reason for submitting**: **Not junk**, **Phish**, **Malware**, or **Spam**</span></span>
- <span data-ttu-id="abbc4-436">**Stato nuova analisi**: **In sospeso** o **Completato**</span><span class="sxs-lookup"><span data-stu-id="abbc4-436">**Rescan status**: **Pending** or **Completed**</span></span>

<span data-ttu-id="abbc4-437">La tabella dei dettagli sotto il grafico  mostra le stesse informazioni  e ha le stesse opzioni Raggruppa o Personalizza colonne della scheda Inviato per l'analisi in **Invio** di &  \> collaborazione.</span><span class="sxs-lookup"><span data-stu-id="abbc4-437">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="abbc4-438">Per altre informazioni, vedi [Visualizzare gli invii di amministratori a Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="abbc4-438">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Pagina del report Invii nel Microsoft 365 Defender portale](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="abbc4-440">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="abbc4-440">Threat protection status report</span></span>

<span data-ttu-id="abbc4-441">La **relazione sullo stato di Protezione** dalle minacce è disponibile sia in EOP che in Defender per Office 365; Tuttavia, i report contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="abbc4-441">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="abbc4-442">Ad esempio, i clienti di EOP possono visualizzare le informazioni sul malware rilevato nella posta elettronica, ma non informazioni sui file dannosi rilevati dagli allegati Safe per [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)e Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="abbc4-442">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="abbc4-443">Il report fornisce il conteggio dei messaggi di posta elettronica con contenuto dannoso, ad esempio file o indirizzi di siti Web (URL) bloccati dal motore antimalware, eliminazione automatica a zero ore [(ZAP)](zero-hour-auto-purge.md)e Defender per funzionalità di Office 365 come collegamenti [di Safe,](safe-links.md) [allegati Safe](safe-attachments.md)e funzionalità di protezione dalla rappresentazione nei criteri [anti-phishing.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="abbc4-443">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="abbc4-444">È possibile utilizzare queste informazioni per identificare le tendenze o determinare se i criteri dell'organizzazione devono essere rettificati.</span><span class="sxs-lookup"><span data-stu-id="abbc4-444">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="abbc4-445">**Nota:** è importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="abbc4-445">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="abbc4-446">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-446">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="abbc4-447">Nella pagina **Rapporti di collaborazione &** posta elettronica individuare Lo stato di Protezione dalle **minacce** e quindi fare clic su **Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-447">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="abbc4-448">Per passare direttamente al report, aprire uno degli URL seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-448">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="abbc4-449">Defender per Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="abbc4-449">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="abbc4-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="abbc4-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Widget Stato protezione dalle minacce nella pagina Report di collaborazione & posta elettronica](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="abbc4-452">Per impostazione predefinita, il grafico mostra i dati degli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="abbc4-452">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="abbc4-453">Se si fa **clic su** Filtro nella pagina Rapporto sullo stato di **Threat Protection,** è possibile selezionare un intervallo di date di 90 giorni (le sottoscrizioni di valutazione potrebbero essere limitate a 30 giorni).</span><span class="sxs-lookup"><span data-stu-id="abbc4-453">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="abbc4-454">La tabella dei dettagli consente il filtro per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="abbc4-454">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="abbc4-455">Le visualizzazioni disponibili sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="abbc4-455">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="abbc4-456">Visualizzare i dati per panoramica</span><span class="sxs-lookup"><span data-stu-id="abbc4-456">View data by Overview</span></span>

![Visualizzazione panoramica nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="abbc4-458">Nella visualizzazione **Visualizza dati per panoramica** vengono visualizzate le seguenti informazioni di rilevamento nel grafico:</span><span class="sxs-lookup"><span data-stu-id="abbc4-458">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="abbc4-459">**Malware di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="abbc4-459">**Email malware**</span></span>
- <span data-ttu-id="abbc4-460">**Phish di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="abbc4-460">**Email phish**</span></span>
- <span data-ttu-id="abbc4-461">**Malware contenuto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-461">**Content malware**</span></span>

<span data-ttu-id="abbc4-462">Sotto il grafico non è disponibile alcuna tabella dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="abbc4-462">No details table is available below the chart.</span></span>

<span data-ttu-id="abbc4-463">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-463">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="abbc4-464">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-464">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-465">**Rilevamento**: **malware della posta** elettronica, **e-mail phish** o **malware contenuto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-465">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="abbc4-466">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="abbc4-466">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="abbc4-467">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="abbc4-467">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="abbc4-468">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-468">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="abbc4-469">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-469">**Direction**</span></span>
- <span data-ttu-id="abbc4-470">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-470">**Domain**</span></span>
- <span data-ttu-id="abbc4-471">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-471">**Policy type**</span></span>

<span data-ttu-id="abbc4-472">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-472">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="abbc4-473">Visualizzare i dati tramite Analisi \> e-mail e scomposizione grafico per tecnologia di rilevamento</span><span class="sxs-lookup"><span data-stu-id="abbc4-473">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Visualizzazione della tecnologia di rilevamento per la posta elettronica di phishing nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="abbc4-475">Nella visualizzazione **Visualizza dati per \> e-mail phish** e **grafico per** tecnologia di rilevamento, nel grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-475">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="abbc4-476">**Reputazione url dannosa:** <sup>\*</sup> reputazione url dannoso generata da Defender per Office 365 detonazioni in altri Microsoft 365 clienti.</span><span class="sxs-lookup"><span data-stu-id="abbc4-476">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="abbc4-477">**Filtro avanzato:** segnali di phishing basati sull'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="abbc4-477">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="abbc4-478">**Filtro generale**: Segnali di phishing basati sulle regole degli analisti.</span><span class="sxs-lookup"><span data-stu-id="abbc4-478">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="abbc4-479">**Spoofing all'interno dell'organizzazione:** il mittente sta tentando di eseguire lo spoofing del dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="abbc4-479">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="abbc4-480">**Spoofing del dominio esterno:** il mittente sta tentando di eseguire lo spoofing di un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="abbc4-480">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="abbc4-481">**Spoof DMARC:** errore di autenticazione DMARC nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="abbc4-481">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="abbc4-482">**Marchio di rappresentazione**: Rappresentazione di marchi noti in base ai mittenti.</span><span class="sxs-lookup"><span data-stu-id="abbc4-482">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="abbc4-483">**Rilevamento dell'analisi mista**</span><span class="sxs-lookup"><span data-stu-id="abbc4-483">**Mixed analysis detection**</span></span>
- <span data-ttu-id="abbc4-484">**Reputazione file**</span><span class="sxs-lookup"><span data-stu-id="abbc4-484">**File reputation**</span></span>
- <span data-ttu-id="abbc4-485">**Corrispondenza delle impronte digitali**</span><span class="sxs-lookup"><span data-stu-id="abbc4-485">**Fingerprint matching**</span></span>
- <span data-ttu-id="abbc4-486">**Reputazione detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abbc4-486">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="abbc4-487">**Detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abbc4-487">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="abbc4-488">**Utente di rappresentazione**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abbc4-488">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="abbc4-489">**Dominio di rappresentazione** <sup>\*</sup> : Rappresentazione dei domini che il cliente possiede o definisce.</span><span class="sxs-lookup"><span data-stu-id="abbc4-489">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="abbc4-490">**Rappresentazione dell'intelligence delle** <sup>\*</sup> cassette postali : Rappresentazione degli utenti definiti dall'amministratore o appresi tramite l'intelligence delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="abbc4-490">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="abbc4-491">**Detonazione file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abbc4-491">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="abbc4-492">**Campagna**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abbc4-492">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="abbc4-493">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-493">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="abbc4-494">**Data**</span><span class="sxs-lookup"><span data-stu-id="abbc4-494">**Date**</span></span>
- <span data-ttu-id="abbc4-495">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-495">**Subject**</span></span>
- <span data-ttu-id="abbc4-496">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-496">**Sender**</span></span>
- <span data-ttu-id="abbc4-497">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="abbc4-497">**Recipients**</span></span>
- <span data-ttu-id="abbc4-498">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="abbc4-498">**Detected by**</span></span>
- <span data-ttu-id="abbc4-499">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="abbc4-499">**Delivery Status**</span></span>
- <span data-ttu-id="abbc4-500">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-500">**Source of Compromise**</span></span>
- <span data-ttu-id="abbc4-501">**Tag**</span><span class="sxs-lookup"><span data-stu-id="abbc4-501">**Tags**</span></span>

<span data-ttu-id="abbc4-502">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-502">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="abbc4-503">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-503">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-504">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="abbc4-504">**Detection**</span></span>
- <span data-ttu-id="abbc4-505">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="abbc4-505">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="abbc4-506">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-506">**Direction**</span></span>
- <span data-ttu-id="abbc4-507">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="abbc4-507">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="abbc4-508">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-508">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="abbc4-509">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-509">**Domain**</span></span>
- <span data-ttu-id="abbc4-510">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-510">**Policy type**</span></span>
- <span data-ttu-id="abbc4-511">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="abbc4-511">**Policy name** (details table only)</span></span>
- <span data-ttu-id="abbc4-512">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="abbc4-512">**Recipients**</span></span>

<span data-ttu-id="abbc4-513">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-513">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="abbc4-514">Visualizzare i dati tramite malware \> e-mail e scomposizione grafico per tecnologia di rilevamento</span><span class="sxs-lookup"><span data-stu-id="abbc4-514">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Visualizzazione della tecnologia di rilevamento per il malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="abbc4-516">Nella visualizzazione **Visualizza dati per \> malware** e-mail e **grafico per** tecnologia di rilevamento, nel grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-516">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="abbc4-517">**Detonazione file:** <sup>\*</sup> rilevamento da parte Safe allegati.</span><span class="sxs-lookup"><span data-stu-id="abbc4-517">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="abbc4-518">**Reputazione detonazione file:** tutta la reputazione dei file dannosi generata da Defender per Office 365 <sup>\*</sup> detonazioni.</span><span class="sxs-lookup"><span data-stu-id="abbc4-518">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="abbc4-519">**Reputazione file**</span><span class="sxs-lookup"><span data-stu-id="abbc4-519">**File reputation**</span></span>
- <span data-ttu-id="abbc4-520">**Motore antimalware:** <sup>\*</sup> rilevamento da motori antimalware.</span><span class="sxs-lookup"><span data-stu-id="abbc4-520">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="abbc4-521">**Blocco del tipo di file dei** criteri antimalware: si tratta di messaggi di posta elettronica filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="abbc4-521">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="abbc4-522">**REPUTAZIONE URL dannosa**</span><span class="sxs-lookup"><span data-stu-id="abbc4-522">**URL malicious reputation**</span></span>
- <span data-ttu-id="abbc4-523">**Detonazione URL**</span><span class="sxs-lookup"><span data-stu-id="abbc4-523">**URL detonation**</span></span>
- <span data-ttu-id="abbc4-524">**Reputazione detonazione URL**</span><span class="sxs-lookup"><span data-stu-id="abbc4-524">**URL detonation reputation**</span></span>
- <span data-ttu-id="abbc4-525">**Campagna**</span><span class="sxs-lookup"><span data-stu-id="abbc4-525">**Campaign**</span></span>

<span data-ttu-id="abbc4-526">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-526">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="abbc4-527">**Data**</span><span class="sxs-lookup"><span data-stu-id="abbc4-527">**Date**</span></span>
- <span data-ttu-id="abbc4-528">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-528">**Subject**</span></span>
- <span data-ttu-id="abbc4-529">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-529">**Sender**</span></span>
- <span data-ttu-id="abbc4-530">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="abbc4-530">**Recipients**</span></span>
- <span data-ttu-id="abbc4-531">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="abbc4-531">**Detected by**</span></span>
- <span data-ttu-id="abbc4-532">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="abbc4-532">**Delivery Status**</span></span>
- <span data-ttu-id="abbc4-533">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-533">**Source of Compromise**</span></span>
- <span data-ttu-id="abbc4-534">**Tag**</span><span class="sxs-lookup"><span data-stu-id="abbc4-534">**Tags**</span></span>

<span data-ttu-id="abbc4-535">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-535">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="abbc4-536">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-536">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-537">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="abbc4-537">**Detection**</span></span>
- <span data-ttu-id="abbc4-538">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="abbc4-538">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="abbc4-539">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-539">**Direction**</span></span>
- <span data-ttu-id="abbc4-540">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="abbc4-540">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="abbc4-541">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-541">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="abbc4-542">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-542">**Domain**</span></span>
- <span data-ttu-id="abbc4-543">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-543">**Policy type**</span></span>
- <span data-ttu-id="abbc4-544">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="abbc4-544">**Policy name** (details table only)</span></span>
- <span data-ttu-id="abbc4-545">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="abbc4-545">**Recipients**</span></span>

<span data-ttu-id="abbc4-546">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-546">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="abbc4-547">Suddivisione del grafico per tipo di criteri e Visualizzazione dei dati tramite e-mail Phish o \> Visualizzazione dei dati tramite malware di posta \> elettronica</span><span class="sxs-lookup"><span data-stu-id="abbc4-547">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Visualizzazione del tipo di criterio per la posta elettronica di phishing o la posta elettronica malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="abbc4-549">Nelle **visualizzazioni Scomposizione grafico** per tipo di criterio e Visualizza dati per posta elettronica **\> o** Visualizza dati tramite **\> malware** tramite posta elettronica, nei grafici vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-549">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="abbc4-550">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="abbc4-550">**Anti-malware**</span></span>
- <span data-ttu-id="abbc4-551">**Safe Allegati**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="abbc4-551">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="abbc4-552">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="abbc4-552">**Anti-phish**</span></span>
- <span data-ttu-id="abbc4-553">**Protezione da posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="abbc4-553">**Anti-spam**</span></span>
- <span data-ttu-id="abbc4-554">**Regola del flusso di** posta (nota anche come regola di trasporto)</span><span class="sxs-lookup"><span data-stu-id="abbc4-554">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="abbc4-555">**Altri**</span><span class="sxs-lookup"><span data-stu-id="abbc4-555">**Others**</span></span>

<span data-ttu-id="abbc4-556">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-556">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="abbc4-557">**Data**</span><span class="sxs-lookup"><span data-stu-id="abbc4-557">**Date**</span></span>
- <span data-ttu-id="abbc4-558">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-558">**Subject**</span></span>
- <span data-ttu-id="abbc4-559">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-559">**Sender**</span></span>
- <span data-ttu-id="abbc4-560">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="abbc4-560">**Recipients**</span></span>
- <span data-ttu-id="abbc4-561">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="abbc4-561">**Detected by**</span></span>
- <span data-ttu-id="abbc4-562">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="abbc4-562">**Delivery Status**</span></span>
- <span data-ttu-id="abbc4-563">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-563">**Source of Compromise**</span></span>
- <span data-ttu-id="abbc4-564">**Tag**</span><span class="sxs-lookup"><span data-stu-id="abbc4-564">**Tags**</span></span>

<span data-ttu-id="abbc4-565">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-565">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="abbc4-566">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-566">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-567">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="abbc4-567">**Detection**</span></span>
- <span data-ttu-id="abbc4-568">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="abbc4-568">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="abbc4-569">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-569">**Direction**</span></span>
- <span data-ttu-id="abbc4-570">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="abbc4-570">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="abbc4-571">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-571">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="abbc4-572">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-572">**Domain**</span></span>
- <span data-ttu-id="abbc4-573">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-573">**Policy type**</span></span>
- <span data-ttu-id="abbc4-574">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="abbc4-574">**Policy name** (details table only)</span></span>
- <span data-ttu-id="abbc4-575">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="abbc4-575">**Recipients**</span></span>

<span data-ttu-id="abbc4-576">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-576">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="abbc4-577">Suddivisione del grafico per stato di recapito e Visualizzazione dei dati tramite e-mail Phish o \> Visualizzazione dei dati tramite malware di posta \> elettronica</span><span class="sxs-lookup"><span data-stu-id="abbc4-577">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Visualizzazione dello stato del recapito per posta elettronica di phishing e posta elettronica malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="abbc4-579">Nelle **visualizzazioni Scomposizione grafico** per stato recapito e Visualizza dati per posta elettronica **\> o** Visualizza dati tramite **\> malware** tramite posta elettronica, nei grafici vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-579">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="abbc4-580">**Cassetta postale ospitata: Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="abbc4-580">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="abbc4-581">**Cassetta postale ospitata: Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="abbc4-581">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="abbc4-582">**Cassetta postale ospitata: cartella personalizzata**</span><span class="sxs-lookup"><span data-stu-id="abbc4-582">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="abbc4-583">**Cassetta postale ospitata: Elementi eliminati**</span><span class="sxs-lookup"><span data-stu-id="abbc4-583">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="abbc4-584">**Inoltrato**</span><span class="sxs-lookup"><span data-stu-id="abbc4-584">**Forwarded**</span></span>
- <span data-ttu-id="abbc4-585">**Server locale: recapitato**</span><span class="sxs-lookup"><span data-stu-id="abbc4-585">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="abbc4-586">**Quarantena**</span><span class="sxs-lookup"><span data-stu-id="abbc4-586">**Quarantine**</span></span>
- <span data-ttu-id="abbc4-587">**Recapito non riuscito**</span><span class="sxs-lookup"><span data-stu-id="abbc4-587">**Delivery failed**</span></span>
- <span data-ttu-id="abbc4-588">**Rilasciato**</span><span class="sxs-lookup"><span data-stu-id="abbc4-588">**Dropped**</span></span>

<span data-ttu-id="abbc4-589">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-589">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="abbc4-590">**Data**</span><span class="sxs-lookup"><span data-stu-id="abbc4-590">**Date**</span></span>
- <span data-ttu-id="abbc4-591">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-591">**Subject**</span></span>
- <span data-ttu-id="abbc4-592">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-592">**Sender**</span></span>
- <span data-ttu-id="abbc4-593">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="abbc4-593">**Recipients**</span></span>
- <span data-ttu-id="abbc4-594">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="abbc4-594">**Detected by**</span></span>
- <span data-ttu-id="abbc4-595">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="abbc4-595">**Delivery Status**</span></span>
- <span data-ttu-id="abbc4-596">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-596">**Source of Compromise**</span></span>
- <span data-ttu-id="abbc4-597">**Tag**</span><span class="sxs-lookup"><span data-stu-id="abbc4-597">**Tags**</span></span>

<span data-ttu-id="abbc4-598">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-598">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="abbc4-599">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-599">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-600">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="abbc4-600">**Detection**</span></span>
- <span data-ttu-id="abbc4-601">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="abbc4-601">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="abbc4-602">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-602">**Direction**</span></span>
- <span data-ttu-id="abbc4-603">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="abbc4-603">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="abbc4-604">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-604">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="abbc4-605">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-605">**Domain**</span></span>
- <span data-ttu-id="abbc4-606">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-606">**Policy type**</span></span>
- <span data-ttu-id="abbc4-607">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="abbc4-607">**Policy name** (details table only)</span></span>
- <span data-ttu-id="abbc4-608">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="abbc4-608">**Recipients**</span></span>

<span data-ttu-id="abbc4-609">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-609">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="abbc4-610">Visualizzare i dati in base al malware contenuto \></span><span class="sxs-lookup"><span data-stu-id="abbc4-610">View data by Content \> Malware</span></span>

![Visualizzazione malware contenuto nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="abbc4-612">Nella visualizzazione **Visualizzazione dati per \> malware** contenuto, nel grafico per Microsoft Defender per Office 365 organizzazioni:</span><span class="sxs-lookup"><span data-stu-id="abbc4-612">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="abbc4-613">**Motore antimalware:** file dannosi rilevati in Sharepoint, OneDrive e Microsoft Teams dal rilevamento di [virus incorporato in Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-613">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="abbc4-614">**Detonazione file:** file dannosi rilevati da Safe allegati per [SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-614">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="abbc4-615">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-615">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="abbc4-616">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-616">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-617">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-617">**Location**</span></span>
- <span data-ttu-id="abbc4-618">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="abbc4-618">**Detected by**</span></span>
- <span data-ttu-id="abbc4-619">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="abbc4-619">**Malware name**</span></span>

<span data-ttu-id="abbc4-620">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-620">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="abbc4-621">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-621">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-622">**Rilevamento:** **motore antimalware o** **detonazione file**</span><span class="sxs-lookup"><span data-stu-id="abbc4-622">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="abbc4-623">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-623">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="abbc4-624">Visualizzare i dati per sostituzione di sistema</span><span class="sxs-lookup"><span data-stu-id="abbc4-624">View data by System override</span></span>

![Visualizzazione sostituzione messaggio nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="abbc4-626">Nella visualizzazione **Visualizza dati per sostituzione di** sistema, nel grafico vengono visualizzate le seguenti informazioni sul motivo dell'override:</span><span class="sxs-lookup"><span data-stu-id="abbc4-626">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="abbc4-627">**Ignora locale**</span><span class="sxs-lookup"><span data-stu-id="abbc4-627">**On-premises skip**</span></span>
- <span data-ttu-id="abbc4-628">**IP allow**</span><span class="sxs-lookup"><span data-stu-id="abbc4-628">**IP allow**</span></span>
- <span data-ttu-id="abbc4-629">**Exchange di trasporto della posta** elettronica (regola del flusso di posta)</span><span class="sxs-lookup"><span data-stu-id="abbc4-629">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="abbc4-630">**Mittenti consentiti dall'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-630">**Organization allowed senders**</span></span>
- <span data-ttu-id="abbc4-631">**Domini consentiti dall'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-631">**Organization allowed domains**</span></span>
- <span data-ttu-id="abbc4-632">**ZAP non abilitato**</span><span class="sxs-lookup"><span data-stu-id="abbc4-632">**ZAP not enabled**</span></span>
- <span data-ttu-id="abbc4-633">**Cartella Posta indesiderata non abilitata**</span><span class="sxs-lookup"><span data-stu-id="abbc4-633">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="abbc4-634">**Mittente Safe utente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-634">**User Safe Sender**</span></span>
- <span data-ttu-id="abbc4-635">**Dominio Safe utente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-635">**User Safe Domain**</span></span>

<span data-ttu-id="abbc4-636">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-636">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="abbc4-637">**Data**</span><span class="sxs-lookup"><span data-stu-id="abbc4-637">**Date**</span></span>
- <span data-ttu-id="abbc4-638">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="abbc4-638">**Subject**</span></span>
- <span data-ttu-id="abbc4-639">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-639">**Sender**</span></span>
- <span data-ttu-id="abbc4-640">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="abbc4-640">**Recipients**</span></span>
- <span data-ttu-id="abbc4-641">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="abbc4-641">**Detected by**</span></span>
- <span data-ttu-id="abbc4-642">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="abbc4-642">**Delivery Status**</span></span>
- <span data-ttu-id="abbc4-643">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-643">**Source of Compromise**</span></span>
- <span data-ttu-id="abbc4-644">**Tag**</span><span class="sxs-lookup"><span data-stu-id="abbc4-644">**Tags**</span></span>

<span data-ttu-id="abbc4-645">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-645">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="abbc4-646">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-646">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="abbc4-647">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="abbc4-647">**Detection**</span></span>
- <span data-ttu-id="abbc4-648">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="abbc4-648">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="abbc4-649">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-649">**Direction**</span></span>
- <span data-ttu-id="abbc4-650">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="abbc4-650">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="abbc4-651">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-651">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="abbc4-652">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-652">**Domain**</span></span>
- <span data-ttu-id="abbc4-653">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-653">**Policy type**</span></span>
- <span data-ttu-id="abbc4-654">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="abbc4-654">**Policy name** (details table only)</span></span>
- <span data-ttu-id="abbc4-655">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="abbc4-655">**Recipients**</span></span>

<span data-ttu-id="abbc4-656">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-656">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="abbc4-657"><sup>\*</sup>Defender solo per Office 365</span><span class="sxs-lookup"><span data-stu-id="abbc4-657"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="abbc4-658">Report principale sul malware</span><span class="sxs-lookup"><span data-stu-id="abbc4-658">Top malware report</span></span>

<span data-ttu-id="abbc4-659">Il **report Top malware** mostra i vari tipi di malware rilevati dalla protezione [antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="abbc4-659">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="abbc4-660">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-660">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="abbc4-661">Nella pagina **E-mail & rapporti di collaborazione,** individuare **Malware** principale e quindi fare clic **su Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-661">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="abbc4-662">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="abbc4-662">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Widget malware principale nella pagina Report di collaborazione & posta elettronica](../../media/top-malware-report-widget.png)

<span data-ttu-id="abbc4-664">Quando si passa il mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi rilevati come malware.</span><span class="sxs-lookup"><span data-stu-id="abbc4-664">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="abbc4-665">Nella pagina **Report malware principale** viene visualizzata una versione più grande del grafico a torta nella pagina del report. La tabella dei dettagli sotto il grafico mostra le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-665">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="abbc4-666">**Malware principale**</span><span class="sxs-lookup"><span data-stu-id="abbc4-666">**Top malware**</span></span>
- <span data-ttu-id="abbc4-667">**Numero**</span><span class="sxs-lookup"><span data-stu-id="abbc4-667">**Count**</span></span>

<span data-ttu-id="abbc4-668">Se si fa **clic su Filtro**, è possibile specificare un intervallo di date con Data **inizio** e **Data fine**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-668">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Visualizzazione dei report principali sul malware](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="abbc4-670">Report di protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="abbc4-670">URL threat protection report</span></span>

<span data-ttu-id="abbc4-671">Il **report di protezione dalle minacce URL** è disponibile in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="abbc4-671">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="abbc4-672">Per ulteriori informazioni, vedere [Report di protezione dalle minacce URL](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="abbc4-672">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="abbc4-673">Rapporto messaggi segnalati dall'utente</span><span class="sxs-lookup"><span data-stu-id="abbc4-673">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="abbc4-674">Per il corretto funzionamento del rapporto **Messaggi segnalati** dall'utente, è necessario che la registrazione di controllo sia attivata per l'Microsoft 365 locale. </span><span class="sxs-lookup"><span data-stu-id="abbc4-674">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="abbc4-675">Questa operazione viene in genere eseguita da un utente a cui è assegnato il ruolo Log di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="abbc4-675">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="abbc4-676">Per ulteriori informazioni, vedere [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-676">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="abbc4-677">Il **report Messaggi segnalati** dall'utente mostra informazioni sui messaggi di posta elettronica [](enable-the-report-message-add-in.md) segnalati dagli utenti come posta indesiderata, tentativi di phishing o buona posta utilizzando il componente aggiuntivo Segnala messaggio o Segnala [phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-677">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="abbc4-678">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="abbc4-678">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="abbc4-679">Nella pagina **Rapporti di collaborazione &** posta elettronica individuare Messaggi segnalati **dall'utente** e quindi fare clic su **Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-679">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="abbc4-680">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="abbc4-680">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="abbc4-681">Per passare agli [invii di amministratore](admin-submission.md)nel portale Microsoft 365 Defender, fare clic **su Vai a Invii.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-681">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget Messaggi segnalati dall'utente nella pagina Rapporti di collaborazione & posta elettronica](../../media/user-reported-messages-widget.png)

<span data-ttu-id="abbc4-683">Nella pagina **Messaggi segnalati** dall'utente è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="abbc4-683">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="abbc4-684">**Data riportata**: **Ora inizio** **e Ora fine**</span><span class="sxs-lookup"><span data-stu-id="abbc4-684">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="abbc4-685">**Segnalato da**</span><span class="sxs-lookup"><span data-stu-id="abbc4-685">**Reported by**</span></span>
- <span data-ttu-id="abbc4-686">**Oggetto e-mail**</span><span class="sxs-lookup"><span data-stu-id="abbc4-686">**Email subject**</span></span>
- <span data-ttu-id="abbc4-687">**ID segnalato messaggio**</span><span class="sxs-lookup"><span data-stu-id="abbc4-687">**Message reported ID**</span></span>
- <span data-ttu-id="abbc4-688">**ID messaggio di rete**</span><span class="sxs-lookup"><span data-stu-id="abbc4-688">**Network Message ID**</span></span>
- <span data-ttu-id="abbc4-689">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-689">**Sender**</span></span>
- <span data-ttu-id="abbc4-690">**Motivo segnalato**</span><span class="sxs-lookup"><span data-stu-id="abbc4-690">**Reported reason**</span></span>
  - <span data-ttu-id="abbc4-691">**Non indesiderato**</span><span class="sxs-lookup"><span data-stu-id="abbc4-691">**Not junk**</span></span>
  - <span data-ttu-id="abbc4-692">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="abbc4-692">**Phish**</span></span>
  - <span data-ttu-id="abbc4-693">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="abbc4-693">**Spam**</span></span>
- <span data-ttu-id="abbc4-694">**Simulazione phish**: **Sì** o **No**</span><span class="sxs-lookup"><span data-stu-id="abbc4-694">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="abbc4-695">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="abbc4-695">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="abbc4-696">Per raggruppare le voci, fare clic **su Gruppo** e selezionare uno dei valori seguenti nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="abbc4-696">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="abbc4-697">**Nessuna**</span><span class="sxs-lookup"><span data-stu-id="abbc4-697">**None**</span></span>
- <span data-ttu-id="abbc4-698">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="abbc4-698">**Reason**</span></span>
- <span data-ttu-id="abbc4-699">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-699">**Sender**</span></span>
- <span data-ttu-id="abbc4-700">**Segnalato da**</span><span class="sxs-lookup"><span data-stu-id="abbc4-700">**Reported by**</span></span>
- <span data-ttu-id="abbc4-701">**Risultato dell'analisi**</span><span class="sxs-lookup"><span data-stu-id="abbc4-701">**Rescan result**</span></span>
- <span data-ttu-id="abbc4-702">**Simulazione phish**</span><span class="sxs-lookup"><span data-stu-id="abbc4-702">**Phish simulation**</span></span>

![Rapporto messaggi segnalati dall'utente](../../media/user-reported-messages-report.png)

<span data-ttu-id="abbc4-704">Nella tabella dei dettagli sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="abbc4-704">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="abbc4-705">**Oggetto e-mail**</span><span class="sxs-lookup"><span data-stu-id="abbc4-705">**Email subject**</span></span>
- <span data-ttu-id="abbc4-706">**Segnalato da**</span><span class="sxs-lookup"><span data-stu-id="abbc4-706">**Reported by**</span></span>
- <span data-ttu-id="abbc4-707">**Data riportata**</span><span class="sxs-lookup"><span data-stu-id="abbc4-707">**Date reported**</span></span>
- <span data-ttu-id="abbc4-708">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="abbc4-708">**Sender**</span></span>
- <span data-ttu-id="abbc4-709">**Motivo segnalato**</span><span class="sxs-lookup"><span data-stu-id="abbc4-709">**Reported reason**</span></span>
- <span data-ttu-id="abbc4-710">**Risultato dell'analisi**</span><span class="sxs-lookup"><span data-stu-id="abbc4-710">**Rescan result**</span></span>
- <span data-ttu-id="abbc4-711">**Tag**</span><span class="sxs-lookup"><span data-stu-id="abbc4-711">**Tags**</span></span>

<span data-ttu-id="abbc4-712">Per inviare un messaggio a Microsoft per l'analisi, selezionare la voce del messaggio dalla tabella, fare clic su Invia a **Microsoft** per l'analisi e quindi selezionare uno dei valori seguenti nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="abbc4-712">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="abbc4-713">**Segnala pulito**</span><span class="sxs-lookup"><span data-stu-id="abbc4-713">**Report clean**</span></span>
- <span data-ttu-id="abbc4-714">**Segnalare phishing**</span><span class="sxs-lookup"><span data-stu-id="abbc4-714">**Report phishing**</span></span>
- <span data-ttu-id="abbc4-715">**Segnalare malware**</span><span class="sxs-lookup"><span data-stu-id="abbc4-715">**Report malware**</span></span>
- <span data-ttu-id="abbc4-716">**Segnala posta indesiderata**'</span><span class="sxs-lookup"><span data-stu-id="abbc4-716">**Report spam**'</span></span>
- <span data-ttu-id="abbc4-717">**Attivare l'indagine** (Defender per Office 365)</span><span class="sxs-lookup"><span data-stu-id="abbc4-717">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="abbc4-718">Quali autorizzazioni sono necessarie per visualizzare questi report?</span><span class="sxs-lookup"><span data-stu-id="abbc4-718">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="abbc4-719">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel portale di Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="abbc4-719">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="abbc4-720">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="abbc4-720">**Organization Management**</span></span>
- <span data-ttu-id="abbc4-721">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="abbc4-721">**Security Administrator**</span></span>
- <span data-ttu-id="abbc4-722">**Lettore sicurezza**</span><span class="sxs-lookup"><span data-stu-id="abbc4-722">**Security Reader**</span></span>
- <span data-ttu-id="abbc4-723">**Lettore globale**</span><span class="sxs-lookup"><span data-stu-id="abbc4-723">**Global Reader**</span></span>

<span data-ttu-id="abbc4-724">Per ulteriori informazioni, vedere [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-724">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="abbc4-725">**Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nel interfaccia di amministrazione di Microsoft 365 offre agli utenti le  autorizzazioni necessarie nel portale di Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="abbc4-725">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="abbc4-726">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="abbc4-726">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="abbc4-727">Cosa succede se i report non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="abbc4-727">What if the reports aren't showing data?</span></span>

<span data-ttu-id="abbc4-728">Se i dati nei report non vengono visualizzati, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="abbc4-728">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="abbc4-729">Per ulteriori informazioni, vedere [Protezione dalle minacce.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="abbc4-729">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="abbc4-730">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="abbc4-730">Related topics</span></span>

[<span data-ttu-id="abbc4-731">Protezione da posta indesiderata e antimalware in EOP</span><span class="sxs-lookup"><span data-stu-id="abbc4-731">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="abbc4-732">Report e informazioni dettagliate intelligenti nel portale Microsoft 365 Defender dati</span><span class="sxs-lookup"><span data-stu-id="abbc4-732">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="abbc4-733">Visualizzare i report del flusso di posta nel portale Microsoft 365 Defender posta</span><span class="sxs-lookup"><span data-stu-id="abbc4-733">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="abbc4-734">Visualizzare i report per Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="abbc4-734">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
