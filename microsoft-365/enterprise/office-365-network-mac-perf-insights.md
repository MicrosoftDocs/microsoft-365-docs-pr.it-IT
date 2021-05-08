---
title: Microsoft 365 Informazioni dettagliate di rete (anteprima)
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
description: Microsoft 365 Informazioni dettagliate di rete (anteprima)
ms.openlocfilehash: ca665f4e492b071e5a387ffde0efae8336bd96bc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245781"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="31663-103">Microsoft 365 Informazioni dettagliate di rete (anteprima)</span><span class="sxs-lookup"><span data-stu-id="31663-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="31663-104">**Le informazioni dettagliate** di rete sono metriche sulle prestazioni raccolte dal tenant Microsoft 365 e disponibili per la visualizzazione solo da parte degli utenti amministrativi nel tenant.</span><span class="sxs-lookup"><span data-stu-id="31663-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="31663-105">Le informazioni dettagliate vengono visualizzate nell'Microsoft 365 admin center all'indirizzo <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="31663-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="31663-106">Le informazioni dettagliate sono utili per progettare perimetri di rete per le posizioni dell'ufficio.</span><span class="sxs-lookup"><span data-stu-id="31663-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="31663-107">Ogni approfondimento fornisce dettagli in tempo reale sulle caratteristiche delle prestazioni per un problema comune specifico per ogni posizione geografica in cui gli utenti accedono al tenant.</span><span class="sxs-lookup"><span data-stu-id="31663-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="31663-108">Sono disponibili sei informazioni dettagliate sulla rete specifiche che possono essere visualizzate per ogni posizione dell'ufficio:</span><span class="sxs-lookup"><span data-stu-id="31663-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="31663-109">Uscita di rete con backhauled</span><span class="sxs-lookup"><span data-stu-id="31663-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="31663-110">Dispositivo intermedio di rete</span><span class="sxs-lookup"><span data-stu-id="31663-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="31663-111">Prestazioni migliori rilevate per i clienti nelle vicinanze</span><span class="sxs-lookup"><span data-stu-id="31663-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="31663-112">Uso di una porta d'ingresso del Exchange Online non ottimale</span><span class="sxs-lookup"><span data-stu-id="31663-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="31663-113">Uso di una porta d'ingresso del servizio SharePoint online non ottimale</span><span class="sxs-lookup"><span data-stu-id="31663-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="31663-114">Bassa velocità di download da SharePoint porta principale</span><span class="sxs-lookup"><span data-stu-id="31663-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="31663-115">Uscita di rete ottimale per gli utenti in Cina</span><span class="sxs-lookup"><span data-stu-id="31663-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="31663-116">Sono disponibili due informazioni dettagliate sulla rete a livello di tenant che possono essere visualizzate per il tenant.</span><span class="sxs-lookup"><span data-stu-id="31663-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="31663-117">Queste vengono visualizzate anche nelle pagine del punteggio di produttività:</span><span class="sxs-lookup"><span data-stu-id="31663-117">These also appear in the productivity score pages:</span></span>

