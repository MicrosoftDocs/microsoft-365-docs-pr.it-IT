---
title: Microsoft 365 Insights Network (anteprima)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Insights Network (anteprima)
ms.openlocfilehash: 9e324af8ea2b81d0ca672b079afc74bededce695
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200770"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="71023-103">Microsoft 365 Insights Network (anteprima)</span><span class="sxs-lookup"><span data-stu-id="71023-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="71023-104">Le **informazioni sulla rete** sono metriche delle prestazioni raccolte dal tenant Microsoft 365 e sono disponibili per la visualizzazione solo da parte di utenti amministrativi del tenant.</span><span class="sxs-lookup"><span data-stu-id="71023-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="71023-105">Le informazioni dettagliate vengono visualizzate nell'interfaccia di amministrazione di Microsoft 365 all'indirizzo <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="71023-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="71023-106">Gli Insight sono destinati a facilitare la progettazione di perimetri di rete per le posizioni di Office.</span><span class="sxs-lookup"><span data-stu-id="71023-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="71023-107">Ogni Insight fornisce informazioni dettagliate sulle caratteristiche delle prestazioni per un problema comune specifico per ogni posizione geografica in cui gli utenti accedono al tenant.</span><span class="sxs-lookup"><span data-stu-id="71023-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="71023-108">Sono presenti sei informazioni specifiche sulla rete che possono essere visualizzate per ogni percorso di Office:</span><span class="sxs-lookup"><span data-stu-id="71023-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="71023-109">Uscita di rete con backhauling</span><span class="sxs-lookup"><span data-stu-id="71023-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="71023-110">Migliorare le prestazioni rilevate per i clienti nelle vicinanze</span><span class="sxs-lookup"><span data-stu-id="71023-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="71023-111">Utilizzo di una porta anteriore del servizio Exchange Online non ottimale</span><span class="sxs-lookup"><span data-stu-id="71023-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="71023-112">Utilizzo di una porta principale del servizio SharePoint Online non ottimale</span><span class="sxs-lookup"><span data-stu-id="71023-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="71023-113">Velocità di download bassa dalla porta di ingresso di SharePoint</span><span class="sxs-lookup"><span data-stu-id="71023-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="71023-114">Uscita di rete ottimale per gli utenti cinesi</span><span class="sxs-lookup"><span data-stu-id="71023-114">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="71023-115">Sono disponibili due informazioni di rete a livello di tenant che è possibile visualizzare per il tenant.</span><span class="sxs-lookup"><span data-stu-id="71023-115">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="71023-116">Sono inoltre presenti nelle pagine del Punteggio di producvitivy:</span><span class="sxs-lookup"><span data-stu-id="71023-116">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="71023-117">Connessioni con campionamento di Exchange interessate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="71023-117">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="71023-118">Connessioni con campionamento di SharePoint influenzate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="71023-118">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="71023-119">Insights di rete, raccomandazioni sulle prestazioni e valutazioni nell'interfaccia di amministrazione di Microsoft 365 è attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 che sono stati registrati nel programma di anteprima delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="71023-119">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="71023-120">Uscita di rete con backhauling</span><span class="sxs-lookup"><span data-stu-id="71023-120">Backhauled network egress</span></span>

<span data-ttu-id="71023-121">Questa intuizione verrà visualizzata se il servizio Network Insights rileva che la distanza tra un determinato percorso utente e l'uscita di rete è superiore a 500 miglia (800 km), a indicare che il traffico di Microsoft 365 viene reindirizzato a un normale dispositivo o proxy di Internet Edge.</span><span class="sxs-lookup"><span data-stu-id="71023-121">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="71023-122">Questa intuizione è abbreviata in "uscita" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="71023-122">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Uscita di rete con backhauling](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="71023-124">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="71023-124">What does this mean?</span></span>

<span data-ttu-id="71023-125">Ciò indica che la distanza tra l'area di lavoro e l'uscita di rete è superiore a 500 miglia (800 km).</span><span class="sxs-lookup"><span data-stu-id="71023-125">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="71023-126">La posizione di Office è identificata da una posizione del computer client offuscata e il percorso dell'uscita di rete viene identificato utilizzando l'indirizzo IP inverso nei database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="71023-126">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="71023-127">La posizione di Office potrebbe non essere accurata se i servizi di posizione di Windows sono disabilitati nei computer.</span><span class="sxs-lookup"><span data-stu-id="71023-127">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="71023-128">La posizione di uscita della rete potrebbe non essere accurata se le informazioni sul database degli indirizzi IP inversi non sono accurate.</span><span class="sxs-lookup"><span data-stu-id="71023-128">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="71023-129">Per informazioni dettagliate su questa panoramica, vedere l'ubicazione dell'ufficio, la percentuale stimata dell'utente tenant totale nel percorso, la posizione corrente di uscita della rete, la pertinenza del percorso di uscita, la distanza tra la posizione e il punto di uscita corrente, la data in cui è stata rilevata la condizione e la data in cui è stata risolta la condizione.</span><span class="sxs-lookup"><span data-stu-id="71023-129">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="71023-130">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="71023-130">What should I do?</span></span>

