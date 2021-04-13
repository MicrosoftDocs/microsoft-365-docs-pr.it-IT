---
title: Tenere traccia e rispondere alle minacce emergenti con Microsoft Defender for Endpoint Threat Analytics
ms.reviewer: ''
description: Informazioni sulle minacce emergenti e sulle tecniche di attacco e su come arrestarle. Valutarne l'impatto sull'organizzazione e valutare la resilienza dell'organizzazione.
keywords: analisi delle minacce, valutazione dei rischi, mitigazione del sistema operativo, mitigazione del microcodice, stato di mitigazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 61b6b0c19730045468c77e5f24bf18470aa5dbd5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688262"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="3dad2-105">Tenere traccia e rispondere alle minacce emergenti con l'analisi delle minacce</span><span class="sxs-lookup"><span data-stu-id="3dad2-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3dad2-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3dad2-106">**Applies to:**</span></span>
- [<span data-ttu-id="3dad2-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="3dad2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3dad2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3dad2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3dad2-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3dad2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3dad2-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="3dad2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3dad2-111">Con gli avversari più sofisticati e le nuove minacce che emergono spesso e prevalentemente, è fondamentale essere in grado di:</span><span class="sxs-lookup"><span data-stu-id="3dad2-111">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="3dad2-112">Valutare l'impatto delle nuove minacce</span><span class="sxs-lookup"><span data-stu-id="3dad2-112">Assess the impact of new threats</span></span>
- <span data-ttu-id="3dad2-113">Esaminare la resilienza o l'esposizione alle minacce</span><span class="sxs-lookup"><span data-stu-id="3dad2-113">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="3dad2-114">Identificare le azioni che è possibile eseguire per arrestare o contenere le minacce</span><span class="sxs-lookup"><span data-stu-id="3dad2-114">Identify the actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="3dad2-115">L'analisi delle minacce è una serie di report di esperti ricercatori di sicurezza Microsoft che coprono le minacce più rilevanti, tra cui:</span><span class="sxs-lookup"><span data-stu-id="3dad2-115">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats, including:</span></span>

- <span data-ttu-id="3dad2-116">Attori delle minacce attive e le loro campagne</span><span class="sxs-lookup"><span data-stu-id="3dad2-116">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="3dad2-117">Tecniche di attacco popolari e nuove</span><span class="sxs-lookup"><span data-stu-id="3dad2-117">Popular and new attack techniques</span></span>
- <span data-ttu-id="3dad2-118">Vulnerabilità critiche</span><span class="sxs-lookup"><span data-stu-id="3dad2-118">Critical vulnerabilities</span></span>
- <span data-ttu-id="3dad2-119">Superfici di attacco comuni</span><span class="sxs-lookup"><span data-stu-id="3dad2-119">Common attack surfaces</span></span>
- <span data-ttu-id="3dad2-120">Malware diffuso</span><span class="sxs-lookup"><span data-stu-id="3dad2-120">Prevalent malware</span></span>

<span data-ttu-id="3dad2-121">Ogni report fornisce un'analisi dettagliata di una minaccia e indicazioni dettagliate su come difendersi da tale minaccia.</span><span class="sxs-lookup"><span data-stu-id="3dad2-121">Each report provides a detailed analysis of a threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="3dad2-122">Incorpora inoltre i dati della rete, che indicano se la minaccia è attiva e se sono presenti protezioni applicabili.</span><span class="sxs-lookup"><span data-stu-id="3dad2-122">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

<span data-ttu-id="3dad2-123">Guarda questo breve video per saperne di più su come l'analisi delle minacce può aiutarti a tenere traccia delle minacce più recenti e a fermarle.</span><span class="sxs-lookup"><span data-stu-id="3dad2-123">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="3dad2-124">Visualizzare il dashboard di analisi delle minacce</span><span class="sxs-lookup"><span data-stu-id="3dad2-124">View the threat analytics dashboard</span></span>

<span data-ttu-id="3dad2-125">Il dashboard di analisi delle minacce è un ottimo punto di partenza per accedere ai report più rilevanti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3dad2-125">The threat analytics dashboard is a great jump off point for getting to the reports that are most relevant to your organization.</span></span> <span data-ttu-id="3dad2-126">Riepiloga le minacce nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3dad2-126">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="3dad2-127">**Minacce più** recenti: elenca i report sulle minacce pubblicati più di recente, insieme al numero di dispositivi con avvisi attivi e risolti.</span><span class="sxs-lookup"><span data-stu-id="3dad2-127">**Latest threats**—lists the most recently published threat reports, along with the number of devices with active and resolved alerts.</span></span>
- <span data-ttu-id="3dad2-128">**Minacce ad alto impatto:** elenca le minacce che hanno avuto il massimo impatto sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3dad2-128">**High-impact threats**—lists the threats that have had the highest impact to the organization.</span></span> <span data-ttu-id="3dad2-129">Questa sezione classifica le minacce in base al numero di dispositivi con avvisi attivi.</span><span class="sxs-lookup"><span data-stu-id="3dad2-129">This section ranks threats by the number of devices that have active alerts.</span></span>
- <span data-ttu-id="3dad2-130">**Riepilogo delle** minacce: mostra l'impatto complessivo delle minacce rilevate mostrando il numero di minacce con avvisi attivi e risolti.</span><span class="sxs-lookup"><span data-stu-id="3dad2-130">**Threat summary**—shows the overall impact of tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="3dad2-131">Selezionare una minaccia dal dashboard per visualizzare il report per tale minaccia.</span><span class="sxs-lookup"><span data-stu-id="3dad2-131">Select a threat from the dashboard to view the report for that threat.</span></span>

![Immagine di un dashboard di analisi delle minacce](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="3dad2-133">Visualizzare un report di analisi delle minacce</span><span class="sxs-lookup"><span data-stu-id="3dad2-133">View a threat analytics report</span></span>

<span data-ttu-id="3dad2-134">Ogni report di analisi delle minacce fornisce informazioni in tre sezioni: **Panoramica,** **Report analista** e **Mitigazioni.**</span><span class="sxs-lookup"><span data-stu-id="3dad2-134">Each threat analytics report provides information in three sections: **Overview**, **Analyst report**, and **Mitigations**.</span></span>

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="3dad2-135">Panoramica: comprendere rapidamente la minaccia, valutarne l'impatto ed esaminare le difese</span><span class="sxs-lookup"><span data-stu-id="3dad2-135">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="3dad2-136">La **sezione Panoramica** offre un'anteprima del report dettagliato degli analisti.</span><span class="sxs-lookup"><span data-stu-id="3dad2-136">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="3dad2-137">Fornisce inoltre grafici che evidenziano l'impatto della minaccia per l'organizzazione e l'esposizione tramite dispositivi non configurati correttamente e senzapatch.</span><span class="sxs-lookup"><span data-stu-id="3dad2-137">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

<span data-ttu-id="3dad2-138">![Immagine della sezione panoramica di un report di analisi delle minacce ](images/ta-overview.png)
 _Sezione Panoramica di un report di analisi delle minacce_</span><span class="sxs-lookup"><span data-stu-id="3dad2-138">![Image of the overview section of a threat analytics report](images/ta-overview.png)
_Overview section of a threat analytics report_</span></span>

#### <a name="assess-the-impact-to-your-organization"></a><span data-ttu-id="3dad2-139">Valutare l'impatto sull'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3dad2-139">Assess the impact to your organization</span></span>
<span data-ttu-id="3dad2-140">Ogni report include grafici progettati per fornire informazioni sull'impatto organizzativo di una minaccia:</span><span class="sxs-lookup"><span data-stu-id="3dad2-140">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="3dad2-141">**Dispositivi con avvisi:** mostra il numero corrente di dispositivi distinti che sono stati influenzati dalla minaccia.</span><span class="sxs-lookup"><span data-stu-id="3dad2-141">**Devices with alerts**—shows the current number of distinct devices that have been impacted by the threat.</span></span> <span data-ttu-id="3dad2-142">Un dispositivo viene classificato come **Attivo** se alla minaccia è associato  almeno un avviso e **Risolto** se tutti gli avvisi associati alla minaccia nel dispositivo sono stati risolti.</span><span class="sxs-lookup"><span data-stu-id="3dad2-142">A device is categorized as **Active** if there is at least one alert associated with that threat and **Resolved** if *all* alerts associated with the threat on the device have been resolved.</span></span>
- <span data-ttu-id="3dad2-143">**Dispositivi con avvisi nel tempo:** mostra il numero di dispositivi distinti con **avvisi attivi** **e** risolti nel tempo.</span><span class="sxs-lookup"><span data-stu-id="3dad2-143">**Devices with alerts over time**—shows the number of distinct devices with **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="3dad2-144">Il numero di avvisi risolti indica la velocità con cui l'organizzazione risponde agli avvisi associati a una minaccia.</span><span class="sxs-lookup"><span data-stu-id="3dad2-144">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="3dad2-145">Idealmente, il grafico dovrebbe mostrare gli avvisi risolti entro pochi giorni.</span><span class="sxs-lookup"><span data-stu-id="3dad2-145">Ideally, the chart should be showing alerts resolved within a few days.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="3dad2-146">Esaminare la resilienza e la postura della sicurezza</span><span class="sxs-lookup"><span data-stu-id="3dad2-146">Review security resilience and posture</span></span>
<span data-ttu-id="3dad2-147">Ogni report include grafici che forniscono una panoramica della resilienza dell'organizzazione rispetto a una determinata minaccia:</span><span class="sxs-lookup"><span data-stu-id="3dad2-147">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="3dad2-148">**Stato della configurazione della** sicurezza: mostra il numero di dispositivi che hanno applicato le impostazioni di sicurezza consigliate che possono contribuire a ridurre la minaccia.</span><span class="sxs-lookup"><span data-stu-id="3dad2-148">**Security configuration status**—shows the number of devices that have applied the recommended security settings that can help mitigate the threat.</span></span> <span data-ttu-id="3dad2-149">I dispositivi sono **considerati sicuri** se hanno applicato _tutte_ le impostazioni rilevate.</span><span class="sxs-lookup"><span data-stu-id="3dad2-149">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="3dad2-150">**Stato applicazione di patch** alle vulnerabilità: mostra il numero di dispositivi che hanno applicato aggiornamenti della sicurezza o patch che affrontano le vulnerabilità sfruttate dalla minaccia.</span><span class="sxs-lookup"><span data-stu-id="3dad2-150">**Vulnerability patching status**—shows the number of devices that have applied security updates or patches that address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="3dad2-151">Report degli analisti: ottenere informazioni approfondite dai ricercatori di sicurezza Microsoft</span><span class="sxs-lookup"><span data-stu-id="3dad2-151">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="3dad2-152">Vai alla sezione **Report analista** per leggere la dettagliata scrittura di esperti.</span><span class="sxs-lookup"><span data-stu-id="3dad2-152">Go to the **Analyst report** section to read through the detailed expert write-up.</span></span> <span data-ttu-id="3dad2-153">La maggior parte dei report fornisce descrizioni dettagliate delle catene di attacco, tra cui tattiche e tecniche mappate al framework CK di MITRE ATT&, elenchi esaustivi di suggerimenti e potenti indicazioni per la ricerca di [minacce.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3dad2-153">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="3dad2-154">Ulteriori informazioni sul report degli analisti</span><span class="sxs-lookup"><span data-stu-id="3dad2-154">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="3dad2-155">Mitigazioni: esaminare l'elenco delle mitigazioni e lo stato dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="3dad2-155">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="3dad2-156">Nella sezione **Mitigazioni** esaminare l'elenco di suggerimenti specifici che consentono di aumentare la resilienza dell'organizzazione contro la minaccia.</span><span class="sxs-lookup"><span data-stu-id="3dad2-156">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="3dad2-157">L'elenco delle mitigazioni rilevate include:</span><span class="sxs-lookup"><span data-stu-id="3dad2-157">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="3dad2-158">**Aggiornamenti della sicurezza:** distribuzione di aggiornamenti della sicurezza o patch per le vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="3dad2-158">**Security updates**—deployment of security updates or patches for vulnerabilities</span></span>
- <span data-ttu-id="3dad2-159">**Impostazioni di Microsoft Defender Antivirus**</span><span class="sxs-lookup"><span data-stu-id="3dad2-159">**Microsoft Defender Antivirus settings**</span></span>
  - <span data-ttu-id="3dad2-160">Versione di Security Intelligence</span><span class="sxs-lookup"><span data-stu-id="3dad2-160">Security intelligence version</span></span>
  - <span data-ttu-id="3dad2-161">Protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="3dad2-161">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="3dad2-162">Protezione delle applicazioni potenzialmente indesiderate</span><span class="sxs-lookup"><span data-stu-id="3dad2-162">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="3dad2-163">Protezione in tempo reale</span><span class="sxs-lookup"><span data-stu-id="3dad2-163">Real-time protection</span></span>
 
<span data-ttu-id="3dad2-164">Le informazioni di mitigazione contenute in questa sezione incorporano i dati della gestione delle minacce e delle [vulnerabilità,](next-gen-threat-and-vuln-mgt.md)che forniscono inoltre informazioni dettagliate di drill-down da vari collegamenti nel report.</span><span class="sxs-lookup"><span data-stu-id="3dad2-164">Mitigation information in this section incorporates data from [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="3dad2-165">![Immagine della sezione mitigazioni di un report di analisi delle minacce ](images/ta-mitigations.png)
 _Sezione Mitigazioni di un report di analisi delle minacce_</span><span class="sxs-lookup"><span data-stu-id="3dad2-165">![Image of the mitigations section of a threat analytics report](images/ta-mitigations.png)
_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="3dad2-166">Ulteriori dettagli e limitazioni del report</span><span class="sxs-lookup"><span data-stu-id="3dad2-166">Additional report details and limitations</span></span>
<span data-ttu-id="3dad2-167">Quando si utilizzano i report, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3dad2-167">When using the reports, keep the following in mind:</span></span> 

- <span data-ttu-id="3dad2-168">L'ambito dei dati è basato sull'ambito RBAC (Role-Based Access Control).</span><span class="sxs-lookup"><span data-stu-id="3dad2-168">Data is scoped based on your role-based access control (RBAC) scope.</span></span> <span data-ttu-id="3dad2-169">Verrà visualizzato lo stato dei dispositivi in [gruppi a cui è possibile accedere.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="3dad2-169">You will see the status of devices in [groups that you can access](machine-groups.md).</span></span>
- <span data-ttu-id="3dad2-170">I grafici riflettono solo le mitigazioni rilevate.</span><span class="sxs-lookup"><span data-stu-id="3dad2-170">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="3dad2-171">Controllare la panoramica del report per ulteriori mitigazioni che non vengono visualizzate nei grafici.</span><span class="sxs-lookup"><span data-stu-id="3dad2-171">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="3dad2-172">Le mitigazioni non garantiscono resilienza completa.</span><span class="sxs-lookup"><span data-stu-id="3dad2-172">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="3dad2-173">Le mitigazioni fornite riflettono le migliori azioni possibili necessarie per migliorare la resilienza.</span><span class="sxs-lookup"><span data-stu-id="3dad2-173">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="3dad2-174">I dispositivi vengono conteggiati come "non disponibili" se non hanno trasmesso dati al servizio.</span><span class="sxs-lookup"><span data-stu-id="3dad2-174">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="3dad2-175">Le statistiche relative all'antivirus si basano sulle impostazioni di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="3dad2-175">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="3dad2-176">I dispositivi con soluzioni antivirus di terze parti possono apparire come "esposti".</span><span class="sxs-lookup"><span data-stu-id="3dad2-176">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="3dad2-177">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3dad2-177">Related topics</span></span>
- [<span data-ttu-id="3dad2-178">Trovare in modo proattivo le minacce con la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="3dad2-178">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="3dad2-179">Informazioni sulla sezione relativa al report degli analisti</span><span class="sxs-lookup"><span data-stu-id="3dad2-179">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="3dad2-180">Valutare e risolvere i punti deboli e le esposizioni della sicurezza</span><span class="sxs-lookup"><span data-stu-id="3dad2-180">Assess and resolve security weaknesses and exposures</span></span>](next-gen-threat-and-vuln-mgt.md)