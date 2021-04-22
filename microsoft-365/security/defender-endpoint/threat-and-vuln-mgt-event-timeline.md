---
title: Sequenza temporale degli eventi nella gestione delle minacce e delle vulnerabilità
description: La sequenza temporale degli eventi è un feed di notizie sui rischi che consente di interpretare il modo in cui i rischi vengono introdotti nell'organizzazione e quali mitigazioni si sono verificate per ridurlo.
keywords: sequenza temporale degli eventi, sequenza temporale degli eventi di Microsoft Defender for Endpoint, sequenza temporale degli eventi di Microsoft Defender for Endpoint tvm, gestione delle minacce e delle vulnerabilità, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 64362598ff4b0512eb110917071e6d32abb8ede9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933482"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a><span data-ttu-id="fa46b-104">Sequenza temporale degli eventi - Gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="fa46b-104">Event timeline - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fa46b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="fa46b-105">**Applies to:**</span></span>
- [<span data-ttu-id="fa46b-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="fa46b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="fa46b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa46b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fa46b-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="fa46b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fa46b-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="fa46b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="fa46b-110">La sequenza temporale degli eventi è un feed di notizie sui rischi che consente di interpretare il modo in cui i rischi vengono introdotti nell'organizzazione attraverso nuove vulnerabilità o exploit.</span><span class="sxs-lookup"><span data-stu-id="fa46b-110">Event timeline is a risk news feed that helps you interpret how risk is introduced into the organization through new vulnerabilities or exploits.</span></span> <span data-ttu-id="fa46b-111">È possibile visualizzare gli eventi che possono influire sui rischi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa46b-111">You can view events that may impact your organization's risk.</span></span> <span data-ttu-id="fa46b-112">Ad esempio, è possibile trovare nuove vulnerabilità introdotte, vulnerabilità che sono diventate sfruttabili, exploit che è stato aggiunto a un exploit kit e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="fa46b-112">For example, you can find new vulnerabilities that were introduced, vulnerabilities that became exploitable, exploit that was added to an exploit kit, and more.</span></span>

<span data-ttu-id="fa46b-113">La sequenza temporale dell'evento illustra anche la storia del punteggio di esposizione e [del punteggio microsoft sicuro](tvm-microsoft-secure-score-devices.md) per i dispositivi, in modo da poter determinare la causa di modifiche di grandi dimensioni. [](tvm-exposure-score.md)</span><span class="sxs-lookup"><span data-stu-id="fa46b-113">Event timeline also tells the story of your [exposure score](tvm-exposure-score.md) and [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) so you can determine the cause of large changes.</span></span> <span data-ttu-id="fa46b-114">Gli eventi possono influire sui dispositivi o sul punteggio per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fa46b-114">Events can impact your devices or your score for devices.</span></span> <span data-ttu-id="fa46b-115">Riduci l'esposizione affrontando gli elementi da correggere in base alle raccomandazioni sulla [sicurezza con priorità.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="fa46b-115">Reduce you exposure by addressing what needs to be remediated based on the prioritized [security recommendations](tvm-security-recommendation.md).</span></span>

>[!TIP]
><span data-ttu-id="fa46b-116">Per ricevere messaggi di posta elettronica sui nuovi eventi di vulnerabilità, vedere Configurare le notifiche di posta elettronica relative alla vulnerabilità [in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="fa46b-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-event-timeline-page"></a><span data-ttu-id="fa46b-117">Passare alla pagina Sequenza temporale eventi</span><span class="sxs-lookup"><span data-stu-id="fa46b-117">Navigate to the Event timeline page</span></span>

<span data-ttu-id="fa46b-118">Esistono anche tre punti di ingresso dal dashboard di gestione delle [minacce e delle vulnerabilità:](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="fa46b-118">There are also three entry points from the [threat and vulnerability management dashboard](tvm-dashboard-insights.md):</span></span>

- <span data-ttu-id="fa46b-119">**Scheda punteggio di esposizione** dell'organizzazione : passa il mouse sui punti dell'evento nel grafico "Punteggio di esposizione nel tempo" e seleziona "Vedi tutti gli eventi di questo giorno".</span><span class="sxs-lookup"><span data-stu-id="fa46b-119">**Organization exposure score card**: Hover over the event dots in the "Exposure Score over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="fa46b-120">Gli eventi rappresentano vulnerabilità software.</span><span class="sxs-lookup"><span data-stu-id="fa46b-120">The events represent software vulnerabilities.</span></span>
- <span data-ttu-id="fa46b-121">**Microsoft Secure Score for Devices**: passa il mouse sui punti dell'evento nel grafico "Il punteggio per i dispositivi nel tempo" e seleziona "Vedi tutti gli eventi di questo giorno".</span><span class="sxs-lookup"><span data-stu-id="fa46b-121">**Microsoft Secure Score for Devices**: Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="fa46b-122">Gli eventi rappresentano nuove valutazioni della configurazione.</span><span class="sxs-lookup"><span data-stu-id="fa46b-122">The events represent new configuration assessments.</span></span>
- <span data-ttu-id="fa46b-123">**Scheda Eventi principali:** seleziona "Mostra altro" nella parte inferiore della tabella degli eventi principali.</span><span class="sxs-lookup"><span data-stu-id="fa46b-123">**Top events card**: Select "Show more" at the bottom of the top events table.</span></span> <span data-ttu-id="fa46b-124">La scheda visualizza i tre eventi più importanti degli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="fa46b-124">The card displays the three most impactful events in the last 7 days.</span></span> <span data-ttu-id="fa46b-125">Gli eventi di impatto possono includere se l'evento interessa un numero elevato di dispositivi o se si tratta di una vulnerabilità critica.</span><span class="sxs-lookup"><span data-stu-id="fa46b-125">Impactful events can include if the event affects a large number of devices, or if it is a critical vulnerability.</span></span>

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a><span data-ttu-id="fa46b-126">Punteggio di esposizione e Microsoft Secure Score per i dispositivi grafici</span><span class="sxs-lookup"><span data-stu-id="fa46b-126">Exposure score and Microsoft Secure Score for Devices graphs</span></span>

<span data-ttu-id="fa46b-127">Nel dashboard di gestione delle minacce e delle vulnerabilità passa il puntatore del mouse sul grafico del punteggio di esposizione per visualizzare i principali eventi di vulnerabilità software di quel giorno che hanno interessato i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fa46b-127">In the threat and vulnerability management dashboard, hover over the Exposure score graph to view top software vulnerability events from that day that impacted your devices.</span></span> <span data-ttu-id="fa46b-128">Passa il puntatore del mouse sul grafico Microsoft Secure Score for Devices per visualizzare le nuove valutazioni della configurazione della sicurezza che influiscono sul punteggio.</span><span class="sxs-lookup"><span data-stu-id="fa46b-128">Hover over the Microsoft Secure Score for Devices graph to view new security configuration assessments that affect your score.</span></span>

<span data-ttu-id="fa46b-129">Se non sono presenti eventi che influiscono sui dispositivi o sul punteggio per i dispositivi, non verrà visualizzato alcun evento.</span><span class="sxs-lookup"><span data-stu-id="fa46b-129">If there are no events that affect your devices or your score for devices, then none will be shown.</span></span>

<span data-ttu-id="fa46b-130">![Punteggio di esposizione al passaggio ](images/tvm-event-timeline-exposure-score350.png) 
 ![ del mouse Microsoft Secure Score per dispositivi al passaggio del mouse](images/tvm-event-timeline-device-hover360.png)</span><span class="sxs-lookup"><span data-stu-id="fa46b-130">![Exposure score hover](images/tvm-event-timeline-exposure-score350.png) 
![Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span></span>

### <a name="drill-down-to-events-from-that-day"></a><span data-ttu-id="fa46b-131">Drill-down per gli eventi di quel giorno</span><span class="sxs-lookup"><span data-stu-id="fa46b-131">Drill down to events from that day</span></span>

<span data-ttu-id="fa46b-132">Selezionando **Mostra tutti gli eventi di questo giorno,** si visualizza la pagina Sequenza temporale eventi con un intervallo di date personalizzato per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="fa46b-132">Selecting **Show all events from this day** takes you to the Event timeline page with a custom date range for that day.</span></span>

![Intervallo di date personalizzato selezionato per la sequenza temporale degli eventi](images/tvm-event-timeline-drilldown.png)

<span data-ttu-id="fa46b-134">Selezionare **Intervallo personalizzato** per modificare l'intervallo di date in un altro intervallo personalizzato o in un intervallo di tempo pre-impostato.</span><span class="sxs-lookup"><span data-stu-id="fa46b-134">Select **Custom range** to change the date range to another custom one, or a pre-set time range.</span></span>

![Opzioni dell'intervallo di date della sequenza temporale degli eventi](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a><span data-ttu-id="fa46b-136">Panoramica della sequenza temporale degli eventi</span><span class="sxs-lookup"><span data-stu-id="fa46b-136">Event timeline overview</span></span>

<span data-ttu-id="fa46b-137">Nella pagina Sequenza temporale evento puoi visualizzare tutte le informazioni necessarie relative a un evento.</span><span class="sxs-lookup"><span data-stu-id="fa46b-137">On the Event timeline page, you can view the all the necessary info related to an event.</span></span> 

<span data-ttu-id="fa46b-138">Caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="fa46b-138">Features:</span></span>

- <span data-ttu-id="fa46b-139">Personalizzare le colonne</span><span class="sxs-lookup"><span data-stu-id="fa46b-139">Customize columns</span></span>
- <span data-ttu-id="fa46b-140">Filtrare in base al tipo di evento o alla percentuale dei dispositivi a cui è stato applicato l'impatto</span><span class="sxs-lookup"><span data-stu-id="fa46b-140">Filter by event type or percent of impacted devices</span></span>
- <span data-ttu-id="fa46b-141">Visualizzare 30, 50 o 100 elementi per pagina</span><span class="sxs-lookup"><span data-stu-id="fa46b-141">View 30, 50, or 100 items per page</span></span>

<span data-ttu-id="fa46b-142">I due numeri grandi nella parte superiore della pagina mostrano il numero di nuove vulnerabilità e vulnerabilità sfruttabili, non eventi.</span><span class="sxs-lookup"><span data-stu-id="fa46b-142">The two large numbers at the top of the page show the number of new vulnerabilities and exploitable vulnerabilities, not events.</span></span> <span data-ttu-id="fa46b-143">Alcuni eventi possono avere più vulnerabilità e altre possono avere più eventi.</span><span class="sxs-lookup"><span data-stu-id="fa46b-143">Some events can have multiple vulnerabilities, and some vulnerabilities can have multiple events.</span></span>

![Pagina Sequenza temporale eventi](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a><span data-ttu-id="fa46b-145">Colonne</span><span class="sxs-lookup"><span data-stu-id="fa46b-145">Columns</span></span>

- <span data-ttu-id="fa46b-146">**Data**: mese, giorno, anno</span><span class="sxs-lookup"><span data-stu-id="fa46b-146">**Date**: month, day, year</span></span>
- <span data-ttu-id="fa46b-147">**Evento:** evento di impatto, inclusi componenti, tipo e numero di dispositivi influenzati</span><span class="sxs-lookup"><span data-stu-id="fa46b-147">**Event**: impactful event, including component, type, and number of impacted devices</span></span>
- <span data-ttu-id="fa46b-148">**Componente correlato**: software</span><span class="sxs-lookup"><span data-stu-id="fa46b-148">**Related component**: software</span></span>
- <span data-ttu-id="fa46b-149">**Dispositivi originariamente influenzati:** il numero e la percentuale dei dispositivi a cui si è verificato l'evento in origine.</span><span class="sxs-lookup"><span data-stu-id="fa46b-149">**Originally impacted devices**: the number, and percentage, of impacted devices when this event originally occurred.</span></span> <span data-ttu-id="fa46b-150">Puoi anche filtrare in base alla percentuale di dispositivi originariamente influenzati, in base al numero totale di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fa46b-150">You can also filter by the percent of originally impacted devices, out of your total number of devices.</span></span>
- <span data-ttu-id="fa46b-151">**Dispositivi attualmente influenzati:** il numero corrente e la percentuale di dispositivi attualmente influenzati da questo evento.</span><span class="sxs-lookup"><span data-stu-id="fa46b-151">**Currently impacted devices**: the current number, and percentage, of devices that this event currently impacts.</span></span> <span data-ttu-id="fa46b-152">È possibile trovare questo campo selezionando **Personalizza colonne.**</span><span class="sxs-lookup"><span data-stu-id="fa46b-152">You can find this field by selecting **Customize columns**.</span></span>
- <span data-ttu-id="fa46b-153">**Tipi**: riflettono gli eventi con timestamp che influiscono sul punteggio.</span><span class="sxs-lookup"><span data-stu-id="fa46b-153">**Types**: reflect time-stamped events that impact the score.</span></span> <span data-ttu-id="fa46b-154">Possono essere filtrati.</span><span class="sxs-lookup"><span data-stu-id="fa46b-154">They can be filtered.</span></span>
    - <span data-ttu-id="fa46b-155">Exploit aggiunto a un exploit kit</span><span class="sxs-lookup"><span data-stu-id="fa46b-155">Exploit added to an exploit kit</span></span>
    - <span data-ttu-id="fa46b-156">Exploit verificato</span><span class="sxs-lookup"><span data-stu-id="fa46b-156">Exploit was verified</span></span>
    - <span data-ttu-id="fa46b-157">Nuovo exploit pubblico</span><span class="sxs-lookup"><span data-stu-id="fa46b-157">New public exploit</span></span>
    - <span data-ttu-id="fa46b-158">Nuova vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="fa46b-158">New vulnerability</span></span>
    - <span data-ttu-id="fa46b-159">Nuova valutazione della configurazione</span><span class="sxs-lookup"><span data-stu-id="fa46b-159">New configuration assessment</span></span>
- <span data-ttu-id="fa46b-160">**Tendenza del punteggio**: tendenza del punteggio di esposizione</span><span class="sxs-lookup"><span data-stu-id="fa46b-160">**Score trend**: exposure score trend</span></span>

### <a name="icons"></a><span data-ttu-id="fa46b-161">Icone</span><span class="sxs-lookup"><span data-stu-id="fa46b-161">Icons</span></span>

<span data-ttu-id="fa46b-162">Accanto agli eventi vengono visualizzate le icone seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa46b-162">The following icons show up next to events:</span></span>

- ![icona bug](images/tvm-black-bug-icon.png) <span data-ttu-id="fa46b-164">Nuovo exploit pubblico</span><span class="sxs-lookup"><span data-stu-id="fa46b-164">New public exploit</span></span>
- ![icona di avviso del report](images/report-warning-icon.png) <span data-ttu-id="fa46b-166">È stata pubblicata una nuova vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="fa46b-166">New vulnerability was published</span></span>
- ![exploit kit](images/bug-lightning-icon2.png) <span data-ttu-id="fa46b-168">Exploit trovato in exploit kit</span><span class="sxs-lookup"><span data-stu-id="fa46b-168">Exploit found in exploit kit</span></span>
- ![icona bug con icona di avviso](images/bug-caution-icon2.png) <span data-ttu-id="fa46b-170">Exploit verificato</span><span class="sxs-lookup"><span data-stu-id="fa46b-170">Exploit verified</span></span>

### <a name="drill-down-to-a-specific-event"></a><span data-ttu-id="fa46b-171">Eseguire il drill-down a un evento specifico</span><span class="sxs-lookup"><span data-stu-id="fa46b-171">Drill down to a specific event</span></span>

<span data-ttu-id="fa46b-172">Dopo aver selezionato un evento, verrà visualizzato un riquadro a comparsa con un elenco dei dettagli e dei CVE correnti che interessano i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fa46b-172">Once you select an event, a flyout will appear with a list of the details and current CVEs that affect your devices.</span></span> <span data-ttu-id="fa46b-173">È possibile visualizzare più CVE o visualizzare il suggerimento correlato.</span><span class="sxs-lookup"><span data-stu-id="fa46b-173">You can show more CVEs or view the related recommendation.</span></span>

<span data-ttu-id="fa46b-174">La freccia sotto "tendenza del punteggio" consente di determinare se questo evento ha generato o abbassato il punteggio di esposizione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa46b-174">The arrow below "score trend" helps you determine whether this event potentially raised or lowered your organizational exposure score.</span></span> <span data-ttu-id="fa46b-175">Un punteggio di esposizione più elevato indica che i dispositivi sono più vulnerabili allo sfruttamento.</span><span class="sxs-lookup"><span data-stu-id="fa46b-175">Higher exposure score means devices are more vulnerable to exploitation.</span></span>

![Riquadro a comparsa sequenza temporale eventi](images/tvm-event-timeline-flyout500.png)

<span data-ttu-id="fa46b-177">Da qui, selezionare **Vai a suggerimenti** sulla sicurezza correlati visualizzare il suggerimento che risolve la nuova vulnerabilità software nella pagina suggerimenti per la [sicurezza.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="fa46b-177">From there, select **Go to related security recommendation** view the recommendation that addresses the new software vulnerability in the [security recommendations page](tvm-security-recommendation.md).</span></span> <span data-ttu-id="fa46b-178">Dopo aver letto la descrizione e i dettagli della vulnerabilità nel suggerimento per la sicurezza, è possibile inviare una richiesta di correzione e tenere traccia della richiesta nella pagina [di correzione.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="fa46b-178">After reading the description and vulnerability details in the security recommendation, you can submit a remediation request, and track the request in the [remediation page](tvm-remediation.md).</span></span>  

## <a name="view-event-timelines-in-software-pages"></a><span data-ttu-id="fa46b-179">Visualizzazione delle sequenze temporali degli eventi nelle pagine software</span><span class="sxs-lookup"><span data-stu-id="fa46b-179">View Event timelines in software pages</span></span>

<span data-ttu-id="fa46b-180">Per aprire una pagina software, seleziona un evento > seleziona il nome del software con collegamento ipertestuale (ad esempio Visual Studio 2017) nella sezione denominata "Componente correlato" nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="fa46b-180">To open a software page, select an event > select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout.</span></span> [<span data-ttu-id="fa46b-181">Altre informazioni sulle pagine software</span><span class="sxs-lookup"><span data-stu-id="fa46b-181">Learn more about software pages</span></span>](tvm-software-inventory.md#software-pages)

<span data-ttu-id="fa46b-182">Verrà visualizzata una pagina intera con tutti i dettagli di un software specifico.</span><span class="sxs-lookup"><span data-stu-id="fa46b-182">A full page will appear with all the details of a specific software.</span></span> <span data-ttu-id="fa46b-183">Passa il mouse sul grafico per visualizzare la sequenza temporale degli eventi per quel software specifico.</span><span class="sxs-lookup"><span data-stu-id="fa46b-183">Mouse over the graph to see the timeline of events for that specific software.</span></span>

![Pagina Software con un grafico sequenza temporale eventi](images/tvm-event-timeline-software2.png)

<span data-ttu-id="fa46b-185">Passare alla scheda sequenza temporale dell'evento per visualizzare tutti gli eventi correlati a tale software.</span><span class="sxs-lookup"><span data-stu-id="fa46b-185">Navigate to the event timeline tab to view all the events related to that software.</span></span> <span data-ttu-id="fa46b-186">Puoi anche visualizzare consigli sulla sicurezza, vulnerabilità individuate, dispositivi installati e distribuzione delle versioni.</span><span class="sxs-lookup"><span data-stu-id="fa46b-186">You can also see security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span>

![Pagina Software con una scheda Sequenza temporale eventi](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a><span data-ttu-id="fa46b-188">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fa46b-188">Related topics</span></span>

- [<span data-ttu-id="fa46b-189">Panoramica della gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="fa46b-189">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="fa46b-190">Dashboard</span><span class="sxs-lookup"><span data-stu-id="fa46b-190">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="fa46b-191">Punteggio di esposizione.</span><span class="sxs-lookup"><span data-stu-id="fa46b-191">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="fa46b-192">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="fa46b-192">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="fa46b-193">Correggere le vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="fa46b-193">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="fa46b-194">Inventario software</span><span class="sxs-lookup"><span data-stu-id="fa46b-194">Software inventory</span></span>](tvm-software-inventory.md)

