---
title: Monitorare e rispondere alle minacce emergenti con l'analisi delle minacce
ms.reviewer: ''
description: Informazioni sulle minacce emergenti e sulle tecniche di attacco e su come arrestarle. Valutarne l'impatto sull'organizzazione e valutare la resilienza dell'organizzazione.
keywords: threat analytics, risk evaluation, Microsoft 365 Defender, M365D, mitigation status, secure configuration, Microsoft Defender for Office 365, Microsoft Defender for Office 365 threat analytics, MDO threat analytics, integrated MDE and MDO threat analytics data, threat analytics integration, integrated Microsoft 365 Defender threat analytics
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c03dfef28744e2ee565c25d921902b8d11ecb7a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290244"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="7bbab-105">Monitorare e rispondere alle minacce emergenti con l'analisi delle minacce</span><span class="sxs-lookup"><span data-stu-id="7bbab-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7bbab-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7bbab-106">**Applies to:**</span></span>
- <span data-ttu-id="7bbab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bbab-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="7bbab-108">Vuoi provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="7bbab-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="7bbab-109">Puoi [valutarlo in un ambiente lab](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [eseguire il progetto pilota in produzione](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="7bbab-109">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="7bbab-110">L'analisi delle minacce è la soluzione di intelligence per le minacce nel prodotto di esperti ricercatori di sicurezza Microsoft, progettata per aiutare i team di sicurezza a essere il più efficienti possibile affrontando le minacce emergenti, tra cui:</span><span class="sxs-lookup"><span data-stu-id="7bbab-110">Threat analytics is our in-product threat intelligence solution from expert Microsoft security researchers, designed to assist security teams to be as efficient as possible while facing emerging threats, including:</span></span>

- <span data-ttu-id="7bbab-111">Attori delle minacce attive e le loro campagne</span><span class="sxs-lookup"><span data-stu-id="7bbab-111">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="7bbab-112">Tecniche di attacco popolari e nuove</span><span class="sxs-lookup"><span data-stu-id="7bbab-112">Popular and new attack techniques</span></span>
- <span data-ttu-id="7bbab-113">Vulnerabilità critiche</span><span class="sxs-lookup"><span data-stu-id="7bbab-113">Critical vulnerabilities</span></span>
- <span data-ttu-id="7bbab-114">Le superfici di attacco comuni</span><span class="sxs-lookup"><span data-stu-id="7bbab-114">Common attack surfaces</span></span>
- <span data-ttu-id="7bbab-115">I malware prevalenti</span><span class="sxs-lookup"><span data-stu-id="7bbab-115">Prevalent malware</span></span>

<span data-ttu-id="7bbab-116">Guarda questo breve video per saperne di più su come l'analisi delle minacce può aiutarti a tenere traccia delle minacce più recenti e a fermarle.</span><span class="sxs-lookup"><span data-stu-id="7bbab-116">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

<span data-ttu-id="7bbab-117">È Microsoft 365 possibile accedere all'analisi delle minacce dal lato superiore sinistro della barra di spostamento del portale di sicurezza o da una scheda del dashboard dedicata che mostra le minacce principali nell'organizzazione. Ottenere visibilità sulle campagne attive o in corso e sapere cosa fare tramite l'analisi delle minacce può aiutare il team delle operazioni di sicurezza a prendere decisioni informate.</span><span class="sxs-lookup"><span data-stu-id="7bbab-117">You can access threat analytics either from the upper left-hand side of Microsoft 365 security portal’s navigation bar, or from a dedicated dashboard card which shows the top threats in your org. Getting visibility on active or ongoing campaigns and knowing what to do through threat analytics can help equip your security operations team with informed decisions.</span></span> 

![Immagine del dashboard di analisi delle minacce](../../media/threat-analytics/ta_inlandingpage_mtp.png)

<span data-ttu-id="7bbab-119">_Dove accedere all'analisi delle minacce_</span><span class="sxs-lookup"><span data-stu-id="7bbab-119">_Where to access threat analytics_</span></span>

<span data-ttu-id="7bbab-120">Con gli avversari più sofisticati e le nuove minacce che emergono spesso e prevalentemente, è fondamentale essere in grado di:</span><span class="sxs-lookup"><span data-stu-id="7bbab-120">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="7bbab-121">Identificare e reagire alle minacce emergenti</span><span class="sxs-lookup"><span data-stu-id="7bbab-121">Identify and react to emerging threats</span></span>
- <span data-ttu-id="7bbab-122">Informazioni se si è attualmente sotto attacco</span><span class="sxs-lookup"><span data-stu-id="7bbab-122">Learn if you are currently under attack</span></span>
- <span data-ttu-id="7bbab-123">Valutare l'impatto della minaccia per le risorse</span><span class="sxs-lookup"><span data-stu-id="7bbab-123">Assess the impact of the threat to your assets</span></span>
- <span data-ttu-id="7bbab-124">Esaminare la resilienza o l'esposizione alle minacce</span><span class="sxs-lookup"><span data-stu-id="7bbab-124">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="7bbab-125">Identificare le azioni di mitigazione, ripristino o prevenzione che è possibile eseguire per arrestare o contenere le minacce</span><span class="sxs-lookup"><span data-stu-id="7bbab-125">Identify the mitigation, recovery, or prevention actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="7bbab-126">Ogni report fornisce un'analisi di una minaccia monitorata e indicazioni dettagliate su come difendersi da tale minaccia.</span><span class="sxs-lookup"><span data-stu-id="7bbab-126">Each report provides an analysis of a tracked threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="7bbab-127">Incorpora inoltre i dati della rete, che indicano se la minaccia è attiva e se sono presenti protezioni applicabili.</span><span class="sxs-lookup"><span data-stu-id="7bbab-127">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="7bbab-128">Visualizzare il dashboard di analisi delle minacce</span><span class="sxs-lookup"><span data-stu-id="7bbab-128">View the threat analytics dashboard</span></span>

<span data-ttu-id="7bbab-129">Il dashboard di analisi delle minacce ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) evidenzia i report più rilevanti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7bbab-129">The threat analytics dashboard ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) highlights the reports that are most relevant to your organization.</span></span> <span data-ttu-id="7bbab-130">Riepiloga le minacce nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bbab-130">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="7bbab-131">**Minacce più** recenti: elenca i report sulle minacce pubblicati o aggiornati più di recente, insieme al numero di avvisi attivi e risolti.</span><span class="sxs-lookup"><span data-stu-id="7bbab-131">**Latest threats**—lists the most recently published or updated threat reports, along with the number of active and resolved alerts.</span></span>
- <span data-ttu-id="7bbab-132">**Minacce ad alto impatto:** elenca le minacce che hanno il maggiore impatto sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7bbab-132">**High-impact threats**—lists the threats that have the highest impact to your organization.</span></span> <span data-ttu-id="7bbab-133">In questa sezione vengono elencate per prime le minacce con il maggior numero di avvisi attivi e risolti.</span><span class="sxs-lookup"><span data-stu-id="7bbab-133">This section lists threats with the highest number of active and resolved alerts first.</span></span>
- <span data-ttu-id="7bbab-134">**Riepilogo delle** minacce: fornisce l'impatto complessivo di tutte le minacce rilevate mostrando il numero di minacce con avvisi attivi e risolti.</span><span class="sxs-lookup"><span data-stu-id="7bbab-134">**Threat summary**—provides the overall impact of all tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="7bbab-135">Selezionare una minaccia dal dashboard per visualizzare il report per tale minaccia.</span><span class="sxs-lookup"><span data-stu-id="7bbab-135">Select a threat from the dashboard to view the report for that threat.</span></span>

![Screenshot del dashboard di analisi delle minacce](../../media/threat-analytics/ta_dashboard_mtp.png)

<span data-ttu-id="7bbab-137">_Dashboard di analisi delle minacce. Puoi anche fare clic sull'icona Cerca per trovare una parola chiave correlata al report di analisi delle minacce che vuoi leggere._</span><span class="sxs-lookup"><span data-stu-id="7bbab-137">_Threat analytics dashboard. You can also click the Search icon to key in a keyword related to the threat analytics report that you'd like to read._</span></span> 

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="7bbab-138">Visualizzare un report di analisi delle minacce</span><span class="sxs-lookup"><span data-stu-id="7bbab-138">View a threat analytics report</span></span>

<span data-ttu-id="7bbab-139">Ogni report di analisi delle minacce fornisce informazioni in diverse sezioni:</span><span class="sxs-lookup"><span data-stu-id="7bbab-139">Each threat analytics report provides information in several sections:</span></span>

- [<span data-ttu-id="7bbab-140">**Panoramica**</span><span class="sxs-lookup"><span data-stu-id="7bbab-140">**Overview**</span></span>](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses)
- [<span data-ttu-id="7bbab-141">**Report di analisi**</span><span class="sxs-lookup"><span data-stu-id="7bbab-141">**Analyst report**</span></span>](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [<span data-ttu-id="7bbab-142">**Eventi imprevisti correlati**</span><span class="sxs-lookup"><span data-stu-id="7bbab-142">**Related incidents**</span></span>](#related-incidents-view-and-manage-related-incidents)
- [<span data-ttu-id="7bbab-143">**Asset influenzati**</span><span class="sxs-lookup"><span data-stu-id="7bbab-143">**Impacted assets**</span></span>](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [<span data-ttu-id="7bbab-144">**Tentativi di posta elettronica non consentiti**</span><span class="sxs-lookup"><span data-stu-id="7bbab-144">**Prevented email attempts**</span></span>](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [<span data-ttu-id="7bbab-145">**Mitigazioni**</span><span class="sxs-lookup"><span data-stu-id="7bbab-145">**Mitigations**</span></span>](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="7bbab-146">Panoramica: comprendere rapidamente la minaccia, valutarne l'impatto ed esaminare le difese</span><span class="sxs-lookup"><span data-stu-id="7bbab-146">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="7bbab-147">La **sezione Panoramica** offre un'anteprima del report dettagliato degli analisti.</span><span class="sxs-lookup"><span data-stu-id="7bbab-147">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="7bbab-148">Fornisce inoltre grafici che evidenziano l'impatto della minaccia per l'organizzazione e l'esposizione tramite dispositivi non configurati correttamente e senzapatch.</span><span class="sxs-lookup"><span data-stu-id="7bbab-148">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

![Immagine della sezione panoramica di un report di analisi delle minacce](../../media/threat-analytics/ta_overview_mtp.png)

<span data-ttu-id="7bbab-150">_Sezione Panoramica di un report di analisi delle minacce_</span><span class="sxs-lookup"><span data-stu-id="7bbab-150">_Overview section of a threat analytics report_</span></span>

#### <a name="assess-impact-on-your-organization"></a><span data-ttu-id="7bbab-151">Valutare l'impatto sull'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7bbab-151">Assess impact on your organization</span></span>

<span data-ttu-id="7bbab-152">Ogni report include grafici progettati per fornire informazioni sull'impatto organizzativo di una minaccia:</span><span class="sxs-lookup"><span data-stu-id="7bbab-152">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>

- <span data-ttu-id="7bbab-153">**Eventi imprevisti correlati:** offre una panoramica dell'impatto della minaccia rilevata per l'organizzazione con i dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bbab-153">**Related incidents**—provides an overview of the impact of the tracked threat to your organization with the following data:</span></span>
  - <span data-ttu-id="7bbab-154">Numero di avvisi attivi e numero di eventi imprevisti attivi a cui sono associati</span><span class="sxs-lookup"><span data-stu-id="7bbab-154">Number of active alerts and the number of active incidents they are associated with</span></span>
  - <span data-ttu-id="7bbab-155">Gravità degli eventi imprevisti attivi</span><span class="sxs-lookup"><span data-stu-id="7bbab-155">Severity of active incidents</span></span>
- <span data-ttu-id="7bbab-156">**Avvisi nel tempo:** mostra il numero di avvisi **attivi** **e risolti** correlati nel tempo.</span><span class="sxs-lookup"><span data-stu-id="7bbab-156">**Alerts over time**—shows the number of related **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="7bbab-157">Il numero di avvisi risolti indica la velocità con cui l'organizzazione risponde agli avvisi associati a una minaccia.</span><span class="sxs-lookup"><span data-stu-id="7bbab-157">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="7bbab-158">Idealmente, il grafico dovrebbe mostrare gli avvisi risolti entro pochi giorni.</span><span class="sxs-lookup"><span data-stu-id="7bbab-158">Ideally, the chart should be showing alerts resolved within a few days.</span></span>
- <span data-ttu-id="7bbab-159">**Asset influenzati:** mostra il numero di dispositivi distinti e account di posta elettronica (cassette postali) che attualmente hanno almeno un avviso attivo associato alla minaccia rilevata.</span><span class="sxs-lookup"><span data-stu-id="7bbab-159">**Impacted assets**—shows the number of distinct devices and email accounts (mailboxes) that currently have at least one active alert associated with the tracked threat.</span></span> <span data-ttu-id="7bbab-160">Gli avvisi vengono attivati per le cassette postali che hanno ricevuto messaggi di posta elettronica di minaccia.</span><span class="sxs-lookup"><span data-stu-id="7bbab-160">Alerts are triggered for mailboxes that received threat emails.</span></span> <span data-ttu-id="7bbab-161">Esaminare i criteri a livello di organizzazione e utente per le sostituzioni che causano il recapito dei messaggi di posta elettronica di minaccia.</span><span class="sxs-lookup"><span data-stu-id="7bbab-161">Review both org- and user-level policies for overrides that cause the delivery of threat emails.</span></span>
- <span data-ttu-id="7bbab-162">**Tentativi di posta elettronica** non consentiti: indica il numero di messaggi di posta elettronica degli ultimi sette giorni bloccati prima del recapito o recapitati nella cartella posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7bbab-162">**Prevented email attempts**—shows the number of emails from the past seven days that were either blocked before delivery or delivered to the junk mail folder.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="7bbab-163">Esaminare la resilienza e la postura della sicurezza</span><span class="sxs-lookup"><span data-stu-id="7bbab-163">Review security resilience and posture</span></span>

<span data-ttu-id="7bbab-164">Ogni report include grafici che forniscono una panoramica della resilienza dell'organizzazione rispetto a una determinata minaccia:</span><span class="sxs-lookup"><span data-stu-id="7bbab-164">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>

- <span data-ttu-id="7bbab-165">**Stato configurazione sicura:** indica il numero di dispositivi con impostazioni di sicurezza non configurate correttamente.</span><span class="sxs-lookup"><span data-stu-id="7bbab-165">**Secure configuration status**—shows the number of devices with misconfigured security settings.</span></span> <span data-ttu-id="7bbab-166">Applicare le impostazioni di sicurezza consigliate per attenuare la minaccia.</span><span class="sxs-lookup"><span data-stu-id="7bbab-166">Apply the recommended security settings to help mitigate the threat.</span></span> <span data-ttu-id="7bbab-167">I dispositivi sono **considerati sicuri** se hanno applicato _tutte_ le impostazioni rilevate.</span><span class="sxs-lookup"><span data-stu-id="7bbab-167">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="7bbab-168">**Stato patch vulnerabilità:** mostra il numero di dispositivi vulnerabili.</span><span class="sxs-lookup"><span data-stu-id="7bbab-168">**Vulnerability patching status**—shows the number of vulnerable devices.</span></span> <span data-ttu-id="7bbab-169">Applicare aggiornamenti della sicurezza o patch per risolvere le vulnerabilità sfruttate dalla minaccia.</span><span class="sxs-lookup"><span data-stu-id="7bbab-169">Apply security updates or patches to address vulnerabilities exploited by the threat.</span></span>

#### <a name="view-reports-per-threat-tags"></a><span data-ttu-id="7bbab-170">Visualizzare report per tag di minaccia</span><span class="sxs-lookup"><span data-stu-id="7bbab-170">View reports per threat tags</span></span>

<span data-ttu-id="7bbab-171">È possibile filtrare l'elenco dei report delle minacce e visualizzare i report più rilevanti in base a un tag specifico (categoria) o a un tipo di report.</span><span class="sxs-lookup"><span data-stu-id="7bbab-171">You can filter the threat report list and view the most relevant reports according to a specific threat tag (category) or a report type.</span></span>

- <span data-ttu-id="7bbab-172">**Tag per le** minacce: consente di visualizzare i report più rilevanti in base a una categoria di minacce specifica.</span><span class="sxs-lookup"><span data-stu-id="7bbab-172">**Threat tags**—assist you in viewing the most relevant reports according to a specific threat category.</span></span> <span data-ttu-id="7bbab-173">Ad esempio, tutti i report relativi al ransomware.</span><span class="sxs-lookup"><span data-stu-id="7bbab-173">For example, all reports related to ransomware.</span></span>
- <span data-ttu-id="7bbab-174">**Tipi di** report: consente di visualizzare i report più rilevanti in base a un tipo di report specifico.</span><span class="sxs-lookup"><span data-stu-id="7bbab-174">**Report types**—assist you in viewing the most relevant reports according to a specific report type.</span></span> <span data-ttu-id="7bbab-175">Ad esempio, tutti i report che coprono strumenti e tecniche.</span><span class="sxs-lookup"><span data-stu-id="7bbab-175">For example, all reports that cover tools and techniques.</span></span> 
- <span data-ttu-id="7bbab-176">**Filtri:** consente di esaminare in modo efficiente l'elenco dei report delle minacce e filtrare la visualizzazione in base a un tag o a un tipo di report specifico.</span><span class="sxs-lookup"><span data-stu-id="7bbab-176">**Filters**—assist you in efficiently reviewing the threat report list and filtering the view based on a specific threat tag or report type.</span></span> <span data-ttu-id="7bbab-177">Ad esempio, esaminare tutti i report sulle minacce correlati alla categoria ransomware o i report sulle minacce che coprono le vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="7bbab-177">For example, review all threat reports related to ransomware category, or threat reports that cover vulnerabilities.</span></span>

##### <a name="how-does-it-work"></a><span data-ttu-id="7bbab-178">Come funziona?</span><span class="sxs-lookup"><span data-stu-id="7bbab-178">How does it work?</span></span>

<span data-ttu-id="7bbab-179">Il team di Microsoft Threat Intelligence ha aggiunto tag di minaccia a ogni rapporto sulle minacce:</span><span class="sxs-lookup"><span data-stu-id="7bbab-179">The Microsoft Threat Intelligence team has added threat tags to each threat report:</span></span>

- <span data-ttu-id="7bbab-180">Sono ora disponibili quattro tag per le minacce:</span><span class="sxs-lookup"><span data-stu-id="7bbab-180">Four threat tags are now available:</span></span>
  - <span data-ttu-id="7bbab-181">Ransomware</span><span class="sxs-lookup"><span data-stu-id="7bbab-181">Ransomware</span></span>
  - <span data-ttu-id="7bbab-182">Phishing</span><span class="sxs-lookup"><span data-stu-id="7bbab-182">Phishing</span></span>
  - <span data-ttu-id="7bbab-183">Vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="7bbab-183">Vulnerability</span></span>
  - <span data-ttu-id="7bbab-184">Gruppo attività</span><span class="sxs-lookup"><span data-stu-id="7bbab-184">Activity group</span></span>
- <span data-ttu-id="7bbab-185">I tag delle minacce vengono presentati nella parte superiore della pagina di analisi delle minacce, con contatori per il numero di report disponibili in ogni tag.</span><span class="sxs-lookup"><span data-stu-id="7bbab-185">Threat tags are presented at the top of the threat analytics page, with counters for the number of available reports under each tag.</span></span>

  ![tag di minaccia](../../media/threat-analytics/ta-threattags-mtp.png)

- <span data-ttu-id="7bbab-187">L'elenco può anche essere ordinato in base ai tag delle minacce:</span><span class="sxs-lookup"><span data-stu-id="7bbab-187">The list can also be sorted by threat tags:</span></span>

  ![elenchi](../../media/threat-analytics//ta-taglist-mtp.png)

- <span data-ttu-id="7bbab-189">I filtri sono disponibili per ogni tag di minaccia e tipo di report:</span><span class="sxs-lookup"><span data-stu-id="7bbab-189">Filters are available per threat tag and report type:</span></span>

  ![filtri](../../media/threat-analytics/ta-threattag-filters-mtp.png)

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="7bbab-191">Report degli analisti: ottenere informazioni approfondite dai ricercatori di sicurezza Microsoft</span><span class="sxs-lookup"><span data-stu-id="7bbab-191">Analyst report: Get expert insight from Microsoft security researchers</span></span>

<span data-ttu-id="7bbab-192">Nella sezione **Report analista** leggere la descrizione dettagliata dell'esperto.</span><span class="sxs-lookup"><span data-stu-id="7bbab-192">In the **Analyst report** section, read through the detailed expert write-up.</span></span> <span data-ttu-id="7bbab-193">La maggior parte dei report fornisce descrizioni dettagliate delle catene di attacco, tra cui tattiche e tecniche mappate al framework CK di MITRE ATT&, elenchi esaustivi di suggerimenti e potenti indicazioni per la ricerca di [minacce.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7bbab-193">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="7bbab-194">Ulteriori informazioni sul report degli analisti</span><span class="sxs-lookup"><span data-stu-id="7bbab-194">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a><span data-ttu-id="7bbab-195">Eventi imprevisti correlati: visualizzare e gestire gli eventi imprevisti correlati</span><span class="sxs-lookup"><span data-stu-id="7bbab-195">Related incidents: View and manage related incidents</span></span>

<span data-ttu-id="7bbab-196">La **scheda Eventi imprevisti** correlati fornisce l'elenco di tutti gli eventi imprevisti correlati alla minaccia rilevata.</span><span class="sxs-lookup"><span data-stu-id="7bbab-196">The **Related incidents** tab provides the list of all incidents related to the tracked threat.</span></span> <span data-ttu-id="7bbab-197">È possibile assegnare eventi imprevisti o gestire gli avvisi collegati a ogni evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="7bbab-197">You can assign incidents or manage alerts linked to each incident.</span></span> 


![Immagine della sezione relativa agli eventi imprevisti di un report di analisi delle minacce](../../media/threat-analytics/ta_related_incidents_mtp.png)

<span data-ttu-id="7bbab-199">_Sezione Eventi imprevisti correlati di un report di analisi delle minacce_</span><span class="sxs-lookup"><span data-stu-id="7bbab-199">_Related incidents section of a threat analytics report_</span></span>

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a><span data-ttu-id="7bbab-200">Asset influenzati: ottenere l'elenco dei dispositivi e delle cassette postali influenzati</span><span class="sxs-lookup"><span data-stu-id="7bbab-200">Impacted assets: Get list of impacted devices and mailboxes</span></span>

<span data-ttu-id="7bbab-201">Un asset viene considerato interessato se è interessato da un avviso attivo e non risolto.</span><span class="sxs-lookup"><span data-stu-id="7bbab-201">An asset is considered impacted if it is affected by an active, unresolved alert.</span></span> <span data-ttu-id="7bbab-202">Nella **scheda Asset influenzati** sono elencati i seguenti tipi di asset influenzati:</span><span class="sxs-lookup"><span data-stu-id="7bbab-202">The **Impacted assets** tab lists the following types of impacted assets:</span></span>

- <span data-ttu-id="7bbab-203">**Dispositivi influenzati:** endpoint con avvisi di Microsoft Defender for Endpoint irrisolti.</span><span class="sxs-lookup"><span data-stu-id="7bbab-203">**Impacted devices**—endpoints that have unresolved Microsoft Defender for Endpoint alerts.</span></span> <span data-ttu-id="7bbab-204">Questi avvisi vengono in genere generati da avvistamenti di indicatori di minaccia e attività noti.</span><span class="sxs-lookup"><span data-stu-id="7bbab-204">These alerts typically fire on sightings of known threat indicators and activities.</span></span>
- <span data-ttu-id="7bbab-205">**Cassette postali influenzate:** cassette postali che hanno ricevuto messaggi di posta elettronica che hanno attivato Microsoft Defender per Office 365 avvisi.</span><span class="sxs-lookup"><span data-stu-id="7bbab-205">**Impacted mailboxes**—mailboxes that have received email messages that have triggered Microsoft Defender for Office 365 alerts.</span></span> <span data-ttu-id="7bbab-206">Sebbene la maggior parte dei messaggi che attivano avvisi sia in genere bloccata, i criteri a livello di utente o di organizzazione possono ignorare i filtri.</span><span class="sxs-lookup"><span data-stu-id="7bbab-206">While most messages that trigger alerts are typically blocked, user- or org-level policies can override filters.</span></span>

![Immagine della sezione relativa alle risorse influenzate di un report di analisi delle minacce](../../media/threat-analytics/ta_impacted_assets_mtp.png)

<span data-ttu-id="7bbab-208">_Sezione Asset influenzati di un report di analisi delle minacce_</span><span class="sxs-lookup"><span data-stu-id="7bbab-208">_Impacted assets section of a threat analytics report_</span></span>

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a><span data-ttu-id="7bbab-209">Tentativi di posta elettronica non consentiti: visualizzare i messaggi di posta elettronica di minacce bloccate o indesiderate</span><span class="sxs-lookup"><span data-stu-id="7bbab-209">Prevented email attempts: View blocked or junked threat emails</span></span>

<span data-ttu-id="7bbab-210">Microsoft Defender per Office 365 in genere blocca i messaggi di posta elettronica con indicatori di minaccia noti, inclusi collegamenti o allegati dannosi.</span><span class="sxs-lookup"><span data-stu-id="7bbab-210">Microsoft Defender for Office 365 typically blocks emails with known threat indicators, including malicious links or attachments.</span></span> <span data-ttu-id="7bbab-211">In alcuni casi, i meccanismi di filtro proattivi che controllano la presenza di contenuti sospetti invieranno invece messaggi di posta elettronica di minacce alla cartella posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="7bbab-211">In some cases, proactive filtering mechanisms that check for suspicious content will instead send threat emails to the junk mail folder.</span></span> <span data-ttu-id="7bbab-212">In entrambi i casi, le probabilità che la minaccia che avvia il codice malware sul dispositivo sia ridotta.</span><span class="sxs-lookup"><span data-stu-id="7bbab-212">In either case, the chances of the threat launching malware code on the device is reduced.</span></span>

<span data-ttu-id="7bbab-213">Nella **scheda Tentativi di posta elettronica** non consentiti sono elencati tutti i messaggi di posta elettronica bloccati prima del recapito o inviati alla cartella posta indesiderata da Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="7bbab-213">The **Prevented email attempts** tab lists all the emails that have either been blocked before delivery or sent to the junk mail folder by Microsoft Defender for Office 365.</span></span> 

![Immagine della sezione tentativi di posta elettronica non consentiti di un report di analisi delle minacce](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

<span data-ttu-id="7bbab-215">_Sezione Tentativi di posta elettronica non consentiti di un report di analisi delle minacce_</span><span class="sxs-lookup"><span data-stu-id="7bbab-215">_Prevented email attempts section of a threat analytics report_</span></span>

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="7bbab-216">Mitigazioni: esaminare l'elenco delle mitigazioni e lo stato dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="7bbab-216">Mitigations: Review list of mitigations and the status of your devices</span></span>

<span data-ttu-id="7bbab-217">Nella sezione **Mitigazioni** esaminare l'elenco di suggerimenti specifici che consentono di aumentare la resilienza dell'organizzazione contro la minaccia.</span><span class="sxs-lookup"><span data-stu-id="7bbab-217">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="7bbab-218">L'elenco delle mitigazioni rilevate include:</span><span class="sxs-lookup"><span data-stu-id="7bbab-218">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="7bbab-219">**Aggiornamenti della sicurezza:** distribuzione degli aggiornamenti della sicurezza software supportati per le vulnerabilità riscontrate nei dispositivi onboarded</span><span class="sxs-lookup"><span data-stu-id="7bbab-219">**Security updates**—deployment of supported software security updates for vulnerabilities found on onboarded devices</span></span>
- <span data-ttu-id="7bbab-220">**Configurazioni di sicurezza supportate**</span><span class="sxs-lookup"><span data-stu-id="7bbab-220">**Supported security configurations**</span></span>
  - <span data-ttu-id="7bbab-221">Protezione fornita dal cloud</span><span class="sxs-lookup"><span data-stu-id="7bbab-221">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="7bbab-222">Protezione delle applicazioni potenzialmente indesiderate</span><span class="sxs-lookup"><span data-stu-id="7bbab-222">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="7bbab-223">Protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="7bbab-223">Real-time protection</span></span>

<span data-ttu-id="7bbab-224">Le informazioni di mitigazione contenute in questa sezione incorporano i dati di [gestione di minacce e vulnerabilità](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), che forniscono inoltre informazioni dettagliate sul drill-down da vari collegamenti nel report.</span><span class="sxs-lookup"><span data-stu-id="7bbab-224">Mitigation information in this section incorporates data from [threat and vulnerability management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), which also provides detailed drill-down information from various links in the report.</span></span>

![Immagine della sezione mitigazioni di un report di analisi delle minacce che mostra i dettagli della configurazione sicura](../../media/threat-analytics/ta_mitigations_mtp.png)

![Immagine della sezione mitigazioni di un report di analisi delle minacce che mostra i dettagli della vulnerabilità](../../media/threat-analytics/ta_mitigations_mtp2.png)

<span data-ttu-id="7bbab-227">_Sezione Mitigazioni di un report di analisi delle minacce_</span><span class="sxs-lookup"><span data-stu-id="7bbab-227">_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="7bbab-228">Ulteriori dettagli e limitazioni del report</span><span class="sxs-lookup"><span data-stu-id="7bbab-228">Additional report details and limitations</span></span>

> [!NOTE]
> <span data-ttu-id="7bbab-229">Nell'ambito dell'esperienza di sicurezza unificata, l'analisi delle minacce è ora disponibile non solo per Microsoft Defender for Endpoint, ma anche per Microsoft Defender per i titolari di licenze Office E5.</span><span class="sxs-lookup"><span data-stu-id="7bbab-229">As part of the unified security experience, threat analytics is now available not just for Microsoft Defender for Endpoint, but also for Microsoft Defender for Office E5 license holders.</span></span>
>
> <span data-ttu-id="7bbab-230">Se non si utilizza il portale di sicurezza di Microsoft 365 (Microsoft 365 Defender), è anche possibile visualizzare i dettagli del report (senza i dati di Microsoft Defender per Office) nel portale di Microsoft Defender Security Center (Microsoft Defender per endpoint).</span><span class="sxs-lookup"><span data-stu-id="7bbab-230">If you are not using the Microsoft 365 security portal (Microsoft 365 Defender), you can also see the report details (without the Microsoft Defender for Office data) in the Microsoft Defender Security Center portal (Microsoft Defender for Endpoint).</span></span>

<span data-ttu-id="7bbab-231">Per accedere al report di analisi delle minacce sono necessari determinati ruoli e autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="7bbab-231">To access threat analytics report you need certain roles and permissions.</span></span> <span data-ttu-id="7bbab-232">Per [informazioni dettagliate, vedere Custom roles in role-based access control for Microsoft 365 Defender.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="7bbab-232">See [Custom roles in role-based access control for Microsoft 365 Defender](custom-roles.md) for details.</span></span>

- <span data-ttu-id="7bbab-233">Per visualizzare gli avvisi, gli eventi imprevisti o i dati degli asset a impatto, devi disporre delle autorizzazioni per Microsoft Defender per Office o i dati degli avvisi di Microsoft Defender per endpoint o entrambi.</span><span class="sxs-lookup"><span data-stu-id="7bbab-233">To view alerts, incidents, or impacted assets data, you need to have permissions to Microsoft Defender for Office or Microsoft Defender for Endpoint alerts data, or both.</span></span>
- <span data-ttu-id="7bbab-234">Per visualizzare i tentativi di posta elettronica non consentiti, è necessario disporre delle autorizzazioni per Microsoft Defender per Office dati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="7bbab-234">To view prevented email attempts, you need to have permissions to Microsoft Defender for Office hunting data.</span></span> 
- <span data-ttu-id="7bbab-235">Per visualizzare le mitigazioni, devi disporre delle autorizzazioni per gestione di minacce e vulnerabilità dati in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7bbab-235">To view mitigations, you need to have permissions to threat and vulnerability management data in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="7bbab-236">Quando si esaminano i dati di analisi delle minacce, tenere presente i fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bbab-236">When looking at the threat analytics data, remember the following factors:</span></span>

- <span data-ttu-id="7bbab-237">I grafici riflettono solo le mitigazioni rilevate.</span><span class="sxs-lookup"><span data-stu-id="7bbab-237">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="7bbab-238">Controllare la panoramica del report per ulteriori mitigazioni che non vengono visualizzate nei grafici.</span><span class="sxs-lookup"><span data-stu-id="7bbab-238">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="7bbab-239">Le mitigazioni non garantiscono resilienza completa.</span><span class="sxs-lookup"><span data-stu-id="7bbab-239">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="7bbab-240">Le mitigazioni fornite riflettono le migliori azioni possibili necessarie per migliorare la resilienza.</span><span class="sxs-lookup"><span data-stu-id="7bbab-240">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="7bbab-241">I dispositivi vengono conteggiati come "non disponibili" se non hanno trasmesso dati al servizio.</span><span class="sxs-lookup"><span data-stu-id="7bbab-241">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="7bbab-242">Le statistiche relative all'antivirus si basano Antivirus Microsoft Defender impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7bbab-242">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="7bbab-243">I dispositivi con soluzioni antivirus di terze parti possono apparire come "esposti".</span><span class="sxs-lookup"><span data-stu-id="7bbab-243">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="7bbab-244">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7bbab-244">Related topics</span></span>

- [<span data-ttu-id="7bbab-245">Trovare in modo proattivo le minacce con la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7bbab-245">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="7bbab-246">Informazioni sulla sezione relativa al report degli analisti</span><span class="sxs-lookup"><span data-stu-id="7bbab-246">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="7bbab-247">Valutare e risolvere i punti deboli e le esposizioni della sicurezza</span><span class="sxs-lookup"><span data-stu-id="7bbab-247">Assess and resolve security weaknesses and exposures</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
