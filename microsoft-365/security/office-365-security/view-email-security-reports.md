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
description: Gli amministratori possono imparare a trovare e usare i report di sicurezza della posta elettronica disponibili nel portale Microsoft 365 Defender posta elettronica.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ad90038ac818f9759768d0d00019393205b03f3
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083525"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="5fe0c-103">Visualizzare i report di sicurezza della posta elettronica nel portale Microsoft 365 Defender posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5fe0c-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5fe0c-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-104">**Applies to**</span></span>
- [<span data-ttu-id="5fe0c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5fe0c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5fe0c-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="5fe0c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5fe0c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fe0c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5fe0c-108">Nel portale di Microsoft 365 Defender è disponibile un'ampia gamma di report che consentono di verificare in che modo le funzionalità di sicurezza della posta elettronica, ad esempio la protezione da posta indesiderata, antimalware e crittografia in Microsoft 365, proteggono <https://security.microsoft.com> l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="5fe0c-109">Se si dispone [delle](#what-permissions-are-needed-to-view-these-reports)autorizzazioni necessarie, è possibile visualizzare questi  report nel portale di Microsoft 365 Defender andando a Rapporti e-mail & \> **collaborazione** \> **E-mail**& rapporti di collaborazione .</span><span class="sxs-lookup"><span data-stu-id="5fe0c-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5fe0c-110">Per passare direttamente alla pagina Rapporti di **collaborazione &** e-mail, aprire <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="5fe0c-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Pagina dei & di collaborazione tramite posta elettronica nel portale Microsoft 365 Defender posta elettronica](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="5fe0c-112">Alcuni dei report nella pagina Rapporti di **collaborazione &** e-mail richiedono Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="5fe0c-113">Per informazioni su questi report, vedere [View Defender for Office 365 reports in the Microsoft 365 Defender portal.](view-reports-for-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="5fe0c-114">I report correlati al flusso di posta sono ora disponibili nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="5fe0c-115">Per ulteriori informazioni su questi report, vedere [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="5fe0c-116">Report utenti compromessi</span><span class="sxs-lookup"><span data-stu-id="5fe0c-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="5fe0c-117">Questo report è disponibile nelle organizzazioni Microsoft 365 con Exchange Online cassette postali.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="5fe0c-118">Non è disponibile nelle organizzazioni autonome Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="5fe0c-119">Il **report Utenti compromessi** mostra il numero di  account  utente contrassegnati come sospetti o con restrizioni negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="5fe0c-120">Gli account in uno di questi stati sono problematici o addirittura compromessi.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="5fe0c-121">Con un uso frequente, è possibile utilizzare il report per individuare picchi e persino tendenze in account sospetti o con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="5fe0c-122">Per ulteriori informazioni sugli utenti compromessi, vedere [Risposta a un account di posta elettronica compromesso.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Utenti compromessi nella pagina Report & e-mail](../../media/compromised-users-report-widget.png)

<span data-ttu-id="5fe0c-124">La visualizzazione aggregata mostra i dati degli ultimi 90 giorni e la visualizzazione dettagli mostra i dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="5fe0c-125">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5fe0c-126">Nella pagina **Rapporti di &** e-mail individuare Utenti **compromessi** e quindi fare clic **su Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="5fe0c-127">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="5fe0c-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="5fe0c-128">Nella pagina **Utenti compromessi** è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="5fe0c-129">**Date (UTC)**: **Data di inizio** e Data di **fine**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="5fe0c-130">**Attività**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-130">**Activity**:</span></span>
  - <span data-ttu-id="5fe0c-131">**Sospetto:** l'account utente ha inviato messaggi di posta elettronica sospetti ed è a rischio di essere limitato a inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="5fe0c-132">**Con restrizioni**: all'account utente è stato limitato l'invio di posta elettronica a causa di modelli altamente sospetti.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="5fe0c-133">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![Visualizzazione report nel report Utenti compromessi](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="5fe0c-135">Nella tabella dei dettagli sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="5fe0c-136">**Ora creazione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-136">**Creation time**</span></span>
- <span data-ttu-id="5fe0c-137">**ID utente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-137">**User ID**</span></span>
- <span data-ttu-id="5fe0c-138">**Azione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="5fe0c-139">Exchange delle regole di trasporto</span><span class="sxs-lookup"><span data-stu-id="5fe0c-139">Exchange transport rule report</span></span>

<span data-ttu-id="5fe0c-140">Il **Exchange delle regole di trasporto** mostra l'effetto delle regole del flusso di posta (note anche come regole di trasporto) sui messaggi in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="5fe0c-141">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5fe0c-142">Nella pagina **Rapporti di &** e-mail individuare Exchange di **trasporto** e quindi fare clic su **Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="5fe0c-143">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="5fe0c-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Exchange della regola di trasporto nella pagina Rapporti di collaborazione & posta elettronica](../../media/transport-rule-report-widget.png)

<span data-ttu-id="5fe0c-145">Nella pagina **Exchange report delle regole di** trasporto, i grafici e i dati disponibili sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="5fe0c-146">Suddivisione del grafico per direzione</span><span class="sxs-lookup"><span data-stu-id="5fe0c-146">Chart breakdown by Direction</span></span>

![Visualizzazione direzione per Exchange regole di trasporto nel report Exchange regole di trasporto](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="5fe0c-148">Se si seleziona **Suddivisione grafico per direzione**, sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="5fe0c-149">**Visualizzare i dati Exchange regole di trasporto**:  Numero di messaggi **in** ingresso e in uscita interessati dalle regole del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="5fe0c-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="5fe0c-151">Nella tabella dei dettagli sotto il grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="5fe0c-152">**Data**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-152">**Date**</span></span>
- <span data-ttu-id="5fe0c-153">**Criterio DLP** (**Visualizza i dati solo per Exchange DLP)**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="5fe0c-154">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-154">**Transport rule**</span></span>
- <span data-ttu-id="5fe0c-155">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-155">**Subject**</span></span>
- <span data-ttu-id="5fe0c-156">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-156">**Sender address**</span></span>
- <span data-ttu-id="5fe0c-157">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-157">**Recipient address**</span></span>
- <span data-ttu-id="5fe0c-158">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-158">**Severity**</span></span>
- <span data-ttu-id="5fe0c-159">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-159">**Direction**</span></span>

<span data-ttu-id="5fe0c-160">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="5fe0c-161">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-162">**Direzione**: **In uscita** e **in ingresso**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="5fe0c-163">**Gravità**: **Gravità elevata,** **Gravità media** e **Gravità bassa**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="5fe0c-164">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="5fe0c-165">Suddivisione del grafico per gravità</span><span class="sxs-lookup"><span data-stu-id="5fe0c-165">Chart breakdown by Severity</span></span>

![Visualizzazione gravità per Exchange regole di trasporto nel report Exchange regole di trasporto](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="5fe0c-167">Se si seleziona **Scomposizione grafico per gravità**, sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="5fe0c-168">**Visualizzare i dati Exchange regole di trasporto**: Numero di messaggi Di gravità elevata, Gravità media e  **Gravità** bassa. </span><span class="sxs-lookup"><span data-stu-id="5fe0c-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="5fe0c-169">Il livello di gravità viene impostato come azione nella regola **(** Controlla questa regola con livello di gravità o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="5fe0c-170">Per ulteriori informazioni, vedere [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="5fe0c-171">**Visualizzare i dati** da DLP Exchange di trasporto : Numero di messaggi  di gravità **elevata,** gravità media e gravità bassa interessati dalle regole del flusso di posta DLP.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="5fe0c-172">Nella tabella dei dettagli sotto il grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="5fe0c-173">**Data**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-173">**Date**</span></span>
- <span data-ttu-id="5fe0c-174">**Criterio DLP** (**Visualizza i dati solo per Exchange DLP)**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="5fe0c-175">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-175">**Transport rule**</span></span>
- <span data-ttu-id="5fe0c-176">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-176">**Subject**</span></span>
- <span data-ttu-id="5fe0c-177">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-177">**Sender address**</span></span>
- <span data-ttu-id="5fe0c-178">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-178">**Recipient address**</span></span>
- <span data-ttu-id="5fe0c-179">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-179">**Severity**</span></span>
- <span data-ttu-id="5fe0c-180">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-180">**Direction**</span></span>

<span data-ttu-id="5fe0c-181">È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="5fe0c-182">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-183">**Direzione**: **In uscita** e **in ingresso**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="5fe0c-184">**Gravità**: **Gravità elevata,** **Gravità media** e **Gravità bassa**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="5fe0c-185">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="5fe0c-186">Rapporto di inoltro</span><span class="sxs-lookup"><span data-stu-id="5fe0c-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="5fe0c-187">Il **report di inoltro** è ora disponibile nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="5fe0c-188">Per ulteriori informazioni, vedere [Report messaggi inoltrati automaticamente nel nuovo interfaccia di amministrazione di Exchange.](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="5fe0c-189">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="5fe0c-189">Mailflow status report</span></span>

<span data-ttu-id="5fe0c-190">Il **rapporto** sullo stato del flusso di posta è un report intelligente che mostra informazioni sulla posta elettronica in arrivo e in uscita, sui rilevamenti di posta indesiderata, sul malware, sulla posta elettronica identificata come "buona" e sulle informazioni sulla posta elettronica consentita o bloccata sul perimetro.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="5fe0c-191">Questo è l'unico report che contiene informazioni sulla protezione perimetrale e mostra la quantità di posta elettronica bloccata prima di essere consentita al servizio per la valutazione da parte di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="5fe0c-192">È importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="5fe0c-193">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5fe0c-194">Nella pagina **E-mail & rapporti di collaborazione,** trovare Riepilogo stato **flusso** di posta e quindi fare clic **su Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="5fe0c-195">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="5fe0c-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Widget Riepilogo stato flusso di posta nella pagina Rapporti di collaborazione & posta elettronica](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="5fe0c-197">Visualizzazione tipo per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="5fe0c-197">Type view for the Mailflow status report</span></span>

![Visualizzazione tipo nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-type-view.png)

<span data-ttu-id="5fe0c-199">Nella pagina **Relazione sullo stato del flusso di posta** la scheda **Tipo** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-199">On the **Mailflow status report** page, the **Type** tab is selected by default.</span></span> <span data-ttu-id="5fe0c-200">Per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dei dettagli configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-200">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="5fe0c-201">**Data (UTC)** Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-201">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="5fe0c-202">**Direzione della posta**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-202">**Mail direction**:</span></span>
  - <span data-ttu-id="5fe0c-203">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-203">**Inbound**</span></span>
  - <span data-ttu-id="5fe0c-204">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-204">**Outbound**</span></span>
  - <span data-ttu-id="5fe0c-205">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="5fe0c-205">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="5fe0c-206">mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da **In ingresso** e **In uscita)**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-206">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="5fe0c-207">**Digitare**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-207">**Type**:</span></span>
  - <span data-ttu-id="5fe0c-208">**Posta buona**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-208">**Good mail**</span></span>
  - <span data-ttu-id="5fe0c-209">**Malware**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-209">**Malware**</span></span>
  - <span data-ttu-id="5fe0c-210">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-210">**Spam**</span></span>
  - <span data-ttu-id="5fe0c-211">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-211">**Edge protection**</span></span>
  - <span data-ttu-id="5fe0c-212">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-212">**Rule messages**</span></span>
  - <span data-ttu-id="5fe0c-213">**Posta di phishing**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-213">**Phishing email**</span></span>
- <span data-ttu-id="5fe0c-214">**Domain**: **All**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-214">**Domain**: **All**</span></span>

<span data-ttu-id="5fe0c-215">Il grafico è organizzato in base ai **valori Type.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-215">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="5fe0c-216">È possibile modificare questi filtri facendo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-216">You can change these filters by clicking **Filter**.</span></span>

<span data-ttu-id="5fe0c-217">Nella tabella dei dettagli sotto il grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-217">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="5fe0c-218">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-218">**Direction**</span></span>
- <span data-ttu-id="5fe0c-219">**Type**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-219">**Type**</span></span>
- <span data-ttu-id="5fe0c-220">**24 ore**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-220">**24 hours**</span></span>
- <span data-ttu-id="5fe0c-221">**3 giorni**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-221">**3 days**</span></span>
- <span data-ttu-id="5fe0c-222">**7 giorni**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-222">**7 days**</span></span>
- <span data-ttu-id="5fe0c-223">**15 giorni**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-223">**15 days**</span></span>
- <span data-ttu-id="5fe0c-224">**30 giorni**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-224">**30 days**</span></span>

<span data-ttu-id="5fe0c-225">Se si fa **clic su Scegli una categoria per ulteriori dettagli,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-225">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="5fe0c-226">**Posta elettronica di phishing**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-226">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="5fe0c-227">**Malware nella posta elettronica**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-227">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="5fe0c-228">**Rilevamenti di posta indesiderata:** questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-228">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="5fe0c-229">**Posta indesiderata bloccata** perimetrali : questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-229">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="5fe0c-230">Esportare dalla visualizzazione Tipo</span><span class="sxs-lookup"><span data-stu-id="5fe0c-230">Export from Type view</span></span>

<span data-ttu-id="5fe0c-231">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-231">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="5fe0c-232">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-232">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="5fe0c-233">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-233">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5fe0c-234">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-234">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="5fe0c-235">Visualizzazione della direzione per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="5fe0c-235">Direction view for the Mailflow status report</span></span>

![Visualizzazione direzione nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-direction-view.png)

<span data-ttu-id="5fe0c-237">Se si fa clic **sulla scheda Direzione,** vengono utilizzati gli stessi filtri predefiniti della **visualizzazione** Tipo.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-237">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="5fe0c-238">Il grafico è organizzato in base **ai valori di** Direzione.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-238">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="5fe0c-239">È possibile modificare questi filtri facendo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-239">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="5fe0c-240">Vengono utilizzati gli stessi filtri **della** visualizzazione Tipo.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-240">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="5fe0c-241">La tabella dei dettagli contiene le stesse informazioni della **visualizzazione Tipo.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-241">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="5fe0c-242">**L'opzione Scegliere una categoria per ulteriori dettagli** le selezioni e il comportamento disponibili sono gli stessi della visualizzazione **Tipo.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-242">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="5fe0c-243">Esportare dalla visualizzazione Direzione</span><span class="sxs-lookup"><span data-stu-id="5fe0c-243">Export from Direction view</span></span>

<span data-ttu-id="5fe0c-244">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-244">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="5fe0c-245">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-245">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="5fe0c-246">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-246">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5fe0c-247">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-247">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="5fe0c-248">Visualizzazione imbuto per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="5fe0c-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="5fe0c-249">La **visualizzazione Imbuto** mostra come le funzionalità di protezione dalle minacce di posta elettronica di Microsoft filtrano la posta elettronica in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="5fe0c-250">Fornisce informazioni dettagliate sul conteggio totale della posta elettronica e sul modo in cui le funzionalità di protezione dalle minacce configurate, tra cui protezione perimetrale, antimalware, anti-phishing, protezione da posta indesiderata e anti-spoofing influiscono su questo conteggio.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

![Visualizzazione Imbuto nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-funnel-view.png)

<span data-ttu-id="5fe0c-252">Se si fa clic sulla scheda **Imbuto,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dei dettagli configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-252">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="5fe0c-253">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-253">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="5fe0c-254">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-254">**Direction**:</span></span>
  - <span data-ttu-id="5fe0c-255">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-255">**Inbound**</span></span>
  - <span data-ttu-id="5fe0c-256">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-256">**Outbound**</span></span>
  - <span data-ttu-id="5fe0c-257">**Intra-org:** questo conteggio è per i messaggi inviati all'interno di un tenant; Ad esempio, il mittente abc@domain.com inviato al destinatario xyz@domain.com (conteggiato separatamente da Inbound e Outbound).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-257">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="5fe0c-258">La visualizzazione aggregata e la tabella dei dettagli consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-258">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="5fe0c-259">È possibile modificare questi filtri facendo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-259">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="5fe0c-260">Vengono utilizzati gli stessi filtri **della** visualizzazione Tipo.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-260">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="5fe0c-261">Questo grafico mostra il numero di messaggi di posta elettronica organizzati per:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-261">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="5fe0c-262">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-262">**Total email**</span></span>
- <span data-ttu-id="5fe0c-263">**Posta elettronica dopo la protezione edge**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-263">**Email after edge protection**</span></span>
- <span data-ttu-id="5fe0c-264">**Regola di posta elettronica dopo il trasporto** (regola del flusso di posta)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-264">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="5fe0c-265">**Posta elettronica dopo antimalware, reputazione file, blocco del tipo di file**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-265">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="5fe0c-266">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-266">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="5fe0c-267">**Posta elettronica dopo la posta indesiderata, filtro posta in blocco**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-267">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="5fe0c-268">**Posta elettronica dopo la rappresentazione di utenti e domini**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5fe0c-268">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="5fe0c-269">**Posta elettronica dopo la detonazione di file e URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5fe0c-269">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="5fe0c-270">**Email detected as benign after post-delivery protection (URL click time protection)**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-270">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="5fe0c-271"><sup>\*</sup>Defender solo per Office 365</span><span class="sxs-lookup"><span data-stu-id="5fe0c-271"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="5fe0c-272">Per visualizzare il messaggio di posta elettronica filtrato da EOP o Defender per Office 365 separatamente, fare clic sul valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-272">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="5fe0c-273">La tabella dei dettagli contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-273">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="5fe0c-274">**Data**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-274">**Date**</span></span>
- <span data-ttu-id="5fe0c-275">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-275">**Total email**</span></span>
- <span data-ttu-id="5fe0c-276">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-276">**Edge protection**</span></span>
- <span data-ttu-id="5fe0c-277">**Antimalware, reputazione file, blocco del tipo di file**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-277">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="5fe0c-278">**Reputazione file:** messaggi filtrati a causa dell'identificazione di un file allegato da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-278">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="5fe0c-279">**Blocco del tipo di** file : Messaggi filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-279">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="5fe0c-280">**Anti-phish, reputazione URL, rappresentazione del marchio, anti-spoofing**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-280">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="5fe0c-281">**Reputazione URL**: Messaggi filtrati a causa dell'identificazione dell'URL da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-281">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="5fe0c-282">**Rappresentazione del marchio**: messaggi filtrati a causa del messaggio proveniente da mittenti noti che rappresentano il marchio.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-282">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="5fe0c-283">**Anti-spoof**: messaggi filtrati a causa del tentativo di spoofing di un dominio a cui appartiene il destinatario o di un dominio di cui il mittente non è proprietario.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-283">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="5fe0c-284">**Protezione da posta indesiderata, filtro posta in blocco**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-284">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="5fe0c-285">**Filtro posta in blocco**: Messaggi filtrati in base alla soglia del livello di reclamo in blocco (BCL) in un criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-285">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="5fe0c-286">**Rappresentazione utente e dominio (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-286">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="5fe0c-287">**Rappresentazione utente**: messaggi filtrati a causa di un tentativo di rappresentazione di un utente (mittente del messaggio) definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-287">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="5fe0c-288">**Rappresentazione di dominio**: messaggi filtrati a causa di un tentativo di rappresentare un dominio definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-288">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="5fe0c-289">**Detonazione di file e URL (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-289">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="5fe0c-290">**Detonazione file:** messaggi filtrati da un criterio Cassaforte allegati.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-290">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="5fe0c-291">**Detonazione URL:** messaggio filtrato in base a un criterio Cassaforte collegamenti.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-291">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="5fe0c-292">**Protezione post-recapito e ZAP (ATP) o ZAP (EOP):** eliminazione automatica a zero ore (ZAP) per malware, posta indesiderata e phishing.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-292">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="5fe0c-293">Se si seleziona una riga nella tabella dei dettagli, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-293">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="5fe0c-294">Esportare dalla visualizzazione Imbuto</span><span class="sxs-lookup"><span data-stu-id="5fe0c-294">Export from Funnel view</span></span>

<span data-ttu-id="5fe0c-295">Dopo aver fatto **clic su** Esporta **in Opzioni,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-295">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="5fe0c-296">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-296">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="5fe0c-297">**Dettagli (con dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-297">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="5fe0c-298">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-298">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="5fe0c-299">I dati per i filtri correnti verranno esportati in un .csv file.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-299">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="5fe0c-300">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-300">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5fe0c-301">Se i dati contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-301">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="5fe0c-302">Visualizzazione tecnica per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="5fe0c-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="5fe0c-303">La **visualizzazione Tech** è simile alla visualizzazione **Imbuto,** fornendo dettagli più dettagliati per le funzionalità di protezione dalle minacce configurate.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="5fe0c-304">Dal grafico è possibile vedere come i messaggi vengono categorizzati nelle diverse fasi della protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="5fe0c-305">Se si fa clic **sulla scheda Visualizzazione tecnica,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dei dettagli configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="5fe0c-306">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="5fe0c-307">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-307">**Direction**:</span></span>
  - <span data-ttu-id="5fe0c-308">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-308">**Inbound**</span></span>
  - <span data-ttu-id="5fe0c-309">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-309">**Outbound**</span></span>
  - <span data-ttu-id="5fe0c-310">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="5fe0c-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="5fe0c-311">mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da in ingresso e in uscita)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="5fe0c-312">La visualizzazione aggregata e la tabella dei dettagli consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="5fe0c-313">È possibile modificare questi filtri facendo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="5fe0c-314">Vengono utilizzati gli stessi filtri **della** visualizzazione Tipo.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="5fe0c-315">Questo grafico mostra i messaggi organizzati nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="5fe0c-316">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-316">**Total email**</span></span>
- <span data-ttu-id="5fe0c-317">**Edge allow** e **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="5fe0c-318">**Regola di trasporto consentita** **e regola di trasporto filtrata** (regole del flusso di posta)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="5fe0c-319">**Non malware,** **Cassaforte allegati e** rilevamento motore <sup>\*</sup> **antimalware**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="5fe0c-320">**Not phish,** **DMARC failure,** **Impersonation detection,** <sup>\*</sup> Spoof **detection** e **Phish detection**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="5fe0c-321">**Nessun rilevamento con detonazione URL e** **rilevamento detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5fe0c-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="5fe0c-322">**Non posta indesiderata** e  **posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="5fe0c-323">**Posta elettronica non dannosa,** **rilevamento Cassaforte** <sup>\*</sup> collegamenti e **ZAP**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="5fe0c-324"><sup>\*</sup>Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="5fe0c-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="5fe0c-325">Quando si passa il mouse su una categoria nel grafico, è possibile visualizzare il numero di messaggi in tale categoria.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="5fe0c-326">La tabella dei dettagli contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="5fe0c-327">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-327">**Date (UTC)**</span></span>
- <span data-ttu-id="5fe0c-328">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-328">**Total email**</span></span>
- <span data-ttu-id="5fe0c-329">**Edge filtrato**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-329">**Edge filtered**</span></span>
- <span data-ttu-id="5fe0c-330">**Messaggi delle regole**: Messaggi filtrati a causa delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="5fe0c-331">**Motore antimalware**, **Cassaforte allegati** <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="5fe0c-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="5fe0c-332">**DMARC, impersonation,** <sup>\*</sup> **spoof,** **phish filtered**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="5fe0c-333">**DMARC**: Messaggi filtrati a causa dell'errore del messaggio nel controllo di autenticazione DMARC.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="5fe0c-334">**Rilevamento detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5fe0c-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="5fe0c-335">**Protezione da posta indesiderata filtrata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="5fe0c-336">**ZAP rimosso**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-336">**ZAP removed**</span></span>
- <span data-ttu-id="5fe0c-337">**Rilevamento da Cassaforte collegamenti**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5fe0c-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="5fe0c-338"><sup>\*</sup>Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="5fe0c-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="5fe0c-339">Se si seleziona una riga nella tabella dei dettagli, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="5fe0c-340">Esportare da tech view</span><span class="sxs-lookup"><span data-stu-id="5fe0c-340">Export from Tech view</span></span>

<span data-ttu-id="5fe0c-341">Facendo clic **su Esporta,** in **Opzioni** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="5fe0c-342">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="5fe0c-343">**Dettagli (con dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="5fe0c-344">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="5fe0c-345">I dati per i filtri correnti verranno esportati in un .csv file.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="5fe0c-346">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5fe0c-347">Se i dati contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione tecnica nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="5fe0c-349">Report rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="5fe0c-349">Malware detections report</span></span>

<span data-ttu-id="5fe0c-350">Il **report Rilevamenti malware** mostra informazioni sui rilevamenti di malware nei messaggi di posta elettronica in arrivo e in uscita (malware rilevato da Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="5fe0c-351">Per ulteriori informazioni sulla protezione da malware in EOP, vedere [Protezione antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="5fe0c-352">Il filtro di visualizzazione aggregata consente 90 giorni, mentre il filtro della tabella dei dettagli consente solo 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="5fe0c-353">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5fe0c-354">Nella pagina **Rapporti di collaborazione &** posta elettronica individuare Malware rilevato **nella** posta elettronica e quindi fare clic su **Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="5fe0c-355">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="5fe0c-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Rilevamenti di malware nel widget di posta elettronica nella pagina & report di collaborazione](../../media/malware-detections-widget.png)

<span data-ttu-id="5fe0c-357">Nella pagina **report Rilevamenti malware** è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="5fe0c-358">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-359">**Direzione**: **In ingresso** e **In uscita**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-359">**Direction**: **Inbound** and **Outbound**</span></span>

![Visualizzazione report nel report Rilevamento malware nei messaggi di posta elettronica](../../media/malware-detections-report-view.png)

<span data-ttu-id="5fe0c-361">Nella tabella dei dettagli sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="5fe0c-362">**Data**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-362">**Date**</span></span>
- <span data-ttu-id="5fe0c-363">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-363">**Sender address**</span></span>
- <span data-ttu-id="5fe0c-364">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-364">**Recipient address**</span></span>
- <span data-ttu-id="5fe0c-365">**ID messaggio**: Disponibile nel **campo di intestazione Message-ID** nell'intestazione del messaggio e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="5fe0c-366">Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="5fe0c-367">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-367">**Subject**</span></span>
- <span data-ttu-id="5fe0c-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-368">**Filename**</span></span>
- <span data-ttu-id="5fe0c-369">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="5fe0c-370">Rapporto latenza della posta</span><span class="sxs-lookup"><span data-stu-id="5fe0c-370">Mail latency report</span></span>

<span data-ttu-id="5fe0c-371">Il **report Latenza della posta** in Defender per Office 365 contiene informazioni sulla latenza di recapito e detonazione della posta riscontrata all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="5fe0c-372">Per ulteriori informazioni, vedere [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="5fe0c-373">Report sui rilevamenti della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="5fe0c-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="5fe0c-374">Il **rapporto Rilevamenti posta indesiderata** andrà infine via.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="5fe0c-375">Le stesse informazioni sono disponibili nella relazione [sullo stato di Threat Protection.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="5fe0c-376">Report rilevamenti di spoofing</span><span class="sxs-lookup"><span data-stu-id="5fe0c-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="5fe0c-377">Il report dei rilevamenti di spoofing migliorato, come descritto in questo articolo, è in Anteprima, è soggetto a modifiche e non è disponibile in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="5fe0c-378">La versione precedente del report mostra solo **Posta buona** e Posta indesiderata rilevata come **posta indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="5fe0c-379">Il **report Rilevamenti di** spoofing mostra informazioni sui messaggi bloccati o consentiti a causa dello spoofing.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="5fe0c-380">Per ulteriori informazioni sullo spoofing, vedere [Protezione anti-spoofing in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="5fe0c-381">La visualizzazione aggregata del report consente 45 giorni di filtro, mentre la visualizzazione dettagli consente solo <sup>\*</sup> dieci giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="5fe0c-382"><sup>\*</sup> Infine, sarà possibile utilizzare fino a 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="5fe0c-383">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5fe0c-384">Nella pagina **Rapporti di collaborazione &** posta elettronica individuare **Rilevamenti spoofing** e quindi fare clic **su Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="5fe0c-385">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="5fe0c-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget Rilevamenti di spoofing nella pagina Report & di collaborazione tramite posta elettronica](../../media/spoof-detections-widget.png)

<span data-ttu-id="5fe0c-387">Il grafico mostra le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-387">The chart shows the following information:</span></span>

- <span data-ttu-id="5fe0c-388">**Pass**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-388">**Pass**</span></span>
- <span data-ttu-id="5fe0c-389">**Fail**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-389">**Fail**</span></span>
- <span data-ttu-id="5fe0c-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-390">**SoftPass**</span></span>
- <span data-ttu-id="5fe0c-391">**Nessuna**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-391">**None**</span></span>
- <span data-ttu-id="5fe0c-392">**Altro**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-392">**Other**</span></span>

<span data-ttu-id="5fe0c-393">Quando si passa il mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti messaggi falsificati sono stati rilevati e perché.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="5fe0c-394">Nella pagina **Spoofing mail report** è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="5fe0c-395">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-396">**Risultato**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-396">**Result**:</span></span>
  - <span data-ttu-id="5fe0c-397">**Pass**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-397">**Pass**</span></span>
  - <span data-ttu-id="5fe0c-398">**Fail**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-398">**Fail**</span></span>
  - <span data-ttu-id="5fe0c-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-399">**SoftPass**</span></span>
  - <span data-ttu-id="5fe0c-400">**Nessuna**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-400">**None**</span></span>
  - <span data-ttu-id="5fe0c-401">**Altro**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-401">**Other**</span></span>
- <span data-ttu-id="5fe0c-402">**Tipo spoof**: **interno** ed **esterno**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-402">**Spoof type**: **Internal** and **External**</span></span>

![Pagina di report di posta contraffatta nel portale Microsoft 365 Defender posta](../../media/spoof-detections-report-page.png)

<span data-ttu-id="5fe0c-404">Nella tabella dei dettagli sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="5fe0c-405">**Data**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-405">**Date**</span></span>
- <span data-ttu-id="5fe0c-406">**Utente contraffatto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-406">**Spoofed user**</span></span>
- <span data-ttu-id="5fe0c-407">**Infrastruttura di invio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="5fe0c-408">**Tipo spoofing**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-408">**Spoof type**</span></span>
- <span data-ttu-id="5fe0c-409">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-409">**Result**</span></span>
- <span data-ttu-id="5fe0c-410">**Codice risultato**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-410">**Result code**</span></span>
- <span data-ttu-id="5fe0c-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-411">**SPF**</span></span>
- <span data-ttu-id="5fe0c-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-412">**DKIM**</span></span>
- <span data-ttu-id="5fe0c-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-413">**DMARC**</span></span>
- <span data-ttu-id="5fe0c-414">**Conteggio messaggi**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-414">**Message count**</span></span>

<span data-ttu-id="5fe0c-415">Per ulteriori informazioni sui codici dei risultati dell'autenticazione composita, vedere Intestazioni dei messaggi di posta indesiderata [in Microsoft 365](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="5fe0c-416">Report Invii</span><span class="sxs-lookup"><span data-stu-id="5fe0c-416">Submissions report</span></span>

<span data-ttu-id="5fe0c-417">Il **report Invii** mostra informazioni sugli elementi che gli amministratori hanno segnalato a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="5fe0c-418">Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="5fe0c-419">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5fe0c-420">Nella pagina **E-mail & rapporti di collaborazione,** trovare **Invii** e quindi fare clic **su Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="5fe0c-421">Per passare direttamente al report, aprire <https://security.microsoft.com/adminSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="5fe0c-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="5fe0c-422">Per passare agli [invii di amministratore](admin-submission.md)nel portale Microsoft 365 Defender, fare clic **su Vai a Invii.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget Invii nella pagina Report di & e-mail](../../media/submissions-report-widget.png)

<span data-ttu-id="5fe0c-424">Il grafico mostra le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-424">The chart shows the following information:</span></span>

- <span data-ttu-id="5fe0c-425">**In sospeso**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-425">**Pending**</span></span>
- <span data-ttu-id="5fe0c-426">**Operazione completata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-426">**Completed**</span></span>

<span data-ttu-id="5fe0c-427">Nella pagina **Invii** è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="5fe0c-428">**Data riportata**: **Ora inizio** **e Ora fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="5fe0c-429">**Tipo invio**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-429">**Submission type**:</span></span>
  - <span data-ttu-id="5fe0c-430">**Posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-430">**Email**</span></span>
  - <span data-ttu-id="5fe0c-431">**URL**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-431">**URL**</span></span>
  - <span data-ttu-id="5fe0c-432">**File**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-432">**File**</span></span>
- <span data-ttu-id="5fe0c-433">**ID invio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-433">**Submission ID**</span></span>
- <span data-ttu-id="5fe0c-434">**ID messaggio di rete**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-434">**Network Message ID**</span></span>
- <span data-ttu-id="5fe0c-435">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-435">**Sender**</span></span>
- <span data-ttu-id="5fe0c-436">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-436">**Name**</span></span>
- <span data-ttu-id="5fe0c-437">**Inviato da**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-437">**Submitted by**</span></span>
- <span data-ttu-id="5fe0c-438">**Motivo dell'invio:**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-438">**Reason for submitting**:</span></span>
  - <span data-ttu-id="5fe0c-439">**Non indesiderato**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-439">**Not junk**</span></span>
  - <span data-ttu-id="5fe0c-440">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-440">**Phish**</span></span>
  - <span data-ttu-id="5fe0c-441">**Malware**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-441">**Malware**</span></span>
  - <span data-ttu-id="5fe0c-442">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-442">**Spam**</span></span>
- <span data-ttu-id="5fe0c-443">**Stato nuova analisi**:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-443">**Rescan status**:</span></span>
  - <span data-ttu-id="5fe0c-444">**In sospeso**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-444">**Pending**</span></span>
  - <span data-ttu-id="5fe0c-445">**Operazione completata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-445">**Completed**</span></span>

<span data-ttu-id="5fe0c-446">La tabella dei dettagli sotto il grafico  mostra le stesse informazioni  e ha le stesse opzioni Raggruppa o Personalizza colonne della scheda Inviato per l'analisi in **Invio** di &  \> collaborazione.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-446">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="5fe0c-447">Per altre informazioni, vedi [Visualizzare gli invii di amministratori a Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-447">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Pagina del report Invii nel Microsoft 365 Defender portale](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="5fe0c-449">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="5fe0c-449">Threat protection status report</span></span>

<span data-ttu-id="5fe0c-450">La **relazione sullo stato di Protezione** dalle minacce è disponibile sia in EOP che in Defender per Office 365; Tuttavia, i report contengono dati diversi.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-450">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="5fe0c-451">Ad esempio, i clienti di EOP possono visualizzare le informazioni sul malware rilevato nella posta elettronica, ma non informazioni sui file dannosi rilevati da allegati Cassaforte per [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)e Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="5fe0c-451">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="5fe0c-452">Il report fornisce il conteggio dei messaggi di posta elettronica con contenuto dannoso, ad esempio file o indirizzi di siti Web (URL) bloccati dal motore antimalware, eliminazione automatica a zero ore [(ZAP)](zero-hour-auto-purge.md)e Defender per funzionalità di Office 365 come collegamenti [di Cassaforte,](safe-links.md) [allegati Cassaforte](safe-attachments.md)e funzionalità di protezione dalla rappresentazione nei criteri [anti-phishing.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-452">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="5fe0c-453">È possibile utilizzare queste informazioni per identificare le tendenze o determinare se i criteri dell'organizzazione devono essere rettificati.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-453">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="5fe0c-454">**Nota:** è importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-454">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="5fe0c-455">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-455">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5fe0c-456">Nella pagina **Rapporti di collaborazione &** posta elettronica individuare Lo stato di Protezione dalle **minacce** e quindi fare clic su **Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-456">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="5fe0c-457">Per passare direttamente al report, aprire uno degli URL seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-457">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="5fe0c-458">Defender per Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="5fe0c-458">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="5fe0c-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="5fe0c-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Widget Stato protezione dalle minacce nella pagina Report di collaborazione & posta elettronica](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="5fe0c-461">Per impostazione predefinita, il grafico mostra i dati degli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-461">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="5fe0c-462">Se si fa **clic su** Filtro nella pagina Rapporto sullo stato di **Threat Protection,** è possibile selezionare un intervallo di date di 90 giorni (le sottoscrizioni di valutazione potrebbero essere limitate a 30 giorni).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-462">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="5fe0c-463">La tabella dei dettagli consente il filtro per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-463">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="5fe0c-464">Le visualizzazioni disponibili sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-464">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="5fe0c-465">Visualizzare i dati per panoramica</span><span class="sxs-lookup"><span data-stu-id="5fe0c-465">View data by Overview</span></span>

![Visualizzazione panoramica nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="5fe0c-467">Nella visualizzazione **Visualizza dati per panoramica** vengono visualizzate le seguenti informazioni di rilevamento nel grafico:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-467">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="5fe0c-468">**Malware di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-468">**Email malware**</span></span>
- <span data-ttu-id="5fe0c-469">**Phish di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-469">**Email phish**</span></span>
- <span data-ttu-id="5fe0c-470">**Malware contenuto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-470">**Content malware**</span></span>

<span data-ttu-id="5fe0c-471">Sotto il grafico non è disponibile alcuna tabella dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-471">No details table is available below the chart.</span></span>

<span data-ttu-id="5fe0c-472">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-472">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5fe0c-473">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-473">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-474">**Rilevamento**: **malware della posta** elettronica, **e-mail phish** o **malware contenuto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-474">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="5fe0c-475">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-475">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5fe0c-476">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-476">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5fe0c-477">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-477">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5fe0c-478">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-478">**Direction**</span></span>
- <span data-ttu-id="5fe0c-479">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-479">**Domain**</span></span>
- <span data-ttu-id="5fe0c-480">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-480">**Policy type**</span></span>

<span data-ttu-id="5fe0c-481">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-481">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="5fe0c-482">Visualizzare i dati tramite Analisi \> e-mail e scomposizione grafico per tecnologia di rilevamento</span><span class="sxs-lookup"><span data-stu-id="5fe0c-482">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Visualizzazione della tecnologia di rilevamento per la posta elettronica di phishing nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="5fe0c-484">Nella visualizzazione **Visualizza dati per \> e-mail phish** e **grafico per** tecnologia di rilevamento, nel grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-484">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="5fe0c-485">**Reputazione url dannosa:** <sup>\*</sup> reputazione url dannoso generata da Defender per Office 365 detonazioni in altri Microsoft 365 clienti.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-485">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="5fe0c-486">**Filtro avanzato:** segnali di phishing basati sull'apprendimento automatico.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-486">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="5fe0c-487">**Filtro generale**: Segnali di phishing basati sulle regole degli analisti.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-487">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="5fe0c-488">**Spoofing all'interno dell'organizzazione:** il mittente sta tentando di eseguire lo spoofing del dominio del destinatario.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-488">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="5fe0c-489">**Spoofing del dominio esterno:** il mittente sta tentando di eseguire lo spoofing di un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-489">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="5fe0c-490">**Spoof DMARC:** errore di autenticazione DMARC nei messaggi.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-490">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="5fe0c-491">**Marchio di rappresentazione**: Rappresentazione di marchi noti in base ai mittenti.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-491">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="5fe0c-492">**Rilevamento dell'analisi mista**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-492">**Mixed analysis detection**</span></span>
- <span data-ttu-id="5fe0c-493">**Reputazione file**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-493">**File reputation**</span></span>
- <span data-ttu-id="5fe0c-494">**Corrispondenza delle impronte digitali**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-494">**Fingerprint matching**</span></span>
- <span data-ttu-id="5fe0c-495">**Reputazione detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5fe0c-495">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="5fe0c-496">**Detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5fe0c-496">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="5fe0c-497">**Utente di rappresentazione**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5fe0c-497">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="5fe0c-498">**Dominio di rappresentazione** <sup>\*</sup> : Rappresentazione dei domini che il cliente possiede o definisce.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-498">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="5fe0c-499">**Rappresentazione dell'intelligence delle** <sup>\*</sup> cassette postali : Rappresentazione degli utenti definiti dall'amministratore o appresi tramite l'intelligence delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-499">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="5fe0c-500">**Detonazione file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5fe0c-500">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="5fe0c-501">**Campagna**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5fe0c-501">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="5fe0c-502">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-502">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5fe0c-503">**Data**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-503">**Date**</span></span>
- <span data-ttu-id="5fe0c-504">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-504">**Subject**</span></span>
- <span data-ttu-id="5fe0c-505">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-505">**Sender**</span></span>
- <span data-ttu-id="5fe0c-506">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-506">**Recipients**</span></span>
- <span data-ttu-id="5fe0c-507">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-507">**Detected by**</span></span>
- <span data-ttu-id="5fe0c-508">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-508">**Delivery Status**</span></span>
- <span data-ttu-id="5fe0c-509">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-509">**Source of Compromise**</span></span>
- <span data-ttu-id="5fe0c-510">**Tag**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-510">**Tags**</span></span>

<span data-ttu-id="5fe0c-511">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-511">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5fe0c-512">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-512">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-513">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-513">**Detection**</span></span>
- <span data-ttu-id="5fe0c-514">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-514">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5fe0c-515">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-515">**Direction**</span></span>
- <span data-ttu-id="5fe0c-516">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-516">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5fe0c-517">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-517">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5fe0c-518">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-518">**Domain**</span></span>
- <span data-ttu-id="5fe0c-519">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-519">**Policy type**</span></span>
- <span data-ttu-id="5fe0c-520">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-520">**Policy name** (details table only)</span></span>
- <span data-ttu-id="5fe0c-521">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-521">**Recipients**</span></span>

<span data-ttu-id="5fe0c-522">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-522">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="5fe0c-523">Visualizzare i dati tramite malware \> e-mail e scomposizione grafico per tecnologia di rilevamento</span><span class="sxs-lookup"><span data-stu-id="5fe0c-523">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Visualizzazione della tecnologia di rilevamento per il malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="5fe0c-525">Nella visualizzazione **Visualizza dati per \> malware** e-mail e **grafico per** tecnologia di rilevamento, nel grafico vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-525">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="5fe0c-526">**Detonazione file** <sup>\*</sup> : rilevamento da parte Cassaforte allegati.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-526">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="5fe0c-527">**Reputazione detonazione file:** tutta la reputazione dei file dannosi generata da Defender per Office 365 <sup>\*</sup> detonazioni.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-527">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="5fe0c-528">**Reputazione file**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-528">**File reputation**</span></span>
- <span data-ttu-id="5fe0c-529">**Motore antimalware:** <sup>\*</sup> rilevamento da motori antimalware.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-529">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="5fe0c-530">**Blocco del tipo di file dei** criteri antimalware: si tratta di messaggi di posta elettronica filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-530">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="5fe0c-531">**REPUTAZIONE URL dannosa**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-531">**URL malicious reputation**</span></span>
- <span data-ttu-id="5fe0c-532">**Detonazione URL**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-532">**URL detonation**</span></span>
- <span data-ttu-id="5fe0c-533">**Reputazione detonazione URL**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-533">**URL detonation reputation**</span></span>
- <span data-ttu-id="5fe0c-534">**Campagna**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-534">**Campaign**</span></span>

<span data-ttu-id="5fe0c-535">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-535">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5fe0c-536">**Data**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-536">**Date**</span></span>
- <span data-ttu-id="5fe0c-537">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-537">**Subject**</span></span>
- <span data-ttu-id="5fe0c-538">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-538">**Sender**</span></span>
- <span data-ttu-id="5fe0c-539">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-539">**Recipients**</span></span>
- <span data-ttu-id="5fe0c-540">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-540">**Detected by**</span></span>
- <span data-ttu-id="5fe0c-541">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-541">**Delivery Status**</span></span>
- <span data-ttu-id="5fe0c-542">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-542">**Source of Compromise**</span></span>
- <span data-ttu-id="5fe0c-543">**Tag**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-543">**Tags**</span></span>

<span data-ttu-id="5fe0c-544">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-544">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5fe0c-545">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-545">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-546">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-546">**Detection**</span></span>
- <span data-ttu-id="5fe0c-547">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-547">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5fe0c-548">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-548">**Direction**</span></span>
- <span data-ttu-id="5fe0c-549">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-549">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5fe0c-550">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-550">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5fe0c-551">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-551">**Domain**</span></span>
- <span data-ttu-id="5fe0c-552">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-552">**Policy type**</span></span>
- <span data-ttu-id="5fe0c-553">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-553">**Policy name** (details table only)</span></span>
- <span data-ttu-id="5fe0c-554">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-554">**Recipients**</span></span>

<span data-ttu-id="5fe0c-555">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-555">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="5fe0c-556">Suddivisione del grafico per tipo di criteri e Visualizzazione dei dati tramite e-mail Phish o \> Visualizzazione dei dati tramite malware di posta \> elettronica</span><span class="sxs-lookup"><span data-stu-id="5fe0c-556">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Visualizzazione del tipo di criterio per la posta elettronica di phishing o la posta elettronica malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="5fe0c-558">Nelle **visualizzazioni Scomposizione grafico** per tipo di criterio e Visualizza dati per posta elettronica **\> o** Visualizza dati tramite **\> malware** tramite posta elettronica, nei grafici vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-558">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="5fe0c-559">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-559">**Anti-malware**</span></span>
- <span data-ttu-id="5fe0c-560">**Cassaforte Allegati**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5fe0c-560">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="5fe0c-561">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-561">**Anti-phish**</span></span>
- <span data-ttu-id="5fe0c-562">**Protezione da posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-562">**Anti-spam**</span></span>
- <span data-ttu-id="5fe0c-563">**Regola del flusso di** posta (nota anche come regola di trasporto)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-563">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="5fe0c-564">**Altri**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-564">**Others**</span></span>

<span data-ttu-id="5fe0c-565">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-565">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5fe0c-566">**Data**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-566">**Date**</span></span>
- <span data-ttu-id="5fe0c-567">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-567">**Subject**</span></span>
- <span data-ttu-id="5fe0c-568">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-568">**Sender**</span></span>
- <span data-ttu-id="5fe0c-569">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-569">**Recipients**</span></span>
- <span data-ttu-id="5fe0c-570">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-570">**Detected by**</span></span>
- <span data-ttu-id="5fe0c-571">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-571">**Delivery Status**</span></span>
- <span data-ttu-id="5fe0c-572">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-572">**Source of Compromise**</span></span>
- <span data-ttu-id="5fe0c-573">**Tag**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-573">**Tags**</span></span>

<span data-ttu-id="5fe0c-574">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5fe0c-575">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-575">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-576">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-576">**Detection**</span></span>
- <span data-ttu-id="5fe0c-577">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-577">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5fe0c-578">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-578">**Direction**</span></span>
- <span data-ttu-id="5fe0c-579">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-579">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5fe0c-580">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-580">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5fe0c-581">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-581">**Domain**</span></span>
- <span data-ttu-id="5fe0c-582">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-582">**Policy type**</span></span>
- <span data-ttu-id="5fe0c-583">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-583">**Policy name** (details table only)</span></span>
- <span data-ttu-id="5fe0c-584">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-584">**Recipients**</span></span>

<span data-ttu-id="5fe0c-585">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-585">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="5fe0c-586">Suddivisione del grafico per stato di recapito e Visualizzazione dei dati tramite e-mail Phish o \> Visualizzazione dei dati tramite malware di posta \> elettronica</span><span class="sxs-lookup"><span data-stu-id="5fe0c-586">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Visualizzazione dello stato del recapito per posta elettronica di phishing e posta elettronica malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="5fe0c-588">Nelle **visualizzazioni Scomposizione grafico** per stato recapito e Visualizza dati per posta elettronica **\> o** Visualizza dati tramite **\> malware** tramite posta elettronica, nei grafici vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-588">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="5fe0c-589">**Cassetta postale ospitata: Posta in arrivo**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-589">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="5fe0c-590">**Cassetta postale ospitata: Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-590">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="5fe0c-591">**Cassetta postale ospitata: cartella personalizzata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-591">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="5fe0c-592">**Cassetta postale ospitata: Elementi eliminati**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-592">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="5fe0c-593">**Inoltrato**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-593">**Forwarded**</span></span>
- <span data-ttu-id="5fe0c-594">**Server locale: recapitato**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-594">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="5fe0c-595">**Quarantena**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-595">**Quarantine**</span></span>
- <span data-ttu-id="5fe0c-596">**Recapito non riuscito**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-596">**Delivery failed**</span></span>
- <span data-ttu-id="5fe0c-597">**Rilasciato**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-597">**Dropped**</span></span>

<span data-ttu-id="5fe0c-598">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-598">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5fe0c-599">**Data**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-599">**Date**</span></span>
- <span data-ttu-id="5fe0c-600">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-600">**Subject**</span></span>
- <span data-ttu-id="5fe0c-601">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-601">**Sender**</span></span>
- <span data-ttu-id="5fe0c-602">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-602">**Recipients**</span></span>
- <span data-ttu-id="5fe0c-603">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-603">**Detected by**</span></span>
- <span data-ttu-id="5fe0c-604">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-604">**Delivery Status**</span></span>
- <span data-ttu-id="5fe0c-605">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-605">**Source of Compromise**</span></span>
- <span data-ttu-id="5fe0c-606">**Tag**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-606">**Tags**</span></span>

<span data-ttu-id="5fe0c-607">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-607">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5fe0c-608">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-608">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-609">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-609">**Detection**</span></span>
- <span data-ttu-id="5fe0c-610">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-610">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5fe0c-611">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-611">**Direction**</span></span>
- <span data-ttu-id="5fe0c-612">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-612">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5fe0c-613">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-613">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5fe0c-614">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-614">**Domain**</span></span>
- <span data-ttu-id="5fe0c-615">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-615">**Policy type**</span></span>
- <span data-ttu-id="5fe0c-616">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-616">**Policy name** (details table only)</span></span>
- <span data-ttu-id="5fe0c-617">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-617">**Recipients**</span></span>

<span data-ttu-id="5fe0c-618">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-618">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="5fe0c-619">Visualizzare i dati in base al malware contenuto \></span><span class="sxs-lookup"><span data-stu-id="5fe0c-619">View data by Content \> Malware</span></span>

![Visualizzazione malware contenuto nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="5fe0c-621">Nella visualizzazione **Visualizzazione dati per \> malware** contenuto, nel grafico per Microsoft Defender per Office 365 organizzazioni:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-621">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="5fe0c-622">**Motore antimalware:** file dannosi rilevati in Sharepoint, OneDrive e Microsoft Teams dal rilevamento di [virus incorporato in Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-622">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="5fe0c-623">**Detonazione file:** file dannosi rilevati da Cassaforte allegati per [SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-623">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="5fe0c-624">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-624">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5fe0c-625">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-625">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-626">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-626">**Location**</span></span>
- <span data-ttu-id="5fe0c-627">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-627">**Detected by**</span></span>
- <span data-ttu-id="5fe0c-628">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-628">**Malware name**</span></span>

<span data-ttu-id="5fe0c-629">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-629">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5fe0c-630">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-630">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-631">**Rilevamento:** **motore antimalware o** **detonazione file**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-631">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="5fe0c-632">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-632">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="5fe0c-633">Visualizzare i dati per sostituzione di sistema</span><span class="sxs-lookup"><span data-stu-id="5fe0c-633">View data by System override</span></span>

![Visualizzazione sostituzione messaggio nel rapporto sullo stato di Threat Protection](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="5fe0c-635">Nella visualizzazione **Visualizza dati per sostituzione di** sistema, nel grafico vengono visualizzate le seguenti informazioni sul motivo dell'override:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-635">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="5fe0c-636">**Ignora locale**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-636">**On-premises skip**</span></span>
- <span data-ttu-id="5fe0c-637">**IP allow**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-637">**IP allow**</span></span>
- <span data-ttu-id="5fe0c-638">**Exchange di trasporto della posta** elettronica (regola del flusso di posta)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-638">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="5fe0c-639">**Mittenti consentiti dall'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-639">**Organization allowed senders**</span></span>
- <span data-ttu-id="5fe0c-640">**Domini consentiti dall'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-640">**Organization allowed domains**</span></span>
- <span data-ttu-id="5fe0c-641">**ZAP non abilitato**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-641">**ZAP not enabled**</span></span>
- <span data-ttu-id="5fe0c-642">**Cartella Posta indesiderata non abilitata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-642">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="5fe0c-643">**Mittente Cassaforte utente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-643">**User Safe Sender**</span></span>
- <span data-ttu-id="5fe0c-644">**Dominio Cassaforte utente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-644">**User Safe Domain**</span></span>

<span data-ttu-id="5fe0c-645">Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-645">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5fe0c-646">**Data**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-646">**Date**</span></span>
- <span data-ttu-id="5fe0c-647">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-647">**Subject**</span></span>
- <span data-ttu-id="5fe0c-648">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-648">**Sender**</span></span>
- <span data-ttu-id="5fe0c-649">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-649">**Recipients**</span></span>
- <span data-ttu-id="5fe0c-650">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-650">**Detected by**</span></span>
- <span data-ttu-id="5fe0c-651">**Stato recapito**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-651">**Delivery Status**</span></span>
- <span data-ttu-id="5fe0c-652">**Origine della compromissione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-652">**Source of Compromise**</span></span>
- <span data-ttu-id="5fe0c-653">**Tag**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-653">**Tags**</span></span>

<span data-ttu-id="5fe0c-654">Se si fa **clic su Filtro**, sono disponibili i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-654">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5fe0c-655">**Data (UTC)** **Data di inizio e** Data **fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-655">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5fe0c-656">**Rilevamento**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-656">**Detection**</span></span>
- <span data-ttu-id="5fe0c-657">**Protetto da**: **MDO** (Defender per Office 365) o **EOP**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-657">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5fe0c-658">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-658">**Direction**</span></span>
- <span data-ttu-id="5fe0c-659">**Tag**: filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-659">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5fe0c-660">Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-660">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5fe0c-661">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-661">**Domain**</span></span>
- <span data-ttu-id="5fe0c-662">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-662">**Policy type**</span></span>
- <span data-ttu-id="5fe0c-663">**Nome criterio** (solo tabella dei dettagli)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-663">**Policy name** (details table only)</span></span>
- <span data-ttu-id="5fe0c-664">**Destinatari**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-664">**Recipients**</span></span>

<span data-ttu-id="5fe0c-665">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-665">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="5fe0c-666"><sup>\*</sup>Defender solo per Office 365</span><span class="sxs-lookup"><span data-stu-id="5fe0c-666"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="5fe0c-667">Report principale sul malware</span><span class="sxs-lookup"><span data-stu-id="5fe0c-667">Top malware report</span></span>

<span data-ttu-id="5fe0c-668">Il **report Top malware** mostra i vari tipi di malware rilevati dalla protezione [antimalware in EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-668">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="5fe0c-669">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-669">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5fe0c-670">Nella pagina **E-mail & rapporti di collaborazione,** individuare **Malware** principale e quindi fare clic **su Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-670">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="5fe0c-671">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="5fe0c-671">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Widget malware principale nella pagina Report di collaborazione & posta elettronica](../../media/top-malware-report-widget.png)

<span data-ttu-id="5fe0c-673">Quando si passa il mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi rilevati come malware.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-673">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="5fe0c-674">Nella pagina **Report malware principale** viene visualizzata una versione più grande del grafico a torta nella pagina del report. La tabella dei dettagli sotto il grafico mostra le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-674">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="5fe0c-675">**Malware principale**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-675">**Top malware**</span></span>
- <span data-ttu-id="5fe0c-676">**Numero**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-676">**Count**</span></span>

<span data-ttu-id="5fe0c-677">Se si fa **clic su Filtro**, è possibile specificare un intervallo di date con Data **inizio** e **Data fine**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-677">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Visualizzazione dei report principali sul malware](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="5fe0c-679">Report di protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="5fe0c-679">URL threat protection report</span></span>

<span data-ttu-id="5fe0c-680">Il **report di protezione dalle minacce URL** è disponibile solo in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-680">The **URL threat protection report** is available only in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="5fe0c-681">Per ulteriori informazioni, vedere [Report di protezione dalle minacce URL](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-681">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="5fe0c-682">Rapporto messaggi segnalati dall'utente</span><span class="sxs-lookup"><span data-stu-id="5fe0c-682">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fe0c-683">Per il corretto funzionamento del rapporto **Messaggi segnalati** dall'utente, è necessario che la registrazione di controllo sia attivata per l'Microsoft 365 locale. </span><span class="sxs-lookup"><span data-stu-id="5fe0c-683">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="5fe0c-684">Questa operazione viene in genere eseguita da un utente a cui è assegnato il ruolo Log di controllo in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-684">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="5fe0c-685">Per ulteriori informazioni, vedere [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-685">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="5fe0c-686">Il **report Messaggi segnalati** dall'utente mostra informazioni sui messaggi di posta elettronica [](enable-the-report-message-add-in.md) segnalati dagli utenti come posta indesiderata, tentativi di phishing o buona posta utilizzando il componente aggiuntivo Segnala messaggio o Segnala [phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-686">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="5fe0c-687">Per visualizzare il report nel portale Microsoft 365 Defender, passare **a** Report e-mail & \> **collaborazione** \> **E-mail & rapporti di collaborazione**.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-687">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5fe0c-688">Nella pagina **Rapporti di collaborazione &** posta elettronica individuare Messaggi segnalati **dall'utente** e quindi fare clic su **Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-688">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="5fe0c-689">Per passare direttamente al report, aprire <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="5fe0c-689">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="5fe0c-690">Per passare agli [invii di amministratore](admin-submission.md)nel portale Microsoft 365 Defender, fare clic **su Vai a Invii.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-690">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget Messaggi segnalati dall'utente nella pagina Rapporti di collaborazione & posta elettronica](../../media/user-reported-messages-widget.png)

<span data-ttu-id="5fe0c-692">Nella pagina **Messaggi segnalati** dall'utente è possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtro** e selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-692">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="5fe0c-693">**Data riportata**: **Ora inizio** **e Ora fine**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-693">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="5fe0c-694">**Segnalato da**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-694">**Reported by**</span></span>
- <span data-ttu-id="5fe0c-695">**Oggetto e-mail**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-695">**Email subject**</span></span>
- <span data-ttu-id="5fe0c-696">**ID segnalato messaggio**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-696">**Message reported ID**</span></span>
- <span data-ttu-id="5fe0c-697">**ID messaggio di rete**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-697">**Network Message ID**</span></span>
- <span data-ttu-id="5fe0c-698">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-698">**Sender**</span></span>
- <span data-ttu-id="5fe0c-699">**Motivo segnalato**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-699">**Reported reason**</span></span>
  - <span data-ttu-id="5fe0c-700">**Non indesiderato**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-700">**Not junk**</span></span>
  - <span data-ttu-id="5fe0c-701">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-701">**Phish**</span></span>
  - <span data-ttu-id="5fe0c-702">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-702">**Spam**</span></span>
- <span data-ttu-id="5fe0c-703">**Simulazione phish**: **Sì** o **No**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-703">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="5fe0c-704">Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-704">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="5fe0c-705">Per raggruppare le voci, fare clic **su Gruppo** e selezionare uno dei valori seguenti nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-705">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="5fe0c-706">**Nessuna**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-706">**None**</span></span>
- <span data-ttu-id="5fe0c-707">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-707">**Reason**</span></span>
- <span data-ttu-id="5fe0c-708">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-708">**Sender**</span></span>
- <span data-ttu-id="5fe0c-709">**Segnalato da**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-709">**Reported by**</span></span>
- <span data-ttu-id="5fe0c-710">**Risultato dell'analisi**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-710">**Rescan result**</span></span>
- <span data-ttu-id="5fe0c-711">**Simulazione phish**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-711">**Phish simulation**</span></span>

![Rapporto messaggi segnalati dall'utente](../../media/user-reported-messages-report.png)

<span data-ttu-id="5fe0c-713">Nella tabella dei dettagli sotto il grafico è possibile visualizzare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-713">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="5fe0c-714">**Oggetto e-mail**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-714">**Email subject**</span></span>
- <span data-ttu-id="5fe0c-715">**Segnalato da**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-715">**Reported by**</span></span>
- <span data-ttu-id="5fe0c-716">**Data riportata**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-716">**Date reported**</span></span>
- <span data-ttu-id="5fe0c-717">**Mittente**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-717">**Sender**</span></span>
- <span data-ttu-id="5fe0c-718">**Motivo segnalato**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-718">**Reported reason**</span></span>
- <span data-ttu-id="5fe0c-719">**Risultato dell'analisi**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-719">**Rescan result**</span></span>
- <span data-ttu-id="5fe0c-720">**Tag**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-720">**Tags**</span></span>

<span data-ttu-id="5fe0c-721">Per inviare un messaggio a Microsoft per l'analisi, selezionare la voce del messaggio dalla tabella, fare clic su Invia a **Microsoft** per l'analisi e quindi selezionare uno dei valori seguenti nell'elenco a discesa:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-721">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="5fe0c-722">**Segnala pulito**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-722">**Report clean**</span></span>
- <span data-ttu-id="5fe0c-723">**Segnalare phishing**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-723">**Report phishing**</span></span>
- <span data-ttu-id="5fe0c-724">**Segnalare malware**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-724">**Report malware**</span></span>
- <span data-ttu-id="5fe0c-725">**Segnala posta indesiderata**'</span><span class="sxs-lookup"><span data-stu-id="5fe0c-725">**Report spam**'</span></span>
- <span data-ttu-id="5fe0c-726">**Attivare l'indagine** (Defender per Office 365)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-726">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="5fe0c-727">Quali autorizzazioni sono necessarie per visualizzare questi report?</span><span class="sxs-lookup"><span data-stu-id="5fe0c-727">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="5fe0c-728">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel portale di Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="5fe0c-728">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="5fe0c-729">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-729">**Organization Management**</span></span>
- <span data-ttu-id="5fe0c-730">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-730">**Security Administrator**</span></span>
- <span data-ttu-id="5fe0c-731">**Lettore sicurezza**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-731">**Security Reader**</span></span>
- <span data-ttu-id="5fe0c-732">**Lettore globale**</span><span class="sxs-lookup"><span data-stu-id="5fe0c-732">**Global Reader**</span></span>

<span data-ttu-id="5fe0c-733">Per altre informazioni, vedere [Autorizzazioni nel portale di Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-733">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

<span data-ttu-id="5fe0c-734">**Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nel interfaccia di amministrazione di Microsoft 365 offre agli utenti le  autorizzazioni necessarie nel portale di Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-734">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5fe0c-735">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5fe0c-735">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="5fe0c-736">Cosa succede se i report non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="5fe0c-736">What if the reports aren't showing data?</span></span>

<span data-ttu-id="5fe0c-737">Se i dati nei report non vengono visualizzati, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="5fe0c-737">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="5fe0c-738">Per ulteriori informazioni, vedere [Protezione dalle minacce.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="5fe0c-738">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5fe0c-739">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5fe0c-739">Related topics</span></span>

[<span data-ttu-id="5fe0c-740">Protezione da posta indesiderata e antimalware in EOP</span><span class="sxs-lookup"><span data-stu-id="5fe0c-740">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="5fe0c-741">Report e informazioni dettagliate intelligenti nel portale Microsoft 365 Defender dati</span><span class="sxs-lookup"><span data-stu-id="5fe0c-741">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="5fe0c-742">Visualizzare i report del flusso di posta nel portale Microsoft 365 Defender posta</span><span class="sxs-lookup"><span data-stu-id="5fe0c-742">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="5fe0c-743">Visualizzare i report per Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="5fe0c-743">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