<span data-ttu-id="71023-131">Per questa intuizione, è consigliabile utilizzare l'uscita di rete più vicina alla posizione di Office in modo che la connettività possa essere instradata in maniera ottimale alla rete globale di Microsoft e alla porta principale del servizio Microsoft 365 più vicina.</span><span class="sxs-lookup"><span data-stu-id="71023-131">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="71023-132">Dopo aver chiuso l'uscita di rete per gli utenti, le posizioni di Office consentono anche di migliorare le prestazioni in futuro, in quanto Microsoft espande entrambi i punti di rete di presenza e le porte frontali del servizio Microsoft 365 in futuro.</span><span class="sxs-lookup"><span data-stu-id="71023-132">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="71023-133">Per ulteriori informazioni su come risolvere il problema, vedere l'argomento relativo alle [connessioni di rete in uscita localmente](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) nei [principi di connettività di rete di Office 365](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="71023-133">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="71023-134">Migliorare le prestazioni rilevate per i clienti nelle vicinanze</span><span class="sxs-lookup"><span data-stu-id="71023-134">Better performance detected for customers near you</span></span>

<span data-ttu-id="71023-135">Questa intuizione verrà visualizzata se il servizio Network Insights rileva che un numero significativo di clienti nell'area metropolitana ha prestazioni migliori rispetto a quelle degli utenti dell'organizzazione in questa posizione di ufficio.</span><span class="sxs-lookup"><span data-stu-id="71023-135">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="71023-136">Questa intuizione è abbreviata in "peer" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="71023-136">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Prestazioni di rete relative](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="71023-138">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="71023-138">What does this mean?</span></span>

<span data-ttu-id="71023-139">In questa panoramica vengono esaminate le prestazioni aggregate dei clienti di Microsoft 365 nella stessa città del percorso di Office.</span><span class="sxs-lookup"><span data-stu-id="71023-139">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="71023-140">Questa intuizione viene visualizzata se la latenza media degli utenti è superiore del 10% rispetto alla media latenza dei tenant limitrofi.</span><span class="sxs-lookup"><span data-stu-id="71023-140">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="71023-141">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="71023-141">What should I do?</span></span>

<span data-ttu-id="71023-142">Sono possibili molti motivi per questa condizione, tra cui la latenza della rete aziendale o dell'ISP, i colli di bottiglia o i problemi di progettazione dell'architettura.</span><span class="sxs-lookup"><span data-stu-id="71023-142">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="71023-143">Esaminare la latenza tra ogni hop del percorso tra la rete aziendale e l'attuale porta principale di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="71023-143">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="71023-144">Per ulteriori informazioni, vedere [principi di connettività di rete di Office 365](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="71023-144">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="71023-145">Utilizzo di una porta anteriore del servizio Exchange Online non ottimale</span><span class="sxs-lookup"><span data-stu-id="71023-145">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="71023-146">Questa intuizione verrà visualizzata se il servizio Network Insights rileva che gli utenti in una posizione specifica non si connettono a un front door del servizio Exchange Online ottimale.</span><span class="sxs-lookup"><span data-stu-id="71023-146">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="71023-147">Questa intuizione è abbreviata in "routing" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="71023-147">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Porta anteriore EXO non ottimale](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="71023-149">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="71023-149">What does this mean?</span></span>

<span data-ttu-id="71023-150">Vengono elencate le porte anteriori del servizio Exchange Online che sono adatte per l'utilizzo da parte di Office location City con buone prestazioni.</span><span class="sxs-lookup"><span data-stu-id="71023-150">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="71023-151">Se il test corrente Mostra l'utilizzo di una porta di ingresso del servizio Exchange Online non presente nell'elenco, verrà chiamato questo suggerimento.</span><span class="sxs-lookup"><span data-stu-id="71023-151">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="71023-152">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="71023-152">What should I do?</span></span>

<span data-ttu-id="71023-153">L'utilizzo di una porta anteriore del servizio Exchange Online non ottimale può essere causato da un backhaul della rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita di rete locale e diretta.</span><span class="sxs-lookup"><span data-stu-id="71023-153">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="71023-154">Potrebbe anche essere causato dall'utilizzo di un server resolver DNS ricorsivo remoto, nel qual caso si consiglia di allineare il server resolver ricorsivo DNS con l'uscita di rete.</span><span class="sxs-lookup"><span data-stu-id="71023-154">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="71023-155">Utilizzo di una porta principale del servizio SharePoint Online non ottimale</span><span class="sxs-lookup"><span data-stu-id="71023-155">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="71023-156">Questa intuizione verrà visualizzata se il servizio Network Insights rileva che gli utenti in una posizione specifica non si connettono al portale principale del servizio SharePoint Online più vicino.</span><span class="sxs-lookup"><span data-stu-id="71023-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="71023-157">Questa intuizione è abbreviata in "AFD" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="71023-157">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Porta anteriore non ottimale per SPO](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="71023-159">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="71023-159">What does this mean?</span></span>

<span data-ttu-id="71023-160">Identificare la porta di ingresso del servizio SharePoint Online a cui si connette il client di test.</span><span class="sxs-lookup"><span data-stu-id="71023-160">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="71023-161">Quindi, per la città Ubicazione di Office, viene confrontato con il servizio SharePoint Online previsto per la città.</span><span class="sxs-lookup"><span data-stu-id="71023-161">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="71023-162">In caso contrario, è consigliabile eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="71023-162">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="71023-163">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="71023-163">What should I do?</span></span>

<span data-ttu-id="71023-164">L'utilizzo di un servizio di SharePoint Online non ottimale può essere causato da un backhaul della rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita di rete locale e diretta.</span><span class="sxs-lookup"><span data-stu-id="71023-164">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="71023-165">Potrebbe anche essere causato dall'utilizzo di un server resolver DNS ricorsivo remoto, nel qual caso si consiglia di allineare il server resolver ricorsivo DNS con l'uscita di rete.</span><span class="sxs-lookup"><span data-stu-id="71023-165">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="71023-166">Velocità di download bassa dalla porta di ingresso di SharePoint</span><span class="sxs-lookup"><span data-stu-id="71023-166">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="71023-167">Questa intuizione verrà visualizzata se il servizio Network Insights rileva che la larghezza di banda tra la posizione specifica di Office e SharePoint Online è inferiore a 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="71023-167">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="71023-168">Questa intuizione è abbreviata come "velocità effettiva" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="71023-168">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="71023-169">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="71023-169">What does this mean?</span></span>

<span data-ttu-id="71023-170">La velocità di download che un utente può ottenere dalle porte frontali di servizio di SharePoint Online e OneDrive for business è misurata in megabyte al secondo (MBps).</span><span class="sxs-lookup"><span data-stu-id="71023-170">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="71023-171">Se questo valore è inferiore a 1 MBps, verrà fornita questa panoramica.</span><span class="sxs-lookup"><span data-stu-id="71023-171">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="71023-172">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="71023-172">What should I do?</span></span>

<span data-ttu-id="71023-173">Per migliorare la velocità di download, potrebbe essere necessario aumentare la larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="71023-173">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="71023-174">In alternativa, è possibile che vi sia una congestione della rete tra i computer degli utenti nell'ubicazione dell'ufficio e la porta di servizio di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="71023-174">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="71023-175">A volte viene chiamato perdita congestizia e limita la velocità di download disponibile per gli utenti anche se è disponibile una larghezza di banda sufficiente.</span><span class="sxs-lookup"><span data-stu-id="71023-175">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="71023-176">Uscita di rete ottimale per gli utenti cinesi</span><span class="sxs-lookup"><span data-stu-id="71023-176">China user optimal network egress</span></span>

<span data-ttu-id="71023-177">Questa intuizione verrà visualizzata se l'organizzazione dispone di utenti in Cina che si connettono al tenant Microsoft 365 in altre posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="71023-177">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="71023-178">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="71023-178">What does this mean?</span></span>

<span data-ttu-id="71023-179">Se l'organizzazione dispone di connettività WAN privata, è consigliabile configurare un circuito WAN di rete dalle posizioni di Office in Cina che dispongono di un'uscita di rete su Internet in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="71023-179">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="71023-180">RAS di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="71023-180">Hong Kong</span></span>
- <span data-ttu-id="71023-181">Giappone</span><span class="sxs-lookup"><span data-stu-id="71023-181">Japan</span></span>
- <span data-ttu-id="71023-182">Taiwan</span><span class="sxs-lookup"><span data-stu-id="71023-182">Taiwan</span></span>
- <span data-ttu-id="71023-183">Corea del Sud</span><span class="sxs-lookup"><span data-stu-id="71023-183">South Korea</span></span>
- <span data-ttu-id="71023-184">Singapore</span><span class="sxs-lookup"><span data-stu-id="71023-184">Singapore</span></span>
- <span data-ttu-id="71023-185">Malaysia</span><span class="sxs-lookup"><span data-stu-id="71023-185">Malaysia</span></span>

<span data-ttu-id="71023-186">L'uscita Internet più lontana dagli utenti rispetto a queste posizioni ridurrà le prestazioni e l'uscita in Cina potrebbe causare problemi di connettività e latenza elevata a causa della congestione transfrontaliera.</span><span class="sxs-lookup"><span data-stu-id="71023-186">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="71023-187">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="71023-187">What should I do?</span></span>

<span data-ttu-id="71023-188">Per ulteriori informazioni su come attenuare i problemi relativi alle prestazioni relativi a questa intuizione, vedere [Office 365 Global tenant Performance Optimization for China Users](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="71023-188">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="71023-189">Connessioni con campionamento di Exchange interessate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="71023-189">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="71023-190">Questa intuizione mostrerà quando 50% o più delle connessioni campionate sono influito.</span><span class="sxs-lookup"><span data-stu-id="71023-190">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="71023-191">L'impatto è definito dalla valutazione di Exchange che si trova al di sotto del 60% per ogni campione.</span><span class="sxs-lookup"><span data-stu-id="71023-191">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="71023-192">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="71023-192">What does this mean?</span></span>

<span data-ttu-id="71023-193">È un'indicazione che la maggior parte degli utenti è probabile che si verifichino problemi di esperienza utente con Outlook che si connette a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="71023-193">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="71023-194">La percentuale di esempi rappresenta probabilmente la percentuale di utenti che mostrano al di sotto di 60 punti.</span><span class="sxs-lookup"><span data-stu-id="71023-194">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="71023-195">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="71023-195">What should I do?</span></span>

<span data-ttu-id="71023-196">Abilitare la visibilità della connettività di rete di Office location se non è stato già fatto.</span><span class="sxs-lookup"><span data-stu-id="71023-196">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="71023-197">Si desidera identificare quali uffici sono interessati da una scarsa connettività di rete che ha un impatto su Exchange e trovare modi per migliorare il perimetro della rete in ognuno dei quali connette gli utenti alla rete di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71023-197">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="71023-198">Connessioni con campionamento di SharePoint influenzate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="71023-198">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="71023-199">Questa intuizione mostrerà quando 50% o più delle connessioni campionate sono influito.</span><span class="sxs-lookup"><span data-stu-id="71023-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="71023-200">L'impatto è definito dalla valutazione di SharePoint al di sotto del 40% per ogni campione.</span><span class="sxs-lookup"><span data-stu-id="71023-200">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="71023-201">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="71023-201">What does this mean?</span></span>

<span data-ttu-id="71023-202">È un'indicazione che la maggior parte degli utenti è probabile che si verifichino problemi di esperienza utente con SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="71023-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="71023-203">La percentuale di esempi rappresenta probabilmente la percentuale di utenti che mostrano al di sotto di 40 punti.</span><span class="sxs-lookup"><span data-stu-id="71023-203">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="71023-204">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="71023-204">What should I do?</span></span>

<span data-ttu-id="71023-205">Abilitare la visibilità della connettività di rete di Office location se non è stato già fatto.</span><span class="sxs-lookup"><span data-stu-id="71023-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="71023-206">Si desidera identificare quali uffici sono interessati da una scarsa connettività di rete che ha un impatto su SharePoint e trovare modi per migliorare il perimetro della rete in ognuno dei quali connette gli utenti alla rete di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71023-206">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="71023-207">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="71023-207">Related topics</span></span>

[<span data-ttu-id="71023-208">Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="71023-208">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="71023-209">Valutazione della rete Microsoft 365 (Preview)</span><span class="sxs-lookup"><span data-stu-id="71023-209">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="71023-210">Strumento di test della connettività di rete Microsoft 365 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="71023-210">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="71023-211">Microsoft 365 servizi di localizzazione della connettività di rete (anteprima)</span><span class="sxs-lookup"><span data-stu-id="71023-211">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
