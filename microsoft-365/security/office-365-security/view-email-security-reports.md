---
title: Visualizzare i report di sicurezza della posta elettronica nel portale di Microsoft 365 Defender
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
description: Informazioni su come trovare e utilizzare i report di sicurezza della posta elettronica per l'organizzazione. I report di sicurezza della posta elettronica sono disponibili nel portale di Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d46aec8601d19234eed8682955ffef27b7e9b467
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985304"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="261c9-104">Visualizzare i report di sicurezza della posta elettronica nel portale di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="261c9-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="261c9-105">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="261c9-105">**Applies to**</span></span>
- [<span data-ttu-id="261c9-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="261c9-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="261c9-107">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="261c9-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="261c9-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="261c9-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="261c9-109">Nel portale di Microsoft 365 Defender sono disponibili diversi report che consentono di vedere come le funzionalità di sicurezza della posta elettronica, ad esempio la protezione da posta indesiderata, antimalware e crittografia <https://security.microsoft.com> in Microsoft 365, proteggono l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="261c9-109">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="261c9-110">Se si dispone delle autorizzazioni [necessarie,](#what-permissions-are-needed-to-view-these-reports)è possibile visualizzare questi report nel  portale di Microsoft 365 Defender andando a Rapporti e-mail & \> **collaborazione** \> **E-mail**& rapporti di collaborazione .</span><span class="sxs-lookup"><span data-stu-id="261c9-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="261c9-111">Per passare direttamente alla pagina Rapporti di **collaborazione &** e-mail, aprire <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="261c9-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Pagina dei & di collaborazione tramite posta elettronica nel portale di Microsoft 365 Defender](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="261c9-113">Alcuni dei report nella pagina Rapporti di **collaborazione &** e-mail richiedono Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="261c9-113">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="261c9-114">Per informazioni su questi report, vedere [View Defender for Office 365 reports in the Microsoft 365 Defender portal.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="261c9-114">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="261c9-115">I report correlati al flusso di posta sono ora disponibili nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="261c9-115">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="261c9-116">Per ulteriori informazioni su questi report, vedere [Mail flow reports in the new Exchange admin center.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="261c9-116">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="261c9-117">Report utenti compromessi</span><span class="sxs-lookup"><span data-stu-id="261c9-117">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="261c9-118">Questo report è disponibile nelle organizzazioni di Microsoft 365 con cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="261c9-118">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="261c9-119">Non è disponibile nelle organizzazioni autonome di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="261c9-119">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="261c9-120">Il **report Utenti compromessi** mostra il numero di  account  utente contrassegnati come sospetti o con restrizioni negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="261c9-120">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="261c9-121">Gli account in uno di questi stati sono problematici o addirittura compromessi.</span><span class="sxs-lookup"><span data-stu-id="261c9-121">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="261c9-122">Con un uso frequente, è possibile utilizzare il report per individuare picchi e persino tendenze in account sospetti o con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="261c9-122">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="261c9-123">Per ulteriori informazioni sugli utenti compromessi, vedere [Risposta a un account di posta elettronica compromesso.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="261c9-123">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Utenti compromessi nella pagina Report & e-mail](../../media/compromised-users-report-widget.png)

<span data-ttu-id="261c9-125">La visualizzazione aggregata mostra i dati degli ultimi 90 giorni e la visualizzazione dettagli mostra i dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="261c9-125">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="261c9-126">Per visualizzare il report nel portale di Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="261c9-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="261c9-127">In **Utenti compromessi** fare clic **su Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="261c9-127">On **Compromised users**, click **View details**.</span></span> <span data-ttu-id="261c9-128">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="261c9-128">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="261c9-129">Dopo aver **fatto** clic su Visualizza dettagli, è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="261c9-129">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="261c9-130">**Date (UTC)**: **Data di inizio** e Data di **fine**.</span><span class="sxs-lookup"><span data-stu-id="261c9-130">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="261c9-131">**Attività**:</span><span class="sxs-lookup"><span data-stu-id="261c9-131">**Activity**:</span></span>
  - <span data-ttu-id="261c9-132">**Sospetto:** l'account utente ha inviato messaggi di posta elettronica sospetti ed è a rischio di essere limitato a inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="261c9-132">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="261c9-133">**Con restrizioni**: all'account utente è stato limitato l'invio di posta elettronica a causa di modelli altamente sospetti.</span><span class="sxs-lookup"><span data-stu-id="261c9-133">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="261c9-134">Al termine del filtro, fare clic **su Applica** o **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="261c9-134">When you're finished filtering, click **Apply** or **Cancel**.</span></span>

![Visualizzazione report nel report Utenti compromessi](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="261c9-136">Nella tabella sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-136">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="261c9-137">**Ora creazione**</span><span class="sxs-lookup"><span data-stu-id="261c9-137">**Creation time**</span></span>
- <span data-ttu-id="261c9-138">**ID utente**</span><span class="sxs-lookup"><span data-stu-id="261c9-138">**User ID**</span></span>
- <span data-ttu-id="261c9-139">**Azione**</span><span class="sxs-lookup"><span data-stu-id="261c9-139">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="261c9-140">Report delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="261c9-140">Exchange transport rule report</span></span>

<span data-ttu-id="261c9-141">Il **rapporto sulle regole di trasporto** di Exchange mostra l'effetto delle regole del flusso di posta (note anche come regole di trasporto) sui messaggi in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="261c9-141">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="261c9-142">Per visualizzare il report nel portale di Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="261c9-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="261c9-143">In **Regola di trasporto di Exchange** fare clic su Visualizza **dettagli**.</span><span class="sxs-lookup"><span data-stu-id="261c9-143">On **Exchange transport rule**, click **View details**.</span></span> <span data-ttu-id="261c9-144">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="261c9-144">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Widget regola di trasporto di Exchange nella pagina Rapporti di collaborazione & e-mail](../../media/transport-rule-report-widget.png)

<span data-ttu-id="261c9-146">Dopo aver fatto **clic su Visualizza dettagli,** sono disponibili i grafici e i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-146">After you click **View details**, the following charts and data are available:</span></span>

- <span data-ttu-id="261c9-147">**Visualizzare i dati in base alle regole di trasporto di Exchange** \> **Scomposizione grafico per direzione**: questo  grafico mostra il numero di **messaggi in** ingresso e in uscita interessati dalle regole del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="261c9-147">**View data by Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>

- <span data-ttu-id="261c9-148">**Visualizzare i dati in base alle regole di trasporto di Exchange** \> **Suddivisione del grafico per gravità**: questo grafico mostra il numero **di** messaggi Di gravità **elevata,** Gravità media e **Gravità** bassa.</span><span class="sxs-lookup"><span data-stu-id="261c9-148">**View data by Exchange transport rules** \> **Chart breakdown by Severity**: This chart shows the number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="261c9-149">Il livello di gravità viene impostato come azione nella regola **(** Controlla questa regola con livello di gravità o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="261c9-149">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="261c9-150">Per ulteriori informazioni, vedere [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="261c9-150">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="261c9-151">**Visualizzare i dati in base alle regole di trasporto di Exchange DLP** \> **Scomposizione grafico per direzione**: questo  grafico mostra il numero di messaggi **in** ingresso e in uscita interessati dalle regole del flusso di posta DLP (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="261c9-151">**View data by DLP Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

- <span data-ttu-id="261c9-152">**Visualizzare i dati in base alle regole di trasporto di Exchange DLP** \> **Suddivisione del grafico** in base alla gravità : in questa  visualizzazione viene visualizzato il numero di messaggi di gravità **elevata,** di gravità **media** e di gravità bassa interessati dalle regole del flusso di posta DLP.</span><span class="sxs-lookup"><span data-stu-id="261c9-152">**View data by DLP Exchange transport rules** \> **Chart breakdown by Severity**: This view shows the number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="261c9-153">Per La selezione delle regole di trasporto di Exchange Per visualizzare i dati in base alle regole di trasporto di **Exchange,** nella tabella dei dettagli sotto il grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-153">For **View data by Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="261c9-154">**Data**</span><span class="sxs-lookup"><span data-stu-id="261c9-154">**Date**</span></span>
- <span data-ttu-id="261c9-155">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="261c9-155">**Transport rule**</span></span>
- <span data-ttu-id="261c9-156">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="261c9-156">**Subject**</span></span>
- <span data-ttu-id="261c9-157">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="261c9-157">**Sender address**</span></span>
- <span data-ttu-id="261c9-158">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="261c9-158">**Recipient address**</span></span>
- <span data-ttu-id="261c9-159">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="261c9-159">**Severity**</span></span>
- <span data-ttu-id="261c9-160">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="261c9-160">**Direction**</span></span>

<span data-ttu-id="261c9-161">Per Visualizzare i dati in base alle selezioni delle regole di trasporto di **Exchange DLP,** nella tabella dei dettagli sotto il grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-161">For **View data by DLP Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="261c9-162">**Data**</span><span class="sxs-lookup"><span data-stu-id="261c9-162">**Date**</span></span>
- <span data-ttu-id="261c9-163">**Criterio DLP**</span><span class="sxs-lookup"><span data-stu-id="261c9-163">**DLP policy**</span></span>
- <span data-ttu-id="261c9-164">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="261c9-164">**Transport rule**</span></span>
- <span data-ttu-id="261c9-165">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="261c9-165">**Subject**</span></span>
- <span data-ttu-id="261c9-166">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="261c9-166">**Sender address**</span></span>
- <span data-ttu-id="261c9-167">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="261c9-167">**Recipient address**</span></span>
- <span data-ttu-id="261c9-168">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="261c9-168">**Severity**</span></span>
- <span data-ttu-id="261c9-169">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="261c9-169">**Direction**</span></span>

<span data-ttu-id="261c9-170">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="261c9-170">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="261c9-171">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-171">**Start date** and **End date**</span></span>
- <span data-ttu-id="261c9-172">**Direzione**: **In uscita** e **in ingresso**</span><span class="sxs-lookup"><span data-stu-id="261c9-172">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="261c9-173">**Gravità**: **Gravità elevata,** **Gravità media** e **Gravità bassa**</span><span class="sxs-lookup"><span data-stu-id="261c9-173">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

![Visualizzazione dei report nel report delle regole di trasporto di Exchange](../../media/transport-rule-report-report-view.png)

## <a name="mailflow-status-report"></a><span data-ttu-id="261c9-175">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="261c9-175">Mailflow status report</span></span>

<span data-ttu-id="261c9-176">Il **rapporto** sullo stato del flusso di posta è un report intelligente che mostra informazioni sulla posta elettronica in arrivo e in uscita, sui rilevamenti di posta indesiderata, sul malware, sulla posta elettronica identificata come "buona" e sulle informazioni sulla posta elettronica consentita o bloccata sul perimetro.</span><span class="sxs-lookup"><span data-stu-id="261c9-176">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="261c9-177">Questo è l'unico report che contiene informazioni sulla protezione perimetrale e mostra la quantità di posta elettronica bloccata prima di essere consentita al servizio per la valutazione da Parte di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="261c9-177">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="261c9-178">È importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="261c9-178">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="261c9-179">Per visualizzare il report nel portale di Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="261c9-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="261c9-180">In **Riepilogo stato flusso di posta** fare clic su Visualizza **dettagli.**</span><span class="sxs-lookup"><span data-stu-id="261c9-180">On **Mailflow status summary**, click **View details**.</span></span> <span data-ttu-id="261c9-181">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="261c9-181">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Widget Riepilogo stato flusso di posta nella pagina Rapporti di collaborazione & posta elettronica](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="261c9-183">Visualizzazione tipo per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="261c9-183">Type view for the Mailflow status report</span></span>

<span data-ttu-id="261c9-184">Quando si apre il report, la **scheda Tipo** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="261c9-184">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="261c9-185">Per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-185">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="261c9-186">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="261c9-186">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="261c9-187">**Direzione della posta**:</span><span class="sxs-lookup"><span data-stu-id="261c9-187">**Mail direction**:</span></span>
  - <span data-ttu-id="261c9-188">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="261c9-188">**Inbound**</span></span>
  - <span data-ttu-id="261c9-189">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="261c9-189">**Outbound**</span></span>
  - <span data-ttu-id="261c9-190">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="261c9-190">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="261c9-191">mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da **In ingresso** e **In uscita)**</span><span class="sxs-lookup"><span data-stu-id="261c9-191">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="261c9-192">**Digitare**:</span><span class="sxs-lookup"><span data-stu-id="261c9-192">**Type**:</span></span>
  - <span data-ttu-id="261c9-193">**Posta buona**</span><span class="sxs-lookup"><span data-stu-id="261c9-193">**Good mail**</span></span>
  - <span data-ttu-id="261c9-194">**Malware**</span><span class="sxs-lookup"><span data-stu-id="261c9-194">**Malware**</span></span>
  - <span data-ttu-id="261c9-195">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="261c9-195">**Spam**</span></span>
  - <span data-ttu-id="261c9-196">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="261c9-196">**Edge protection**</span></span>
  - <span data-ttu-id="261c9-197">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="261c9-197">**Rule messages**</span></span>
  - <span data-ttu-id="261c9-198">**Posta di phishing**</span><span class="sxs-lookup"><span data-stu-id="261c9-198">**Phishing email**</span></span>
- <span data-ttu-id="261c9-199">**Domain**: **All**</span><span class="sxs-lookup"><span data-stu-id="261c9-199">**Domain**: **All**</span></span>

<span data-ttu-id="261c9-200">Il grafico è organizzato in base ai **valori Type.**</span><span class="sxs-lookup"><span data-stu-id="261c9-200">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="261c9-201">È possibile modificare questi filtri facendo clic **su Filtro** o su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="261c9-201">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="261c9-202">La tabella dati contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-202">The data table contains the following information:</span></span>

- <span data-ttu-id="261c9-203">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="261c9-203">**Direction**</span></span>
- <span data-ttu-id="261c9-204">**Type**</span><span class="sxs-lookup"><span data-stu-id="261c9-204">**Type**</span></span>
- <span data-ttu-id="261c9-205">**24 ore**</span><span class="sxs-lookup"><span data-stu-id="261c9-205">**24 hours**</span></span>
- <span data-ttu-id="261c9-206">**3 giorni**</span><span class="sxs-lookup"><span data-stu-id="261c9-206">**3 days**</span></span>
- <span data-ttu-id="261c9-207">**7 giorni**</span><span class="sxs-lookup"><span data-stu-id="261c9-207">**7 days**</span></span>
- <span data-ttu-id="261c9-208">**15 giorni**</span><span class="sxs-lookup"><span data-stu-id="261c9-208">**15 days**</span></span>
- <span data-ttu-id="261c9-209">**30 giorni**</span><span class="sxs-lookup"><span data-stu-id="261c9-209">**30 days**</span></span>

<span data-ttu-id="261c9-210">Se si fa **clic su Scegli una categoria per ulteriori dettagli,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-210">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="261c9-211">**Posta elettronica di phishing**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="261c9-211">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="261c9-212">**Malware nella posta elettronica**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="261c9-212">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="261c9-213">**Rilevamenti di posta indesiderata:** questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="261c9-213">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="261c9-214">**Posta indesiderata bloccata** perimetrali : questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="261c9-214">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="261c9-215">Esportare dalla visualizzazione Tipo</span><span class="sxs-lookup"><span data-stu-id="261c9-215">Export from Type view</span></span>

<span data-ttu-id="261c9-216">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="261c9-216">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="261c9-217">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="261c9-217">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="261c9-218">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="261c9-218">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="261c9-219">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="261c9-219">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione tipo nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="261c9-221">Visualizzazione della direzione per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="261c9-221">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="261c9-222">Se si fa clic **sulla scheda Direzione,** vengono utilizzati gli stessi filtri predefiniti della **visualizzazione** Tipo.</span><span class="sxs-lookup"><span data-stu-id="261c9-222">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="261c9-223">Il grafico è organizzato in base **ai valori di** Direzione.</span><span class="sxs-lookup"><span data-stu-id="261c9-223">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="261c9-224">È possibile modificare questi filtri facendo clic **su Filtro** o su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="261c9-224">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="261c9-225">Vengono utilizzati gli stessi filtri **della** visualizzazione Tipo.</span><span class="sxs-lookup"><span data-stu-id="261c9-225">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="261c9-226">La tabella dati contiene le stesse informazioni della **visualizzazione Tipo.**</span><span class="sxs-lookup"><span data-stu-id="261c9-226">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="261c9-227">**L'opzione Scegliere una categoria per ulteriori dettagli** le selezioni e il comportamento disponibili sono gli stessi della visualizzazione **Tipo.**</span><span class="sxs-lookup"><span data-stu-id="261c9-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="261c9-228">Esportare dalla visualizzazione Direzione</span><span class="sxs-lookup"><span data-stu-id="261c9-228">Export from Direction view</span></span>

<span data-ttu-id="261c9-229">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="261c9-229">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="261c9-230">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="261c9-230">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="261c9-231">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="261c9-231">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="261c9-232">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="261c9-232">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione direzione nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="261c9-234">Visualizzazione imbuto per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="261c9-234">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="261c9-235">La **visualizzazione Imbuto** mostra come le funzionalità di protezione dalle minacce di posta elettronica di Microsoft filtrano la posta elettronica in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="261c9-235">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="261c9-236">Fornisce informazioni dettagliate sul conteggio totale della posta elettronica e sul modo in cui le funzionalità di protezione dalle minacce configurate, tra cui protezione perimetrale, antimalware, anti-phishing, protezione da posta indesiderata e anti-spoofing influiscono su questo conteggio.</span><span class="sxs-lookup"><span data-stu-id="261c9-236">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="261c9-237">Se si fa clic sulla scheda **Imbuto,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-237">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="261c9-238">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="261c9-238">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="261c9-239">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="261c9-239">**Direction**:</span></span>

  - <span data-ttu-id="261c9-240">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="261c9-240">**Inbound**</span></span>
  - <span data-ttu-id="261c9-241">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="261c9-241">**Outbound**</span></span>
  - <span data-ttu-id="261c9-242">**Intra-org:** questo conteggio è per i messaggi inviati all'interno di un tenant; Ad esempio, il mittente abc@domain.com inviato al destinatario xyz@domain.com (conteggiato separatamente da Inbound e Outbound).</span><span class="sxs-lookup"><span data-stu-id="261c9-242">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="261c9-243">La visualizzazione aggregata e la visualizzazione tabella dati consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="261c9-243">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="261c9-244">Se si fa **clic su Filtro**, è possibile filtrare sia il grafico che la tabella dati.</span><span class="sxs-lookup"><span data-stu-id="261c9-244">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="261c9-245">Questo grafico mostra il numero di messaggi di posta elettronica organizzati per:</span><span class="sxs-lookup"><span data-stu-id="261c9-245">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="261c9-246">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="261c9-246">**Total email**</span></span>
- <span data-ttu-id="261c9-247">**Posta elettronica dopo la protezione edge**</span><span class="sxs-lookup"><span data-stu-id="261c9-247">**Email after edge protection**</span></span>
- <span data-ttu-id="261c9-248">**Regola di posta elettronica dopo il trasporto** (regola del flusso di posta)</span><span class="sxs-lookup"><span data-stu-id="261c9-248">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="261c9-249">**Posta elettronica dopo antimalware, reputazione file, blocco del tipo di file**</span><span class="sxs-lookup"><span data-stu-id="261c9-249">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="261c9-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="261c9-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="261c9-251">**Posta elettronica dopo la posta indesiderata, filtro posta in blocco**</span><span class="sxs-lookup"><span data-stu-id="261c9-251">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="261c9-252">**Posta elettronica dopo la rappresentazione di utenti e domini**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="261c9-252">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="261c9-253">**Posta elettronica dopo la detonazione di file e URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="261c9-253">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="261c9-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span><span class="sxs-lookup"><span data-stu-id="261c9-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="261c9-255"><sup>\*</sup>Defender solo per Office 365</span><span class="sxs-lookup"><span data-stu-id="261c9-255"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="261c9-256">Per visualizzare il messaggio di posta elettronica filtrato da EOP o Defender per Office 365 separatamente, fare clic sul valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="261c9-256">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="261c9-257">La tabella dei dati contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="261c9-257">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="261c9-258">**Data**</span><span class="sxs-lookup"><span data-stu-id="261c9-258">**Date**</span></span>
- <span data-ttu-id="261c9-259">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="261c9-259">**Total email**</span></span>
- <span data-ttu-id="261c9-260">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="261c9-260">**Edge protection**</span></span>
- <span data-ttu-id="261c9-261">**Antimalware, reputazione file, blocco del tipo di file**:</span><span class="sxs-lookup"><span data-stu-id="261c9-261">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="261c9-262">**Reputazione file:** messaggi filtrati a causa dell'identificazione di un file allegato da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="261c9-262">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="261c9-263">**Blocco del tipo di** file : Messaggi filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="261c9-263">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="261c9-264">**Anti-phish, reputazione URL, rappresentazione del marchio, anti-spoofing**:</span><span class="sxs-lookup"><span data-stu-id="261c9-264">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="261c9-265">**Reputazione URL**: Messaggi filtrati a causa dell'identificazione dell'URL da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="261c9-265">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="261c9-266">**Rappresentazione del marchio**: messaggi filtrati a causa del messaggio proveniente da mittenti noti che rappresentano il marchio.</span><span class="sxs-lookup"><span data-stu-id="261c9-266">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="261c9-267">**Anti-spoof**: messaggi filtrati a causa del tentativo di spoofing di un dominio a cui appartiene il destinatario o di un dominio di cui il mittente non è proprietario.</span><span class="sxs-lookup"><span data-stu-id="261c9-267">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="261c9-268">**Protezione da posta indesiderata, filtro posta in blocco**:</span><span class="sxs-lookup"><span data-stu-id="261c9-268">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="261c9-269">**Filtro posta in blocco**: Messaggi filtrati in base alla soglia del livello di reclamo in blocco (BCL) in un criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="261c9-269">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="261c9-270">**Rappresentazione utente e dominio (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="261c9-270">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="261c9-271">**Rappresentazione utente**: messaggi filtrati a causa di un tentativo di rappresentazione di un utente (mittente del messaggio) definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="261c9-271">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="261c9-272">**Rappresentazione di dominio**: messaggi filtrati a causa di un tentativo di rappresentare un dominio definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="261c9-272">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="261c9-273">**Detonazione di file e URL (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="261c9-273">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="261c9-274">**Detonazione file:** messaggi filtrati da un criterio Safe allegati.</span><span class="sxs-lookup"><span data-stu-id="261c9-274">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="261c9-275">**Detonazione URL:** messaggio filtrato in base a un Safe dei collegamenti.</span><span class="sxs-lookup"><span data-stu-id="261c9-275">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="261c9-276">**Protezione post-recapito e ZAP (ATP) o ZAP (EOP):** eliminazione automatica a zero ore (ZAP) per malware, posta indesiderata e phishing.</span><span class="sxs-lookup"><span data-stu-id="261c9-276">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="261c9-277">Se si seleziona una riga nella tabella dati, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="261c9-277">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="261c9-278">Esportare dalla visualizzazione Imbuto</span><span class="sxs-lookup"><span data-stu-id="261c9-278">Export from Funnel view</span></span>

<span data-ttu-id="261c9-279">Dopo aver fatto **clic su** Esporta **in Opzioni,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-279">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="261c9-280">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="261c9-280">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="261c9-281">**Dettagli (con dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="261c9-281">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="261c9-282">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="261c9-282">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="261c9-283">I dati per i filtri correnti verranno esportati in un .csv file.</span><span class="sxs-lookup"><span data-stu-id="261c9-283">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="261c9-284">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="261c9-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="261c9-285">Se i dati contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="261c9-285">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione Imbuto nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="261c9-287">Visualizzazione tecnica per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="261c9-287">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="261c9-288">La **visualizzazione Tech** è simile alla visualizzazione **Imbuto,** fornendo dettagli più dettagliati per le funzionalità di protezione dalle minacce configurate.</span><span class="sxs-lookup"><span data-stu-id="261c9-288">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="261c9-289">Dal grafico è possibile vedere come i messaggi vengono categorizzati nelle diverse fasi della protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="261c9-289">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="261c9-290">Se si fa clic **sulla scheda Visualizzazione tecnica,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-290">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="261c9-291">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="261c9-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="261c9-292">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="261c9-292">**Direction**:</span></span>

  - <span data-ttu-id="261c9-293">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="261c9-293">**Inbound**</span></span>
  - <span data-ttu-id="261c9-294">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="261c9-294">**Outbound**</span></span>
  - <span data-ttu-id="261c9-295">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="261c9-295">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="261c9-296">mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da in ingresso e in uscita)</span><span class="sxs-lookup"><span data-stu-id="261c9-296">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="261c9-297">La visualizzazione aggregata e la visualizzazione tabella dati consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="261c9-297">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="261c9-298">Se si fa **clic su Filtro**, è possibile filtrare sia il grafico che la tabella dati.</span><span class="sxs-lookup"><span data-stu-id="261c9-298">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="261c9-299">Questo grafico mostra i messaggi organizzati nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-299">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="261c9-300">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="261c9-300">**Total email**</span></span>
- <span data-ttu-id="261c9-301">**Edge allow** e **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="261c9-301">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="261c9-302">**Regola di trasporto consentita** **e regola di trasporto filtrata** (regole del flusso di posta)</span><span class="sxs-lookup"><span data-stu-id="261c9-302">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="261c9-303">**Non malware,** **Safe allegati e** rilevamento motore <sup>\*</sup> **antimalware**</span><span class="sxs-lookup"><span data-stu-id="261c9-303">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="261c9-304">**Not phish,** **DMARC failure,** **Impersonation detection,** <sup>\*</sup> Spoof **detection** e **Phish detection**</span><span class="sxs-lookup"><span data-stu-id="261c9-304">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="261c9-305">**Nessun rilevamento con detonazione URL e** **rilevamento detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="261c9-305">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="261c9-306">**Non posta indesiderata** e  **posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="261c9-306">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="261c9-307">**Posta elettronica non dannosa,** **rilevamento Safe** <sup>\*</sup> collegamenti e **ZAP**</span><span class="sxs-lookup"><span data-stu-id="261c9-307">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="261c9-308"><sup>\*</sup>Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="261c9-308"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="261c9-309">Quando si passa il mouse su una categoria nel grafico, è possibile visualizzare il numero di messaggi in tale categoria.</span><span class="sxs-lookup"><span data-stu-id="261c9-309">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="261c9-310">La tabella dei dati contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="261c9-310">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="261c9-311">**Data**</span><span class="sxs-lookup"><span data-stu-id="261c9-311">**Date**</span></span>
- <span data-ttu-id="261c9-312">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="261c9-312">**Total email**</span></span>
- <span data-ttu-id="261c9-313">**Edge filtrato**</span><span class="sxs-lookup"><span data-stu-id="261c9-313">**Edge filtered**</span></span>
- <span data-ttu-id="261c9-314">**Messaggi delle regole**: Messaggi filtrati a causa delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="261c9-314">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="261c9-315">**Motore antimalware**, **Safe allegati** <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="261c9-315">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="261c9-316">**DMARC, impersonation,** <sup>\*</sup> **spoof,** **phish filtered**:</span><span class="sxs-lookup"><span data-stu-id="261c9-316">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="261c9-317">**DMARC**: Messaggi filtrati a causa dell'errore del messaggio nel controllo di autenticazione DMARC.</span><span class="sxs-lookup"><span data-stu-id="261c9-317">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="261c9-318">**Rilevamento detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="261c9-318">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="261c9-319">**Protezione da posta indesiderata filtrata**</span><span class="sxs-lookup"><span data-stu-id="261c9-319">**Anti-spam filtered**</span></span>
- <span data-ttu-id="261c9-320">**ZAP rimosso**</span><span class="sxs-lookup"><span data-stu-id="261c9-320">**ZAP removed**</span></span>
- <span data-ttu-id="261c9-321">**Rilevamento da Safe collegamenti**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="261c9-321">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="261c9-322"><sup>\*</sup>Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="261c9-322"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="261c9-323">Se si seleziona una riga nella tabella dati, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="261c9-323">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="261c9-324">Esportare da tech view</span><span class="sxs-lookup"><span data-stu-id="261c9-324">Export from Tech view</span></span>

<span data-ttu-id="261c9-325">Facendo clic **su Esporta,** in **Opzioni** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-325">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="261c9-326">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="261c9-326">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="261c9-327">**Dettagli (con dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="261c9-327">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="261c9-328">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="261c9-328">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="261c9-329">I dati per i filtri correnti verranno esportati in un .csv file.</span><span class="sxs-lookup"><span data-stu-id="261c9-329">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="261c9-330">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="261c9-330">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="261c9-331">Se i dati contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="261c9-331">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione tecnica nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="261c9-333">Report rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="261c9-333">Malware detections report</span></span>

<span data-ttu-id="261c9-334">Il **report Rilevamenti malware** mostra informazioni sui rilevamenti di malware nei messaggi di posta elettronica in arrivo e in uscita (malware rilevato da Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="261c9-334">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="261c9-335">Per ulteriori informazioni sulla protezione da malware in EOP, vedere [Protezione antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="261c9-335">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="261c9-336">Il filtro di visualizzazione aggregata consente 90 giorni, mentre il filtro della tabella dei dettagli consente solo 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="261c9-336">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="261c9-337">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="261c9-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="261c9-338">In **Malware rilevato nella posta elettronica** fare clic su Visualizza **dettagli.**</span><span class="sxs-lookup"><span data-stu-id="261c9-338">On **Malware detected in email**, click **View details**.</span></span> <span data-ttu-id="261c9-339">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="261c9-339">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Rilevamenti di malware nel widget di posta elettronica nella pagina & report di collaborazione](../../media/malware-detections-widget.png)

<span data-ttu-id="261c9-341">Dopo aver fatto **clic su Visualizza dettagli,** è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic **su Filtro** e selezionando:</span><span class="sxs-lookup"><span data-stu-id="261c9-341">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting:</span></span>

- <span data-ttu-id="261c9-342">**Date**: **Data di inizio** e Data **fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-342">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="261c9-343">**Direzione**: **In ingresso** e **In uscita**</span><span class="sxs-lookup"><span data-stu-id="261c9-343">**Direction**: **Inbound** and **Outbound**</span></span>

![Visualizzazione report nel report Rilevamento malware nei messaggi di posta elettronica](../../media/malware-detections-report-view.png)

<span data-ttu-id="261c9-345">Nella tabella dei dettagli sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-345">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="261c9-346">**Data**</span><span class="sxs-lookup"><span data-stu-id="261c9-346">**Date**</span></span>
- <span data-ttu-id="261c9-347">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="261c9-347">**Sender address**</span></span>
- <span data-ttu-id="261c9-348">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="261c9-348">**Recipient address**</span></span>
- <span data-ttu-id="261c9-349">**ID messaggio**: Disponibile nel **campo di intestazione Message-ID** nell'intestazione del messaggio e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="261c9-349">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="261c9-350">Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="261c9-350">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="261c9-351">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="261c9-351">**Subject**</span></span>
- <span data-ttu-id="261c9-352">**Filename**</span><span class="sxs-lookup"><span data-stu-id="261c9-352">**Filename**</span></span>
- <span data-ttu-id="261c9-353">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="261c9-353">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="261c9-354">Rapporto latenza della posta</span><span class="sxs-lookup"><span data-stu-id="261c9-354">Mail latency report</span></span>

<span data-ttu-id="261c9-355">Il **report Latenza della posta** in Defender per Office 365 contiene informazioni sulla latenza di recapito e detonazione della posta riscontrata all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="261c9-355">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="261c9-356">Per ulteriori informazioni, vedere [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="261c9-356">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="261c9-357">Report sui rilevamenti della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="261c9-357">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="261c9-358">Il **report Rilevamenti posta** indesiderata verrà visualizzato il 30 giugno 2021.</span><span class="sxs-lookup"><span data-stu-id="261c9-358">The **Spam detections report** will go away on June 30, 2021.</span></span> <span data-ttu-id="261c9-359">Le stesse informazioni sono disponibili nella relazione [sullo stato di Threat Protection.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="261c9-359">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="261c9-360">Report rilevamenti di spoofing</span><span class="sxs-lookup"><span data-stu-id="261c9-360">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="261c9-361">Il report dei rilevamenti di spoofing migliorato, come descritto in questo articolo, è in Anteprima, è soggetto a modifiche e non è disponibile in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="261c9-361">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="261c9-362">La versione precedente del report mostra solo **Posta buona** e Posta indesiderata rilevata come **posta indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="261c9-362">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="261c9-363">Il **report Rilevamenti di** spoofing mostra informazioni sui messaggi bloccati o consentiti a causa dello spoofing.</span><span class="sxs-lookup"><span data-stu-id="261c9-363">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="261c9-364">Per ulteriori informazioni sullo spoofing, vedere [Protezione anti-spoofing in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="261c9-364">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="261c9-365">La visualizzazione aggregata del report consente 45 giorni di filtro, mentre la visualizzazione dettagli consente solo <sup>\*</sup> dieci giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="261c9-365">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="261c9-366"><sup>\*</sup> Infine, sarà possibile utilizzare fino a 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="261c9-366"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="261c9-367">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="261c9-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="261c9-368">In **Rilevamenti spoofing** fare clic **su Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="261c9-368">On **Spoof detections**, click **View details**.</span></span> <span data-ttu-id="261c9-369">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="261c9-369">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget Rilevamenti di spoofing nella pagina Report & di collaborazione tramite posta elettronica](../../media/spoof-detections-widget.png)

<span data-ttu-id="261c9-371">Quando si passa il mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti messaggi falsificati sono stati rilevati e perché.</span><span class="sxs-lookup"><span data-stu-id="261c9-371">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="261c9-372">Dopo aver fatto **clic su Visualizza dettagli,** è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-372">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="261c9-373">**Date**: **Data di inizio** e Data **fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-373">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="261c9-374">**Risultato**:</span><span class="sxs-lookup"><span data-stu-id="261c9-374">**Result**:</span></span>
  - <span data-ttu-id="261c9-375">**Pass**</span><span class="sxs-lookup"><span data-stu-id="261c9-375">**Pass**</span></span>
  - <span data-ttu-id="261c9-376">**Fail**</span><span class="sxs-lookup"><span data-stu-id="261c9-376">**Fail**</span></span>
  - <span data-ttu-id="261c9-377">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="261c9-377">**SoftPass**</span></span>
  - <span data-ttu-id="261c9-378">**Nessuna**</span><span class="sxs-lookup"><span data-stu-id="261c9-378">**None**</span></span>
  - <span data-ttu-id="261c9-379">**Altro**</span><span class="sxs-lookup"><span data-stu-id="261c9-379">**Other**</span></span>
- <span data-ttu-id="261c9-380">**Tipo spoof**: **interno** ed **esterno**</span><span class="sxs-lookup"><span data-stu-id="261c9-380">**Spoof type**: **Internal** and **External**</span></span>

![Pagina di report di posta contraffatta nel portale Microsoft 365 Defender posta](../../media/spoof-detections-report-page.png)

<span data-ttu-id="261c9-382">Nella tabella sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-382">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="261c9-383">**Data**</span><span class="sxs-lookup"><span data-stu-id="261c9-383">**Date**</span></span>
- <span data-ttu-id="261c9-384">**Utente contraffatto**</span><span class="sxs-lookup"><span data-stu-id="261c9-384">**Spoofed user**</span></span>
- <span data-ttu-id="261c9-385">**Infrastruttura di invio**</span><span class="sxs-lookup"><span data-stu-id="261c9-385">**Sending infrastructure**</span></span>
- <span data-ttu-id="261c9-386">**Tipo spoofing**</span><span class="sxs-lookup"><span data-stu-id="261c9-386">**Spoof type**</span></span>
- <span data-ttu-id="261c9-387">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="261c9-387">**Result**</span></span>
- <span data-ttu-id="261c9-388">**Codice risultato**</span><span class="sxs-lookup"><span data-stu-id="261c9-388">**Result code**</span></span>
- <span data-ttu-id="261c9-389">**SPF**</span><span class="sxs-lookup"><span data-stu-id="261c9-389">**SPF**</span></span>
- <span data-ttu-id="261c9-390">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="261c9-390">**DKIM**</span></span>
- <span data-ttu-id="261c9-391">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="261c9-391">**DMARC**</span></span>
- <span data-ttu-id="261c9-392">**Conteggio messaggi**</span><span class="sxs-lookup"><span data-stu-id="261c9-392">**Message count**</span></span>

<span data-ttu-id="261c9-393">Per ulteriori informazioni sui codici dei risultati dell'autenticazione composita, vedere Intestazioni dei messaggi di posta indesiderata [in Microsoft 365](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-393">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="261c9-394">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="261c9-394">Threat protection status report</span></span>

<span data-ttu-id="261c9-395">La **relazione sullo stato di Protezione** dalle minacce è disponibile sia in EOP che in Defender per Office 365; Tuttavia, i report contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="261c9-395">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="261c9-396">Ad esempio, i clienti di EOP possono visualizzare le informazioni sul malware rilevato nella posta elettronica, ma non informazioni sui file dannosi rilevati dagli allegati Safe per [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)e Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="261c9-396">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="261c9-397">Il report fornisce il conteggio dei messaggi di posta elettronica con contenuto dannoso, ad esempio file o indirizzi di siti Web (URL) bloccati dal motore antimalware, eliminazione automatica a zero ore [(ZAP)](zero-hour-auto-purge.md)e Defender per funzionalità di Office 365 come collegamenti [di Safe,](safe-links.md) [allegati Safe](safe-attachments.md)e funzionalità di protezione dalla rappresentazione nei criteri [anti-phishing.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="261c9-397">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="261c9-398">È possibile utilizzare queste informazioni per identificare le tendenze o determinare se i criteri dell'organizzazione devono essere rettificati.</span><span class="sxs-lookup"><span data-stu-id="261c9-398">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="261c9-399">**Nota:** è importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="261c9-399">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="261c9-400">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="261c9-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="261c9-401">In **Stato protezione dalle minacce** fare clic su Visualizza **dettagli.**</span><span class="sxs-lookup"><span data-stu-id="261c9-401">On **Threat protection status**, click **View details**.</span></span> <span data-ttu-id="261c9-402">Per passare direttamente al report, aprire uno degli URL seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-402">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="261c9-403">Defender per Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="261c9-403">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="261c9-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="261c9-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Widget Stato protezione dalle minacce nella pagina Report di collaborazione & posta elettronica](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="261c9-406">Per impostazione predefinita, dopo aver fatto clic **su Visualizza dettagli,** il grafico mostra i dati degli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="261c9-406">By default, after you click **View details**, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="261c9-407">Se si fa **clic su Filtro**, è possibile selezionare un intervallo di date di 90 giorni (le sottoscrizioni di valutazione potrebbero essere limitate a 30 giorni).</span><span class="sxs-lookup"><span data-stu-id="261c9-407">If you click **Filter**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="261c9-408">La tabella dei dettagli consente il filtro per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="261c9-408">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="261c9-409">Le visualizzazioni disponibili sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="261c9-409">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="261c9-410">Visualizzare i dati per panoramica</span><span class="sxs-lookup"><span data-stu-id="261c9-410">View data by Overview</span></span>

![Visualizzazione panoramica nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="261c9-412">Nella visualizzazione **Visualizza dati per panoramica** vengono visualizzate le seguenti informazioni di rilevamento nel grafico:</span><span class="sxs-lookup"><span data-stu-id="261c9-412">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="261c9-413">**Malware di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="261c9-413">**Email malware**</span></span>
- <span data-ttu-id="261c9-414">**Phish di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="261c9-414">**Email phish**</span></span>
- <span data-ttu-id="261c9-415">**Malware contenuto**</span><span class="sxs-lookup"><span data-stu-id="261c9-415">**Content malware**</span></span>

<span data-ttu-id="261c9-416">Sotto il grafico non è disponibile alcuna tabella dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="261c9-416">No details table is available below the chart.</span></span>

<span data-ttu-id="261c9-417">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-417">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="261c9-418">**Date**: **Data di inizio** e Data **fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-418">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="261c9-419">**Rilevamento**: **malware della posta** elettronica, **e-mail phish** o **malware contenuto**</span><span class="sxs-lookup"><span data-stu-id="261c9-419">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="261c9-420">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="261c9-420">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="261c9-421">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="261c9-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="261c9-422">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="261c9-423">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="261c9-423">**Direction**</span></span>
- <span data-ttu-id="261c9-424">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="261c9-424">**Domain**</span></span>
- <span data-ttu-id="261c9-425">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="261c9-425">**Policy type**</span></span>

<span data-ttu-id="261c9-426">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="261c9-426">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="261c9-427">Visualizzare i dati tramite Analisi \> e-mail e scomposizione grafico per tecnologia di rilevamento</span><span class="sxs-lookup"><span data-stu-id="261c9-427">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Visualizzazione della tecnologia di rilevamento per la posta elettronica di phishing nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="261c9-429">Nella visualizzazione **Visualizza dati per \> e-mail phish** e **grafico per** tecnologia di rilevamento, nel grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="261c9-430">**Reputazione url dannosa:** <sup>\*</sup> reputazione url dannoso generata da Defender per Office 365 detonazioni in altri Microsoft 365 clienti.</span><span class="sxs-lookup"><span data-stu-id="261c9-430">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="261c9-431">**Filtro avanzato:** segnali di phishing basati sull'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="261c9-431">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="261c9-432">**Filtro generale**: Segnali di phishing basati sulle regole degli analisti.</span><span class="sxs-lookup"><span data-stu-id="261c9-432">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="261c9-433">**Spoofing all'interno dell'organizzazione:** il mittente sta tentando di eseguire lo spoofing del dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="261c9-433">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="261c9-434">**Spoofing del dominio esterno:** il mittente sta tentando di eseguire lo spoofing di un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="261c9-434">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="261c9-435">**Spoof DMARC:** errore di autenticazione DMARC nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="261c9-435">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="261c9-436">**Marchio di rappresentazione**: Rappresentazione di marchi noti in base ai mittenti.</span><span class="sxs-lookup"><span data-stu-id="261c9-436">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="261c9-437">**Rilevamento dell'analisi mista**</span><span class="sxs-lookup"><span data-stu-id="261c9-437">**Mixed analysis detection**</span></span>
- <span data-ttu-id="261c9-438">**Reputazione file**</span><span class="sxs-lookup"><span data-stu-id="261c9-438">**File reputation**</span></span>
- <span data-ttu-id="261c9-439">**Corrispondenza delle impronte digitali**</span><span class="sxs-lookup"><span data-stu-id="261c9-439">**Fingerprint matching**</span></span>
- <span data-ttu-id="261c9-440">**Reputazione detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="261c9-440">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="261c9-441">**Detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="261c9-441">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="261c9-442">**Utente di rappresentazione**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="261c9-442">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="261c9-443">**Dominio di rappresentazione** <sup>\*</sup> : Rappresentazione dei domini che il cliente possiede o definisce.</span><span class="sxs-lookup"><span data-stu-id="261c9-443">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="261c9-444">**Rappresentazione dell'intelligence delle** <sup>\*</sup> cassette postali : Rappresentazione degli utenti definiti dall'amministratore o appresi tramite l'intelligence delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="261c9-444">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="261c9-445">**Detonazione file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="261c9-445">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="261c9-446">**Campagna**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="261c9-446">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="261c9-447">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-447">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="261c9-448">**Data**</span><span class="sxs-lookup"><span data-stu-id="261c9-448">**Date**</span></span>
- <span data-ttu-id="261c9-449">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="261c9-449">**Subject**</span></span>
- <span data-ttu-id="261c9-450">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="261c9-450">**Sender**</span></span>
- <span data-ttu-id="261c9-451">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="261c9-451">**Recipients**</span></span>
- <span data-ttu-id="261c9-452">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="261c9-452">**Detected by**</span></span>
- <span data-ttu-id="261c9-453">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="261c9-453">**Delivery Status**</span></span>
- <span data-ttu-id="261c9-454">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="261c9-454">**Source of Compromise**</span></span>
- <span data-ttu-id="261c9-455">**Tag**</span><span class="sxs-lookup"><span data-stu-id="261c9-455">**Tags**</span></span>

<span data-ttu-id="261c9-456">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-456">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="261c9-457">**Date**: **Data di inizio** e Data **fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-457">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="261c9-458">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="261c9-458">**Detection**</span></span>
- <span data-ttu-id="261c9-459">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="261c9-459">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="261c9-460">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="261c9-460">**Direction**</span></span>
- <span data-ttu-id="261c9-461">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="261c9-461">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="261c9-462">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-462">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="261c9-463">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="261c9-463">**Domain**</span></span>
- <span data-ttu-id="261c9-464">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="261c9-464">**Policy type**</span></span>
- <span data-ttu-id="261c9-465">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="261c9-465">**Policy name** (details table only)</span></span>
- <span data-ttu-id="261c9-466">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="261c9-466">**Recipients**</span></span>

<span data-ttu-id="261c9-467">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="261c9-467">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="261c9-468">Visualizzare i dati tramite malware \> e-mail e scomposizione grafico per tecnologia di rilevamento</span><span class="sxs-lookup"><span data-stu-id="261c9-468">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Visualizzazione della tecnologia di rilevamento per il malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="261c9-470">Nella visualizzazione **Visualizza dati per \> malware** e-mail e **grafico per** tecnologia di rilevamento, nel grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-470">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="261c9-471">**Detonazione file:** <sup>\*</sup> rilevamento da parte Safe allegati.</span><span class="sxs-lookup"><span data-stu-id="261c9-471">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="261c9-472">**Reputazione detonazione file:** tutta la reputazione dei file dannosi generata da Defender per Office 365 <sup>\*</sup> detonazioni.</span><span class="sxs-lookup"><span data-stu-id="261c9-472">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="261c9-473">**Reputazione file**</span><span class="sxs-lookup"><span data-stu-id="261c9-473">**File reputation**</span></span>
- <span data-ttu-id="261c9-474">**Motore antimalware:** <sup>\*</sup> rilevamento da motori antimalware.</span><span class="sxs-lookup"><span data-stu-id="261c9-474">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="261c9-475">**Blocco del tipo di file dei** criteri antimalware: si tratta di messaggi di posta elettronica filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="261c9-475">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="261c9-476">**REPUTAZIONE URL dannosa**</span><span class="sxs-lookup"><span data-stu-id="261c9-476">**URL malicious reputation**</span></span>
- <span data-ttu-id="261c9-477">**Detonazione URL**</span><span class="sxs-lookup"><span data-stu-id="261c9-477">**URL detonation**</span></span>
- <span data-ttu-id="261c9-478">**Reputazione detonazione URL**</span><span class="sxs-lookup"><span data-stu-id="261c9-478">**URL detonation reputation**</span></span>
- <span data-ttu-id="261c9-479">**Campagna**</span><span class="sxs-lookup"><span data-stu-id="261c9-479">**Campaign**</span></span>

<span data-ttu-id="261c9-480">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-480">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="261c9-481">**Data**</span><span class="sxs-lookup"><span data-stu-id="261c9-481">**Date**</span></span>
- <span data-ttu-id="261c9-482">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="261c9-482">**Subject**</span></span>
- <span data-ttu-id="261c9-483">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="261c9-483">**Sender**</span></span>
- <span data-ttu-id="261c9-484">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="261c9-484">**Recipients**</span></span>
- <span data-ttu-id="261c9-485">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="261c9-485">**Detected by**</span></span>
- <span data-ttu-id="261c9-486">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="261c9-486">**Delivery Status**</span></span>
- <span data-ttu-id="261c9-487">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="261c9-487">**Source of Compromise**</span></span>
- <span data-ttu-id="261c9-488">**Tag**</span><span class="sxs-lookup"><span data-stu-id="261c9-488">**Tags**</span></span>

<span data-ttu-id="261c9-489">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-489">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="261c9-490">**Date**: **Data di inizio** e Data **fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-490">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="261c9-491">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="261c9-491">**Detection**</span></span>
- <span data-ttu-id="261c9-492">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="261c9-492">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="261c9-493">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="261c9-493">**Direction**</span></span>
- <span data-ttu-id="261c9-494">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="261c9-494">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="261c9-495">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-495">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="261c9-496">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="261c9-496">**Domain**</span></span>
- <span data-ttu-id="261c9-497">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="261c9-497">**Policy type**</span></span>
- <span data-ttu-id="261c9-498">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="261c9-498">**Policy name** (details table only)</span></span>
- <span data-ttu-id="261c9-499">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="261c9-499">**Recipients**</span></span>

<span data-ttu-id="261c9-500">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="261c9-500">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="261c9-501">Suddivisione del grafico per tipo di criteri e Visualizzazione dei dati tramite e-mail Phish o \> Visualizzazione dei dati tramite malware di posta \> elettronica</span><span class="sxs-lookup"><span data-stu-id="261c9-501">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Visualizzazione del tipo di criterio per la posta elettronica di phishing o la posta elettronica malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="261c9-503">Nelle **visualizzazioni Scomposizione grafico** per tipo di criterio e Visualizza dati per posta elettronica **\> o** Visualizza dati tramite **\> malware** tramite posta elettronica, nei grafici vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-503">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="261c9-504">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="261c9-504">**Anti-malware**</span></span>
- <span data-ttu-id="261c9-505">**Safe Allegati**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="261c9-505">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="261c9-506">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="261c9-506">**Anti-phish**</span></span>
- <span data-ttu-id="261c9-507">**Protezione da posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="261c9-507">**Anti-spam**</span></span>
- <span data-ttu-id="261c9-508">**Regola del flusso di** posta (nota anche come regola di trasporto)</span><span class="sxs-lookup"><span data-stu-id="261c9-508">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="261c9-509">**Altri**</span><span class="sxs-lookup"><span data-stu-id="261c9-509">**Others**</span></span>

<span data-ttu-id="261c9-510">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-510">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="261c9-511">**Data**</span><span class="sxs-lookup"><span data-stu-id="261c9-511">**Date**</span></span>
- <span data-ttu-id="261c9-512">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="261c9-512">**Subject**</span></span>
- <span data-ttu-id="261c9-513">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="261c9-513">**Sender**</span></span>
- <span data-ttu-id="261c9-514">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="261c9-514">**Recipients**</span></span>
- <span data-ttu-id="261c9-515">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="261c9-515">**Detected by**</span></span>
- <span data-ttu-id="261c9-516">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="261c9-516">**Delivery Status**</span></span>
- <span data-ttu-id="261c9-517">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="261c9-517">**Source of Compromise**</span></span>
- <span data-ttu-id="261c9-518">**Tag**</span><span class="sxs-lookup"><span data-stu-id="261c9-518">**Tags**</span></span>

<span data-ttu-id="261c9-519">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-519">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="261c9-520">**Date**: **Data di inizio** e Data **fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-520">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="261c9-521">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="261c9-521">**Detection**</span></span>
- <span data-ttu-id="261c9-522">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="261c9-522">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="261c9-523">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="261c9-523">**Direction**</span></span>
- <span data-ttu-id="261c9-524">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="261c9-524">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="261c9-525">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-525">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="261c9-526">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="261c9-526">**Domain**</span></span>
- <span data-ttu-id="261c9-527">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="261c9-527">**Policy type**</span></span>
- <span data-ttu-id="261c9-528">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="261c9-528">**Policy name** (details table only)</span></span>
- <span data-ttu-id="261c9-529">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="261c9-529">**Recipients**</span></span>

<span data-ttu-id="261c9-530">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="261c9-530">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="261c9-531">Suddivisione del grafico per stato di recapito e Visualizzazione dei dati tramite e-mail Phish o \> Visualizzazione dei dati tramite malware di posta \> elettronica</span><span class="sxs-lookup"><span data-stu-id="261c9-531">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Visualizzazione dello stato del recapito per posta elettronica di phishing e posta elettronica malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="261c9-533">Nelle **visualizzazioni Scomposizione grafico** per stato recapito e Visualizza dati per posta elettronica **\> o** Visualizza dati tramite **\> malware** tramite posta elettronica, nei grafici vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-533">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="261c9-534">**Cassetta postale ospitata: Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="261c9-534">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="261c9-535">**Cassetta postale ospitata: Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="261c9-535">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="261c9-536">**Cassetta postale ospitata: cartella personalizzata**</span><span class="sxs-lookup"><span data-stu-id="261c9-536">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="261c9-537">**Cassetta postale ospitata: Elementi eliminati**</span><span class="sxs-lookup"><span data-stu-id="261c9-537">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="261c9-538">**Inoltrato**</span><span class="sxs-lookup"><span data-stu-id="261c9-538">**Forwarded**</span></span>
- <span data-ttu-id="261c9-539">**Server locale: recapitato**</span><span class="sxs-lookup"><span data-stu-id="261c9-539">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="261c9-540">**Quarantena**</span><span class="sxs-lookup"><span data-stu-id="261c9-540">**Quarantine**</span></span>
- <span data-ttu-id="261c9-541">**Recapito non riuscito**</span><span class="sxs-lookup"><span data-stu-id="261c9-541">**Delivery failed**</span></span>
- <span data-ttu-id="261c9-542">**Rilasciato**</span><span class="sxs-lookup"><span data-stu-id="261c9-542">**Dropped**</span></span>

<span data-ttu-id="261c9-543">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-543">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="261c9-544">**Data**</span><span class="sxs-lookup"><span data-stu-id="261c9-544">**Date**</span></span>
- <span data-ttu-id="261c9-545">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="261c9-545">**Subject**</span></span>
- <span data-ttu-id="261c9-546">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="261c9-546">**Sender**</span></span>
- <span data-ttu-id="261c9-547">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="261c9-547">**Recipients**</span></span>
- <span data-ttu-id="261c9-548">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="261c9-548">**Detected by**</span></span>
- <span data-ttu-id="261c9-549">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="261c9-549">**Delivery Status**</span></span>
- <span data-ttu-id="261c9-550">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="261c9-550">**Source of Compromise**</span></span>
- <span data-ttu-id="261c9-551">**Tag**</span><span class="sxs-lookup"><span data-stu-id="261c9-551">**Tags**</span></span>

<span data-ttu-id="261c9-552">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-552">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="261c9-553">**Date**: **Data di inizio** e Data **fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-553">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="261c9-554">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="261c9-554">**Detection**</span></span>
- <span data-ttu-id="261c9-555">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="261c9-555">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="261c9-556">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="261c9-556">**Direction**</span></span>
- <span data-ttu-id="261c9-557">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="261c9-557">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="261c9-558">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-558">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="261c9-559">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="261c9-559">**Domain**</span></span>
- <span data-ttu-id="261c9-560">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="261c9-560">**Policy type**</span></span>
- <span data-ttu-id="261c9-561">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="261c9-561">**Policy name** (details table only)</span></span>
- <span data-ttu-id="261c9-562">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="261c9-562">**Recipients**</span></span>

<span data-ttu-id="261c9-563">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="261c9-563">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="261c9-564">Visualizzare i dati in base al malware contenuto \></span><span class="sxs-lookup"><span data-stu-id="261c9-564">View data by Content \> Malware</span></span>

![Visualizzazione malware contenuto nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="261c9-566">Nella visualizzazione **Visualizzazione dati per \> malware** contenuto, nel grafico per Microsoft Defender per Office 365 organizzazioni:</span><span class="sxs-lookup"><span data-stu-id="261c9-566">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="261c9-567">**Motore antimalware:** file dannosi rilevati in Sharepoint, OneDrive e Microsoft Teams dal rilevamento di [virus incorporato in Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-567">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="261c9-568">**Detonazione file:** file dannosi rilevati da Safe allegati per [SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-568">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="261c9-569">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-569">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="261c9-570">**Date**: **Data di inizio** e Data **fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-570">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="261c9-571">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="261c9-571">**Location**</span></span>
- <span data-ttu-id="261c9-572">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="261c9-572">**Detected by**</span></span>
- <span data-ttu-id="261c9-573">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="261c9-573">**Malware name**</span></span>

<span data-ttu-id="261c9-574">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="261c9-575">**Date**: **Data di inizio** e Data **fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-575">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="261c9-576">**Rilevamento:** **motore antimalware o** **detonazione file**</span><span class="sxs-lookup"><span data-stu-id="261c9-576">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="261c9-577">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="261c9-577">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="261c9-578">Visualizzare i dati per sostituzione di sistema</span><span class="sxs-lookup"><span data-stu-id="261c9-578">View data by System override</span></span>

![Visualizzazione sostituzione messaggio nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="261c9-580">Nella visualizzazione **Visualizza dati per sostituzione di** sistema, nel grafico vengono visualizzate le seguenti informazioni sul motivo dell'override:</span><span class="sxs-lookup"><span data-stu-id="261c9-580">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="261c9-581">**Ignora locale**</span><span class="sxs-lookup"><span data-stu-id="261c9-581">**On-premises skip**</span></span>
- <span data-ttu-id="261c9-582">**IP allow**</span><span class="sxs-lookup"><span data-stu-id="261c9-582">**IP allow**</span></span>
- <span data-ttu-id="261c9-583">**Exchange di trasporto della posta** elettronica (regola del flusso di posta)</span><span class="sxs-lookup"><span data-stu-id="261c9-583">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="261c9-584">**Mittenti consentiti dall'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="261c9-584">**Organization allowed senders**</span></span>
- <span data-ttu-id="261c9-585">**Domini consentiti dall'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="261c9-585">**Organization allowed domains**</span></span>
- <span data-ttu-id="261c9-586">**ZAP non abilitato**</span><span class="sxs-lookup"><span data-stu-id="261c9-586">**ZAP not enabled**</span></span>
- <span data-ttu-id="261c9-587">**Cartella Posta indesiderata non abilitata**</span><span class="sxs-lookup"><span data-stu-id="261c9-587">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="261c9-588">**Mittente Safe utente**</span><span class="sxs-lookup"><span data-stu-id="261c9-588">**User Safe Sender**</span></span>
- <span data-ttu-id="261c9-589">**Dominio Safe utente**</span><span class="sxs-lookup"><span data-stu-id="261c9-589">**User Safe Domain**</span></span>

<span data-ttu-id="261c9-590">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-590">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="261c9-591">**Data**</span><span class="sxs-lookup"><span data-stu-id="261c9-591">**Date**</span></span>
- <span data-ttu-id="261c9-592">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="261c9-592">**Subject**</span></span>
- <span data-ttu-id="261c9-593">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="261c9-593">**Sender**</span></span>
- <span data-ttu-id="261c9-594">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="261c9-594">**Recipients**</span></span>
- <span data-ttu-id="261c9-595">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="261c9-595">**Detected by**</span></span>
- <span data-ttu-id="261c9-596">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="261c9-596">**Delivery Status**</span></span>
- <span data-ttu-id="261c9-597">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="261c9-597">**Source of Compromise**</span></span>
- <span data-ttu-id="261c9-598">**Tag**</span><span class="sxs-lookup"><span data-stu-id="261c9-598">**Tags**</span></span>

<span data-ttu-id="261c9-599">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-599">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="261c9-600">**Date**: **Data di inizio** e Data **fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-600">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="261c9-601">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="261c9-601">**Detection**</span></span>
- <span data-ttu-id="261c9-602">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="261c9-602">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="261c9-603">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="261c9-603">**Direction**</span></span>
- <span data-ttu-id="261c9-604">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="261c9-604">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="261c9-605">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-605">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="261c9-606">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="261c9-606">**Domain**</span></span>
- <span data-ttu-id="261c9-607">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="261c9-607">**Policy type**</span></span>
- <span data-ttu-id="261c9-608">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="261c9-608">**Policy name** (details table only)</span></span>
- <span data-ttu-id="261c9-609">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="261c9-609">**Recipients**</span></span>

<span data-ttu-id="261c9-610">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="261c9-610">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="261c9-611"><sup>\*</sup>Defender solo per Office 365</span><span class="sxs-lookup"><span data-stu-id="261c9-611"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="261c9-612">Report principale sul malware</span><span class="sxs-lookup"><span data-stu-id="261c9-612">Top malware report</span></span>

<span data-ttu-id="261c9-613">Il **report Top malware** mostra i vari tipi di malware rilevati dalla protezione [antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="261c9-613">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="261c9-614">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="261c9-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="261c9-615">In **Malware principale** fare clic su Visualizza **dettagli.**</span><span class="sxs-lookup"><span data-stu-id="261c9-615">On **Top malware**, click **View details**.</span></span> <span data-ttu-id="261c9-616">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="261c9-616">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Widget malware principale nella pagina Report di collaborazione & posta elettronica](../../media/top-malware-report-widget.png)

<span data-ttu-id="261c9-618">Quando si passa il mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi rilevati come malware.</span><span class="sxs-lookup"><span data-stu-id="261c9-618">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="261c9-619">Dopo aver fatto **clic su Visualizza dettagli,** nella pagina del report verrà visualizzata una versione più grande del grafico a torta. La tabella dei dettagli sotto il grafico mostra le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-619">After you click **View details**, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="261c9-620">**Malware principale**</span><span class="sxs-lookup"><span data-stu-id="261c9-620">**Top malware**</span></span>
- <span data-ttu-id="261c9-621">**Numero**</span><span class="sxs-lookup"><span data-stu-id="261c9-621">**Count**</span></span>

<span data-ttu-id="261c9-622">Se si fa **clic su Filtro**, è possibile specificare un intervallo di date con Data **inizio** e **Data fine**.</span><span class="sxs-lookup"><span data-stu-id="261c9-622">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Visualizzazione dei report principali sul malware](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="261c9-624">Report di protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="261c9-624">URL threat protection report</span></span>

<span data-ttu-id="261c9-625">Il **report di protezione dalle minacce URL** è disponibile in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="261c9-625">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="261c9-626">Per ulteriori informazioni, vedere [Report di protezione dalle minacce URL](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="261c9-626">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="261c9-627">Rapporto messaggi segnalati dall'utente</span><span class="sxs-lookup"><span data-stu-id="261c9-627">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="261c9-628">Per il corretto funzionamento del rapporto **Messaggi segnalati** dall'utente, è necessario che la registrazione di controllo sia attivata per l'Microsoft 365 locale. </span><span class="sxs-lookup"><span data-stu-id="261c9-628">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="261c9-629">Questa operazione viene in genere eseguita da un utente a cui è assegnato il ruolo Log di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="261c9-629">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="261c9-630">Per ulteriori informazioni, vedere [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-630">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="261c9-631">Il **report Messaggi segnalati** dall'utente mostra informazioni sui messaggi di posta elettronica [](enable-the-report-message-add-in.md) segnalati dagli utenti come posta indesiderata, tentativi di phishing o buona posta utilizzando il componente aggiuntivo Segnala messaggio o Segnala [phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-631">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="261c9-632">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Rapporti Posta elettronica & collaborazione E-mail & rapporti di collaborazione \>  \>  \> **Messaggi segnalati dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="261c9-632">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span> <span data-ttu-id="261c9-633">In **Messaggi segnalati dall'utente** fare clic **su Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="261c9-633">On **User reported messages**, click **View details**.</span></span> <span data-ttu-id="261c9-634">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="261c9-634">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="261c9-635">Per passare agli [invii di amministratore](admin-submission.md)nel portale Microsoft 365 Defender, fare clic **su Vai a Invii.**</span><span class="sxs-lookup"><span data-stu-id="261c9-635">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget Messaggi segnalati dall'utente nella pagina Rapporti di collaborazione & posta elettronica](../../media/user-reported-messages-widget.png)

<span data-ttu-id="261c9-637">Dopo aver **fatto** clic su Visualizza dettagli, è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="261c9-637">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="261c9-638">**Data riportata**: **Ora inizio** **e Ora fine**</span><span class="sxs-lookup"><span data-stu-id="261c9-638">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="261c9-639">**Segnalato da**</span><span class="sxs-lookup"><span data-stu-id="261c9-639">**Reported by**</span></span>
- <span data-ttu-id="261c9-640">**Oggetto e-mail**</span><span class="sxs-lookup"><span data-stu-id="261c9-640">**Email subject**</span></span>
- <span data-ttu-id="261c9-641">**ID segnalato messaggio**</span><span class="sxs-lookup"><span data-stu-id="261c9-641">**Message reported ID**</span></span>
- <span data-ttu-id="261c9-642">**ID messaggio di rete**</span><span class="sxs-lookup"><span data-stu-id="261c9-642">**Network Message ID**</span></span>
- <span data-ttu-id="261c9-643">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="261c9-643">**Sender**</span></span>
- <span data-ttu-id="261c9-644">**Motivo segnalato**</span><span class="sxs-lookup"><span data-stu-id="261c9-644">**Reported reason**</span></span>
  - <span data-ttu-id="261c9-645">**Non indesiderato**</span><span class="sxs-lookup"><span data-stu-id="261c9-645">**Not junk**</span></span>
  - <span data-ttu-id="261c9-646">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="261c9-646">**Phish**</span></span>
  - <span data-ttu-id="261c9-647">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="261c9-647">**Spam**</span></span>
- <span data-ttu-id="261c9-648">**Simulazione phish**: **Sì** o **No**</span><span class="sxs-lookup"><span data-stu-id="261c9-648">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="261c9-649">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="261c9-649">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="261c9-650">Per raggruppare le voci, fare clic **su Gruppo** e selezionare uno dei valori seguenti nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="261c9-650">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="261c9-651">**Nessuna**</span><span class="sxs-lookup"><span data-stu-id="261c9-651">**None**</span></span>
- <span data-ttu-id="261c9-652">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="261c9-652">**Reason**</span></span>
- <span data-ttu-id="261c9-653">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="261c9-653">**Sender**</span></span>
- <span data-ttu-id="261c9-654">**Segnalato da**</span><span class="sxs-lookup"><span data-stu-id="261c9-654">**Reported by**</span></span>
- <span data-ttu-id="261c9-655">**Risultato dell'analisi**</span><span class="sxs-lookup"><span data-stu-id="261c9-655">**Rescan result**</span></span>
- <span data-ttu-id="261c9-656">**Simulazione phish**</span><span class="sxs-lookup"><span data-stu-id="261c9-656">**Phish simulation**</span></span>

![Rapporto messaggi segnalati dall'utente](../../media/user-reported-messages-report.png)

<span data-ttu-id="261c9-658">Nella tabella sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="261c9-658">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="261c9-659">**Oggetto e-mail**</span><span class="sxs-lookup"><span data-stu-id="261c9-659">**Email subject**</span></span>
- <span data-ttu-id="261c9-660">**Segnalato da**</span><span class="sxs-lookup"><span data-stu-id="261c9-660">**Reported by**</span></span>
- <span data-ttu-id="261c9-661">**Data riportata**</span><span class="sxs-lookup"><span data-stu-id="261c9-661">**Date reported**</span></span>
- <span data-ttu-id="261c9-662">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="261c9-662">**Sender**</span></span>
- <span data-ttu-id="261c9-663">**Motivo segnalato**</span><span class="sxs-lookup"><span data-stu-id="261c9-663">**Reported reason**</span></span>
- <span data-ttu-id="261c9-664">**Risultato dell'analisi**</span><span class="sxs-lookup"><span data-stu-id="261c9-664">**Rescan result**</span></span>
- <span data-ttu-id="261c9-665">**Tag**</span><span class="sxs-lookup"><span data-stu-id="261c9-665">**Tags**</span></span>

<span data-ttu-id="261c9-666">Per inviare un messaggio a Microsoft per l'analisi, selezionare la voce del messaggio dalla tabella, fare clic su Invia a **Microsoft** per l'analisi e quindi selezionare uno dei valori seguenti nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="261c9-666">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="261c9-667">**Segnala pulito**</span><span class="sxs-lookup"><span data-stu-id="261c9-667">**Report clean**</span></span>
- <span data-ttu-id="261c9-668">**Segnalare phishing**</span><span class="sxs-lookup"><span data-stu-id="261c9-668">**Report phishing**</span></span>
- <span data-ttu-id="261c9-669">**Segnalare malware**</span><span class="sxs-lookup"><span data-stu-id="261c9-669">**Report malware**</span></span>
- <span data-ttu-id="261c9-670">**Segnala posta indesiderata**'</span><span class="sxs-lookup"><span data-stu-id="261c9-670">**Report spam**'</span></span>
- <span data-ttu-id="261c9-671">**Attivare l'indagine** (Defender per Office 365)</span><span class="sxs-lookup"><span data-stu-id="261c9-671">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="261c9-672">Quali autorizzazioni sono necessarie per visualizzare questi report?</span><span class="sxs-lookup"><span data-stu-id="261c9-672">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="261c9-673">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel portale di Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="261c9-673">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="261c9-674">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="261c9-674">**Organization Management**</span></span>
- <span data-ttu-id="261c9-675">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="261c9-675">**Security Administrator**</span></span>
- <span data-ttu-id="261c9-676">**Lettore sicurezza**</span><span class="sxs-lookup"><span data-stu-id="261c9-676">**Security Reader**</span></span>
- <span data-ttu-id="261c9-677">**Lettore globale**</span><span class="sxs-lookup"><span data-stu-id="261c9-677">**Global Reader**</span></span>

<span data-ttu-id="261c9-678">Per ulteriori informazioni, vedere [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-678">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="261c9-679">**Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nel interfaccia di amministrazione di Microsoft 365 offre agli utenti le  autorizzazioni necessarie nel portale di Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="261c9-679">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="261c9-680">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="261c9-680">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="261c9-681">Cosa succede se i report non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="261c9-681">What if the reports aren't showing data?</span></span>

<span data-ttu-id="261c9-682">Se i dati nei report non vengono visualizzati, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="261c9-682">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="261c9-683">Per ulteriori informazioni, vedere [Protezione dalle minacce.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="261c9-683">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="261c9-684">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="261c9-684">Related topics</span></span>

[<span data-ttu-id="261c9-685">Protezione da posta indesiderata e antimalware in EOP</span><span class="sxs-lookup"><span data-stu-id="261c9-685">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="261c9-686">Report e informazioni dettagliate intelligenti nel portale Microsoft 365 Defender dati</span><span class="sxs-lookup"><span data-stu-id="261c9-686">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="261c9-687">Visualizzare i report del flusso di posta nel portale Microsoft 365 Defender posta</span><span class="sxs-lookup"><span data-stu-id="261c9-687">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="261c9-688">Visualizzare i report per Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="261c9-688">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