- [<span data-ttu-id="31663-118">Exchange le connessioni campionate influenzate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="31663-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="31663-119">SharePoint le connessioni campionate influenzate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="31663-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="31663-120">Le informazioni dettagliate sulla rete, i consigli sulle prestazioni e le valutazioni nell'interfaccia di amministrazione di Microsoft 365 sono attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 registrati nel programma di anteprima delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="31663-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="31663-121">Uscita di rete con backhauled</span><span class="sxs-lookup"><span data-stu-id="31663-121">Backhauled network egress</span></span>

<span data-ttu-id="31663-122">Queste informazioni dettagliate verranno visualizzate se il servizio informazioni dettagliate di rete rileva che la distanza tra una determinata posizione utente e l'uscita di rete è maggiore di 800 chilometri, a indicare che il traffico di Microsoft 365 viene riabilitato a un proxy o a un dispositivo perimetrale Internet comune.</span><span class="sxs-lookup"><span data-stu-id="31663-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="31663-123">Questa panoramica è abbreviata come "Egress" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="31663-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31663-124">![Uscita di rete con backhauled](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span><span class="sxs-lookup"><span data-stu-id="31663-124">![Backhauled network egress](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31663-125">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="31663-125">What does this mean?</span></span>

<span data-ttu-id="31663-126">Ciò identifica che la distanza tra la sede dell'ufficio e l'uscita di rete è superiore a 500 miglia (800 chilometri).</span><span class="sxs-lookup"><span data-stu-id="31663-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="31663-127">La posizione dell'ufficio è identificata da una posizione offuscata del computer client e la posizione di uscita dalla rete viene identificata utilizzando l'indirizzo IP inverso per i database delle località.</span><span class="sxs-lookup"><span data-stu-id="31663-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="31663-128">La posizione dell'ufficio potrebbe non essere corretta se Windows è disabilitato nei computer.</span><span class="sxs-lookup"><span data-stu-id="31663-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="31663-129">Il percorso di uscita della rete potrebbe non essere accurato se le informazioni del database degli indirizzi IP inversa non sono accurate.</span><span class="sxs-lookup"><span data-stu-id="31663-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="31663-130">I dettagli per queste informazioni includono la posizione dell'ufficio, la percentuale stimata dell'utente tenant totale nella posizione, la posizione corrente di uscita della rete, la pertinenza della posizione di uscita, la distanza tra la posizione e il punto di uscita corrente, la data in cui la condizione è stata rilevata per la prima volta e la data in cui la condizione è stata risolta.</span><span class="sxs-lookup"><span data-stu-id="31663-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31663-131">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="31663-131">What should I do?</span></span>

<span data-ttu-id="31663-132">Per queste informazioni, è consigliabile l'uscita della rete più vicino alla sede dell'ufficio, in modo che la connettività possa essere instradato in modo ottimale alla rete globale di Microsoft e alla porta d'ingresso del servizio di Microsoft 365 più vicina.</span><span class="sxs-lookup"><span data-stu-id="31663-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="31663-133">La presenza di una stretta uscita di rete per le sedi degli utenti consente inoltre di migliorare le prestazioni in futuro, poiché Microsoft espande i punti di presenza della rete e Microsoft 365 porte anteriori del servizio in futuro.</span><span class="sxs-lookup"><span data-stu-id="31663-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="31663-134">Per ulteriori informazioni su come risolvere questo problema, vedere Egress [connessioni](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) di rete in locale in [Office 365 di connettività di rete](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="31663-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="31663-135">Dispositivo intermedio di rete</span><span class="sxs-lookup"><span data-stu-id="31663-135">Network intermediary device</span></span>

<span data-ttu-id="31663-136">Questa panoramica verrà visualizzata se sono stati rilevati dispositivi tra gli utenti e la rete di Microsoft che potrebbero influire sulla Office 365'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="31663-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="31663-137">È consigliabile ignorarlo per il traffico di Microsoft 365 specifico destinato ai datacenter Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31663-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="31663-138">Questa raccomandazione è descritta in Microsoft 365 [di connettività di rete](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="31663-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span> 

<span data-ttu-id="31663-139">Un'analisi intermedia di rete mostrata è l'interruzione e l'ispezione SSL quando gli endpoint di rete Office 365 critici per Exchange, SharePoint e Teams vengono intercettati e decrittografati dai dispositivi di intermediazione di rete.</span><span class="sxs-lookup"><span data-stu-id="31663-139">One network intermediary insight we show is SSL break and inspection when critical Office 365 network endpoints for Exchange, SharePoint and Teams are intercepted and decrypted by network intermediary devices.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31663-140">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="31663-140">What does this mean?</span></span>

<span data-ttu-id="31663-141">I dispositivi intermedi di rete, ad esempio server proxy, VPN e dispositivi di prevenzione della perdita di dati, possono influire sulle prestazioni e sulla stabilità dei client Microsoft 365 in cui il traffico è intermedio.</span><span class="sxs-lookup"><span data-stu-id="31663-141">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31663-142">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="31663-142">What should I do?</span></span>

<span data-ttu-id="31663-143">Configurare il dispositivo intermedio di rete rilevato per ignorare l'elaborazione Microsoft 365 traffico di rete.</span><span class="sxs-lookup"><span data-stu-id="31663-143">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="31663-144">Prestazioni migliori rilevate per i clienti nelle vicinanze</span><span class="sxs-lookup"><span data-stu-id="31663-144">Better performance detected for customers near you</span></span>

<span data-ttu-id="31663-145">Questa panoramica verrà visualizzata se il servizio informazioni dettagliate di rete rileva che un numero significativo di clienti nell'area della metropolitana ha prestazioni migliori rispetto agli utenti dell'organizzazione in questa sede dell'ufficio.</span><span class="sxs-lookup"><span data-stu-id="31663-145">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="31663-146">Questa panoramica è abbreviata come "Peers" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="31663-146">This insight is abbreviated as "Peers" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31663-147">![Prestazioni di rete relative](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span><span class="sxs-lookup"><span data-stu-id="31663-147">![Relative network performance](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31663-148">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="31663-148">What does this mean?</span></span>

<span data-ttu-id="31663-149">Questa panoramica esamina le prestazioni aggregate dei clienti Microsoft 365 nella stessa città di questa sede.</span><span class="sxs-lookup"><span data-stu-id="31663-149">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="31663-150">Questa panoramica viene visualizzata se la latenza media degli utenti è superiore del 10% alla latenza media dei tenant vicini.</span><span class="sxs-lookup"><span data-stu-id="31663-150">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31663-151">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="31663-151">What should I do?</span></span>

<span data-ttu-id="31663-152">Questa condizione può essere causata da molti motivi, tra cui la latenza nella rete aziendale o nell'ISP, colli di bottiglia o problemi di progettazione dell'architettura.</span><span class="sxs-lookup"><span data-stu-id="31663-152">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="31663-153">Esaminare la latenza tra ogni hop nella route tra la rete dell'ufficio e la porta Microsoft 365 porta principale corrente.</span><span class="sxs-lookup"><span data-stu-id="31663-153">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="31663-154">Per ulteriori informazioni, vedere [Microsoft 365 di connettività di rete](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="31663-154">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="31663-155">Uso di una porta d'ingresso del Exchange Online non ottimale</span><span class="sxs-lookup"><span data-stu-id="31663-155">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="31663-156">Questa panoramica verrà visualizzata se il servizio informazioni dettagliate di rete rileva che gli utenti in una posizione specifica non si connettono a una porta d'ingresso del servizio Exchange Online ottimale.</span><span class="sxs-lookup"><span data-stu-id="31663-156">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="31663-157">Questa panoramica è abbreviata come "Routing" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="31663-157">This insight is abbreviated as "Routing" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31663-158">![Porta anteriore EXO non ottimale](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span><span class="sxs-lookup"><span data-stu-id="31663-158">![Non-optimal EXO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31663-159">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="31663-159">What does this mean?</span></span>

<span data-ttu-id="31663-160">Sono elencate Exchange Online porte anteriori del servizio adatte per l'uso dalla città della sede dell'ufficio con buone prestazioni.</span><span class="sxs-lookup"><span data-stu-id="31663-160">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="31663-161">Se il test corrente mostra l'uso di una porta Exchange Online di servizio non in questo elenco, questa raccomandazione viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="31663-161">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31663-162">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="31663-162">What should I do?</span></span>

<span data-ttu-id="31663-163">L'uso di una porta anteriore del servizio Exchange Online non ottimale potrebbe essere causato da un backhaul di rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita di rete locale e diretta.</span><span class="sxs-lookup"><span data-stu-id="31663-163">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="31663-164">Potrebbe anche essere causato dall'utilizzo di un server Resolver ricorsivo DNS remoto nel qual caso è consigliabile allineare il server Resolver ricorsivo DNS con l'uscita di rete.</span><span class="sxs-lookup"><span data-stu-id="31663-164">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="31663-165">Uso di una porta d'ingresso del servizio SharePoint online non ottimale</span><span class="sxs-lookup"><span data-stu-id="31663-165">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="31663-166">Questa panoramica verrà visualizzata se il servizio informazioni dettagliate di rete rileva che gli utenti in una posizione specifica non si connettono alla porta d'ingresso del servizio online SharePoint più vicina.</span><span class="sxs-lookup"><span data-stu-id="31663-166">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="31663-167">Questa panoramica è abbreviata come "Afd" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="31663-167">This insight is abbreviated as "Afd" in some summary views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31663-168">![Porta anteriore spo non ottimale](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span><span class="sxs-lookup"><span data-stu-id="31663-168">![Non-optimal SPO front door](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31663-169">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="31663-169">What does this mean?</span></span>

<span data-ttu-id="31663-170">Identifi SharePoint porta principale del servizio online a cui si connette il client di test.</span><span class="sxs-lookup"><span data-stu-id="31663-170">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="31663-171">Quindi, per la città della sede si confronta con la porta d'ingresso del servizio SharePoint online prevista per quella città.</span><span class="sxs-lookup"><span data-stu-id="31663-171">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="31663-172">Se non corrisponde, questo consiglio viene fatto.</span><span class="sxs-lookup"><span data-stu-id="31663-172">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31663-173">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="31663-173">What should I do?</span></span>

<span data-ttu-id="31663-174">L'uso di una porta d'ingresso del servizio SharePoint Online non ottimale potrebbe essere causato da un backhaul di rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita di rete locale e diretta.</span><span class="sxs-lookup"><span data-stu-id="31663-174">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="31663-175">Potrebbe anche essere causato dall'utilizzo di un server Resolver ricorsivo DNS remoto nel qual caso è consigliabile allineare il server Resolver ricorsivo DNS con l'uscita di rete.</span><span class="sxs-lookup"><span data-stu-id="31663-175">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="31663-176">Bassa velocità di download da SharePoint porta principale</span><span class="sxs-lookup"><span data-stu-id="31663-176">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="31663-177">Questa panoramica verrà visualizzata se il servizio informazioni dettagliate di rete rileva che la larghezza di banda tra la posizione specifica dell'ufficio e SharePoint Online è inferiore a 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="31663-177">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="31663-178">Questa panoramica è abbreviata come "Velocità effettiva" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="31663-178">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31663-179">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="31663-179">What does this mean?</span></span>

<span data-ttu-id="31663-180">La velocità di download che un utente può ottenere da SharePoint Online e OneDrive for Business front doors del servizio è misurata in megabyte al secondo (MBps).</span><span class="sxs-lookup"><span data-stu-id="31663-180">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="31663-181">Se questo valore è inferiore a 1 MBps, forniamo queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="31663-181">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31663-182">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="31663-182">What should I do?</span></span>

<span data-ttu-id="31663-183">Per migliorare la velocità di download, potrebbe essere necessario aumentare la larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="31663-183">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="31663-184">In alternativa, potrebbe verificarsi una congestione di rete tra i computer degli utenti nella sede dell'ufficio e la porta d'ingresso del SharePoint del servizio online.</span><span class="sxs-lookup"><span data-stu-id="31663-184">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="31663-185">Questa operazione viene talvolta definita perdita congestionata e limita la velocità di download disponibile per gli utenti anche se è disponibile una larghezza di banda sufficiente.</span><span class="sxs-lookup"><span data-stu-id="31663-185">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="31663-186">Uscita di rete ottimale per gli utenti in Cina</span><span class="sxs-lookup"><span data-stu-id="31663-186">China user optimal network egress</span></span>

<span data-ttu-id="31663-187">Questa panoramica verrà visualizzata se l'organizzazione ha utenti in Cina che si connettono al tenant Microsoft 365 in altre posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="31663-187">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="31663-188">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="31663-188">What does this mean?</span></span>

<span data-ttu-id="31663-189">Se l'organizzazione dispone di connettività WAN privata, è consigliabile configurare un circuito WAN di rete dalle posizioni dell'ufficio in Cina con uscita di rete verso Internet in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="31663-189">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="31663-190">Hong Kong</span><span class="sxs-lookup"><span data-stu-id="31663-190">Hong Kong</span></span>
- <span data-ttu-id="31663-191">Giappone</span><span class="sxs-lookup"><span data-stu-id="31663-191">Japan</span></span>
- <span data-ttu-id="31663-192">Taiwan</span><span class="sxs-lookup"><span data-stu-id="31663-192">Taiwan</span></span>
- <span data-ttu-id="31663-193">Corea del Sud</span><span class="sxs-lookup"><span data-stu-id="31663-193">South Korea</span></span>
- <span data-ttu-id="31663-194">Singapore</span><span class="sxs-lookup"><span data-stu-id="31663-194">Singapore</span></span>
- <span data-ttu-id="31663-195">Malaysia</span><span class="sxs-lookup"><span data-stu-id="31663-195">Malaysia</span></span>

<span data-ttu-id="31663-196">L'uscita da Internet più lontano dagli utenti rispetto a queste posizioni ridurrà le prestazioni e l'uscita in Cina potrebbe causare problemi di latenza e connettività elevati a causa della congestione transfrontaliera.</span><span class="sxs-lookup"><span data-stu-id="31663-196">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="31663-197">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="31663-197">What should I do?</span></span>

<span data-ttu-id="31663-198">Per ulteriori informazioni su come ridurre i problemi di prestazioni correlati a queste informazioni, vedere Microsoft 365 ottimizzazione delle prestazioni del tenant globale [per gli utenti della Cina.](microsoft-365-networking-china.md)</span><span class="sxs-lookup"><span data-stu-id="31663-198">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="31663-199">Exchange le connessioni campionate influenzate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="31663-199">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="31663-200">Questa panoramica mostrerà quando il 50% o più delle connessioni campionate sono influenzate.</span><span class="sxs-lookup"><span data-stu-id="31663-200">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="31663-201">L'impatto è definito dalla valutazione Exchange inferiore al 60% per ogni campione.</span><span class="sxs-lookup"><span data-stu-id="31663-201">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31663-202">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="31663-202">What does this mean?</span></span>

<span data-ttu-id="31663-203">Si tratta di un'indicazione del fatto che la maggior parte degli utenti probabilmente riscontra problemi di esperienza utente Outlook connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="31663-203">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="31663-204">La percentuale di campioni rappresenta probabilmente la percentuale di utenti che mostrano meno di 60 punti.</span><span class="sxs-lookup"><span data-stu-id="31663-204">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="31663-205">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="31663-205">What should I do?</span></span>

<span data-ttu-id="31663-206">Abilitare la visibilità della connettività di rete della posizione dell'ufficio, se non è già stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="31663-206">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="31663-207">Si desidera identificare quali uffici sono influenzati da una connettività di rete scarsa che influisce su Exchange e trovare modi per migliorare il perimetro di rete in ognuno di essi che connette gli utenti alla rete di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31663-207">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="31663-208">SharePoint le connessioni campionate influenzate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="31663-208">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="31663-209">Questa panoramica mostrerà quando il 50% o più delle connessioni campionate sono influenzate.</span><span class="sxs-lookup"><span data-stu-id="31663-209">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="31663-210">L'impatto è definito dalla valutazione SharePoint inferiore al 40% per ogni campione.</span><span class="sxs-lookup"><span data-stu-id="31663-210">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="31663-211">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="31663-211">What does this mean?</span></span>

<span data-ttu-id="31663-212">È un'indicazione che la maggior parte degli utenti probabilmente riscontra problemi di esperienza utente con SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="31663-212">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="31663-213">La percentuale di campioni rappresenta probabilmente la percentuale di utenti che mostrano meno di 40 punti.</span><span class="sxs-lookup"><span data-stu-id="31663-213">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="31663-214">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="31663-214">What should I do?</span></span>

<span data-ttu-id="31663-215">Abilitare la visibilità della connettività di rete della posizione dell'ufficio, se non è già stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="31663-215">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="31663-216">Si desidera identificare quali uffici sono influenzati da una connettività di rete scarsa che influisce su SharePoint e trovare modi per migliorare il perimetro di rete in ognuno di essi che connette gli utenti alla rete di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31663-216">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="31663-217">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="31663-217">Related topics</span></span>

[<span data-ttu-id="31663-218">Connettività di rete nell'Microsoft 365 admin center (anteprima)</span><span class="sxs-lookup"><span data-stu-id="31663-218">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="31663-219">Microsoft 365 di rete (anteprima)</span><span class="sxs-lookup"><span data-stu-id="31663-219">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="31663-220">Microsoft 365 di test della connettività di rete (anteprima)</span><span class="sxs-lookup"><span data-stu-id="31663-220">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="31663-221">Microsoft 365 Servizi percorso di connettività di rete (anteprima)</span><span class="sxs-lookup"><span data-stu-id="31663-221">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
