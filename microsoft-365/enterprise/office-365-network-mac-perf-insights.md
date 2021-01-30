---
title: Microsoft 365 Network Insights (anteprima)
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
description: Microsoft 365 Network Insights (anteprima)
ms.openlocfilehash: d6786ce6cd58ce6f350804fbbacd272b8c077dc0
ms.sourcegitcommit: 1ac884d8470b2f2a58b6f79e324fd91e4d11dceb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055474"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="41e0c-103">Microsoft 365 Network Insights (anteprima)</span><span class="sxs-lookup"><span data-stu-id="41e0c-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="41e0c-104">**Le informazioni dettagliate** di rete sono metriche sulle prestazioni raccolte dal tenant di Microsoft 365 e possono essere visualizzate solo dagli utenti amministrativi nel tenant.</span><span class="sxs-lookup"><span data-stu-id="41e0c-104">**Network insights** are performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="41e0c-105">I dati statistici vengono visualizzati nell'interfaccia di amministrazione di Microsoft 365 all'indirizzo <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="41e0c-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="41e0c-106">Le informazioni dettagliate sono utili per progettare i perimetri di rete per le sedi degli uffici.</span><span class="sxs-lookup"><span data-stu-id="41e0c-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="41e0c-107">Ogni approfondimento fornisce dettagli in tempo reale sulle caratteristiche delle prestazioni per un problema comune specifico per ogni posizione geografica in cui gli utenti accedono al tenant.</span><span class="sxs-lookup"><span data-stu-id="41e0c-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="41e0c-108">Sono disponibili sei informazioni dettagliate di rete specifiche che possono essere visualizzate per ogni posizione dell'ufficio:</span><span class="sxs-lookup"><span data-stu-id="41e0c-108">There are six specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="41e0c-109">Uscita dalla rete con backhauled</span><span class="sxs-lookup"><span data-stu-id="41e0c-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="41e0c-110">Dispositivo intermedio di rete</span><span class="sxs-lookup"><span data-stu-id="41e0c-110">Network intermediary device</span></span>](#network-intermediary-device)
- [<span data-ttu-id="41e0c-111">Prestazioni migliori rilevate per i clienti nelle vicinanze</span><span class="sxs-lookup"><span data-stu-id="41e0c-111">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="41e0c-112">Utilizzo di una porta d'ingresso del servizio Exchange Online non ottimale</span><span class="sxs-lookup"><span data-stu-id="41e0c-112">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="41e0c-113">Utilizzo di una porta d'ingresso del servizio SharePoint Online non ottimale</span><span class="sxs-lookup"><span data-stu-id="41e0c-113">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="41e0c-114">Bassa velocità di download dalla porta principale di SharePoint</span><span class="sxs-lookup"><span data-stu-id="41e0c-114">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)
- [<span data-ttu-id="41e0c-115">Uscita di rete ottimale per gli utenti della Cina</span><span class="sxs-lookup"><span data-stu-id="41e0c-115">China user optimal network egress</span></span>](#china-user-optimal-network-egress)

<span data-ttu-id="41e0c-116">Sono disponibili due informazioni dettagliate sulla rete a livello di tenant che possono essere visualizzate per il tenant.</span><span class="sxs-lookup"><span data-stu-id="41e0c-116">There are two tenant level network insights that may be shown for the tenant.</span></span> <span data-ttu-id="41e0c-117">Queste vengono visualizzate anche nelle pagine dei punteggi di produzione:</span><span class="sxs-lookup"><span data-stu-id="41e0c-117">These also appear in the producvitivy score pages:</span></span>

- [<span data-ttu-id="41e0c-118">Connessioni campionate di Exchange influenzate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="41e0c-118">Exchange sampled connections impacted by connectivity issues</span></span>](#exchange-sampled-connections-impacted-by-connectivity-issues)
- [<span data-ttu-id="41e0c-119">Connessioni campionate di SharePoint influenzate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="41e0c-119">SharePoint sampled connections impacted by connectivity issues</span></span>](#sharepoint-sampled-connections-impacted-by-connectivity-issues)

>[!IMPORTANT]
><span data-ttu-id="41e0c-120">Le informazioni dettagliate sulla rete, i consigli sulle prestazioni e le valutazioni nell'interfaccia di amministrazione di Microsoft 365 sono attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 che sono stati registrati nel programma di anteprima delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="41e0c-120">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="41e0c-121">Uscita dalla rete con backhauled</span><span class="sxs-lookup"><span data-stu-id="41e0c-121">Backhauled network egress</span></span>

<span data-ttu-id="41e0c-122">Queste informazioni dettagliate verranno visualizzate se il servizio informazioni dettagliate di rete rileva che la distanza da una determinata posizione utente all'uscita di rete è maggiore di 800 chilometri, a indicare che il traffico di Microsoft 365 viene backhauled a un proxy o a un dispositivo perimetrale Internet comune.</span><span class="sxs-lookup"><span data-stu-id="41e0c-122">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="41e0c-123">Queste informazioni sono abbreviate come "Uscita" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="41e0c-123">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Uscita dalla rete con backhauled](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="41e0c-125">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="41e0c-125">What does this mean?</span></span>

<span data-ttu-id="41e0c-126">Ciò indica che la distanza tra la sede dell'ufficio e l'uscita di rete è superiore a 800 chilometri.</span><span class="sxs-lookup"><span data-stu-id="41e0c-126">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="41e0c-127">La posizione dell'ufficio è identificata da un percorso del computer client offuscato e il percorso di uscita dalla rete viene identificato utilizzando l'indirizzo IP inverso per i database delle località.</span><span class="sxs-lookup"><span data-stu-id="41e0c-127">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="41e0c-128">La posizione dell'ufficio potrebbe non essere corretta se i servizi di posizione di Windows sono disabilitati nei computer.</span><span class="sxs-lookup"><span data-stu-id="41e0c-128">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="41e0c-129">Il percorso di uscita dalla rete potrebbe non essere accurato se le informazioni del database degli indirizzi IP inversa non sono accurate.</span><span class="sxs-lookup"><span data-stu-id="41e0c-129">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="41e0c-130">I dettagli di queste informazioni includono la posizione dell'ufficio, la percentuale stimata dell'utente tenant totale nella posizione, la posizione di uscita della rete corrente, la pertinenza della posizione di uscita, la distanza tra la posizione e il punto di uscita corrente, la data in cui la condizione è stata rilevata per la prima volta e la data in cui la condizione è stata risolta.</span><span class="sxs-lookup"><span data-stu-id="41e0c-130">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="41e0c-131">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="41e0c-131">What should I do?</span></span>

<span data-ttu-id="41e0c-132">Per queste informazioni, è consigliabile l'uscita di rete più vicina alla sede dell'ufficio, in modo che la connettività possa instradare in modo ottimale alla rete globale di Microsoft e al front door del servizio Microsoft 365 più vicino.</span><span class="sxs-lookup"><span data-stu-id="41e0c-132">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="41e0c-133">Una stretta uscita di rete nelle sedi degli utenti consente anche di migliorare le prestazioni in futuro, in quanto Microsoft espande i punti di presenza di rete e le porte anteriori dei servizi di Microsoft 365 in futuro.</span><span class="sxs-lookup"><span data-stu-id="41e0c-133">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="41e0c-134">Per ulteriori informazioni su come risolvere questo problema, vedere [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="41e0c-134">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="network-intermediary-device"></a><span data-ttu-id="41e0c-135">Dispositivo intermedio di rete</span><span class="sxs-lookup"><span data-stu-id="41e0c-135">Network intermediary device</span></span>

<span data-ttu-id="41e0c-136">Queste informazioni verranno visualizzate se sono stati rilevati dispositivi tra gli utenti e la rete di Microsoft che potrebbero influire sull'esperienza utente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="41e0c-136">This insight will be displayed if we detected devices between your users and Microsoft's network which may impact the Office 365 user experience.</span></span> <span data-ttu-id="41e0c-137">È consigliabile ignorarlo per il traffico di rete specifico di Microsoft 365 destinato ai datacenter Microsoft.</span><span class="sxs-lookup"><span data-stu-id="41e0c-137">It is recommended that these be bypassed for specific Microsoft 365 network traffic that is destined for Microsoft datacenters.</span></span> <span data-ttu-id="41e0c-138">Questa raccomandazione è descritta anche in Principi di connettività [di rete di Microsoft 365](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="41e0c-138">This recommendation is additionally described in [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="41e0c-139">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="41e0c-139">What does this mean?</span></span>

<span data-ttu-id="41e0c-140">I dispositivi intermedi di rete come server proxy, VPN e dispositivi di prevenzione della perdita dei dati possono influire sulle prestazioni e sulla stabilità dei client Microsoft 365 in cui il traffico è intermedio.</span><span class="sxs-lookup"><span data-stu-id="41e0c-140">Network intermediary devices such as proxy servers, VPNs, and data loss prevention devices can affect performance and stability of Microsoft 365 clients where traffic is intermediated.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="41e0c-141">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="41e0c-141">What should I do?</span></span>

<span data-ttu-id="41e0c-142">Configurare il dispositivo intermedio di rete rilevato per ignorare l'elaborazione del traffico di rete di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41e0c-142">Configure the network intermediary device that was detected to bypass processing for Microsoft 365 network traffic.</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="41e0c-143">Prestazioni migliori rilevate per i clienti nelle vicinanze</span><span class="sxs-lookup"><span data-stu-id="41e0c-143">Better performance detected for customers near you</span></span>

<span data-ttu-id="41e0c-144">Queste informazioni verranno visualizzate se il servizio Informazioni dettagliate di rete rileva che un numero significativo di clienti nell'area della metropolitana ha prestazioni migliori rispetto agli utenti dell'organizzazione in questa sede dell'ufficio.</span><span class="sxs-lookup"><span data-stu-id="41e0c-144">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="41e0c-145">Queste informazioni sono abbreviate come "Peer" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="41e0c-145">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Prestazioni di rete relative](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="41e0c-147">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="41e0c-147">What does this mean?</span></span>

<span data-ttu-id="41e0c-148">Queste informazioni esaminano le prestazioni aggregate dei clienti di Microsoft 365 nella stessa città di questa sede.</span><span class="sxs-lookup"><span data-stu-id="41e0c-148">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="41e0c-149">Queste informazioni vengono visualizzate se la latenza media degli utenti è superiore del 10% alla latenza media dei tenant adiacenti.</span><span class="sxs-lookup"><span data-stu-id="41e0c-149">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="41e0c-150">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="41e0c-150">What should I do?</span></span>

<span data-ttu-id="41e0c-151">Questa condizione può essere causata da diversi motivi, tra cui la latenza nella rete aziendale o nell'ISP, colli di bottiglia o problemi di progettazione dell'architettura.</span><span class="sxs-lookup"><span data-stu-id="41e0c-151">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="41e0c-152">Esaminare la latenza tra ogni hop nella route tra la rete dell'ufficio e l'attuale porta d'ingresso di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41e0c-152">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="41e0c-153">Per ulteriori informazioni, vedere Principi di connettività di [rete di Microsoft 365.](microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="41e0c-153">For more information, see [Microsoft 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="41e0c-154">Utilizzo di una porta d'ingresso del servizio Exchange Online non ottimale</span><span class="sxs-lookup"><span data-stu-id="41e0c-154">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="41e0c-155">Queste informazioni verranno visualizzate se il servizio Informazioni dettagliate di rete rileva che gli utenti in una posizione specifica non si connettono a un front door ottimale del servizio Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="41e0c-155">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="41e0c-156">Queste informazioni sono abbreviate come "Routing" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="41e0c-156">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Porta anteriore EXO non ottimale](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="41e0c-158">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="41e0c-158">What does this mean?</span></span>

<span data-ttu-id="41e0c-159">Sono elencate le porte anteriori del servizio Exchange Online adatte per l'uso dalla città di sede dell'ufficio con buone prestazioni.</span><span class="sxs-lookup"><span data-stu-id="41e0c-159">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="41e0c-160">Se il test corrente mostra l'uso di un front door del servizio Exchange Online non in questo elenco, viene chiamato questo consiglio.</span><span class="sxs-lookup"><span data-stu-id="41e0c-160">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="41e0c-161">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="41e0c-161">What should I do?</span></span>

<span data-ttu-id="41e0c-162">L'uso di una porta anteriore del servizio Exchange Online non ottimale potrebbe essere causato dal backhaul di rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita dalla rete locale e diretta.</span><span class="sxs-lookup"><span data-stu-id="41e0c-162">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="41e0c-163">Potrebbe anche essere causato dall'uso di un server resolver DNS ricorsivo remoto, nel qual caso è consigliabile allineare il server resolver ricorsivo DNS all'uscita di rete.</span><span class="sxs-lookup"><span data-stu-id="41e0c-163">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="41e0c-164">Uso di un front door del servizio SharePoint Online non ottimale</span><span class="sxs-lookup"><span data-stu-id="41e0c-164">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="41e0c-165">Queste informazioni dettagliate verranno visualizzate se il servizio Informazioni dettagliate di rete rileva che gli utenti in una posizione specifica non si connettono al front door del servizio SharePoint Online più vicino.</span><span class="sxs-lookup"><span data-stu-id="41e0c-165">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="41e0c-166">Queste informazioni sono abbreviate come "Afd" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="41e0c-166">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Porta anteriore di Spo non ottimale](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="41e0c-168">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="41e0c-168">What does this mean?</span></span>

<span data-ttu-id="41e0c-169">Viene identificata la porta d'ingresso del servizio SharePoint Online a cui si connette il client di test.</span><span class="sxs-lookup"><span data-stu-id="41e0c-169">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="41e0c-170">Quindi, per la città dell'ubicazione dell'ufficio viene confrontato con l'ingresso del servizio SharePoint Online previsto per quella città.</span><span class="sxs-lookup"><span data-stu-id="41e0c-170">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="41e0c-171">Se non corrisponde, è consigliabile farlo.</span><span class="sxs-lookup"><span data-stu-id="41e0c-171">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="41e0c-172">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="41e0c-172">What should I do?</span></span>

<span data-ttu-id="41e0c-173">L'uso di una porta anteriore del servizio SharePoint Online non ottimale potrebbe essere causato dal backhaul di rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita dalla rete locale e diretta.</span><span class="sxs-lookup"><span data-stu-id="41e0c-173">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="41e0c-174">Potrebbe anche essere causato dall'uso di un server resolver DNS ricorsivo remoto, nel qual caso è consigliabile allineare il server resolver ricorsivo DNS all'uscita di rete.</span><span class="sxs-lookup"><span data-stu-id="41e0c-174">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="41e0c-175">Bassa velocità di download dalla porta d'ingresso di SharePoint</span><span class="sxs-lookup"><span data-stu-id="41e0c-175">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="41e0c-176">Queste informazioni dettagliate verranno visualizzate se il servizio Informazioni dettagliate di rete rileva che la larghezza di banda tra la posizione specifica dell'ufficio e SharePoint Online è inferiore a 1 MBps.</span><span class="sxs-lookup"><span data-stu-id="41e0c-176">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="41e0c-177">Queste informazioni sono abbreviate come "Velocità effettiva" in alcune visualizzazioni di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="41e0c-177">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="41e0c-178">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="41e0c-178">What does this mean?</span></span>

<span data-ttu-id="41e0c-179">La velocità di download che un utente può ottenere dalle porte anteriori del servizio SharePoint Online e OneDrive for Business è misurata in megabyte al secondo (MBps).</span><span class="sxs-lookup"><span data-stu-id="41e0c-179">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="41e0c-180">Se questo valore è inferiore a 1 MBps, queste informazioni vengono fornite.</span><span class="sxs-lookup"><span data-stu-id="41e0c-180">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="41e0c-181">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="41e0c-181">What should I do?</span></span>

<span data-ttu-id="41e0c-182">Per migliorare la velocità di download, potrebbe essere necessario aumentare la larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="41e0c-182">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="41e0c-183">In alternativa, potrebbe verificarsi una congestione della rete tra i computer degli utenti nella sede dell'ufficio e la porta d'ingresso del servizio SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="41e0c-183">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="41e0c-184">A volte si tratta di una perdita congestionata che limita la velocità di download disponibile per gli utenti anche se è disponibile una larghezza di banda sufficiente.</span><span class="sxs-lookup"><span data-stu-id="41e0c-184">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="41e0c-185">Uscita ottimale della rete dell'utente in Cina</span><span class="sxs-lookup"><span data-stu-id="41e0c-185">China user optimal network egress</span></span>

<span data-ttu-id="41e0c-186">Queste informazioni verranno visualizzate se l'organizzazione ha utenti in Cina che si connettono al tenant di Microsoft 365 in altre posizioni geografiche.</span><span class="sxs-lookup"><span data-stu-id="41e0c-186">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="41e0c-187">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="41e0c-187">What does this mean?</span></span>

<span data-ttu-id="41e0c-188">Se l'organizzazione dispone di connettività WAN privata, è consigliabile configurare un circuito WAN di rete dalle sedi degli uffici in Cina con uscita di rete verso Internet in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41e0c-188">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="41e0c-189">Hong Kong</span><span class="sxs-lookup"><span data-stu-id="41e0c-189">Hong Kong</span></span>
- <span data-ttu-id="41e0c-190">Giappone</span><span class="sxs-lookup"><span data-stu-id="41e0c-190">Japan</span></span>
- <span data-ttu-id="41e0c-191">Taiwan</span><span class="sxs-lookup"><span data-stu-id="41e0c-191">Taiwan</span></span>
- <span data-ttu-id="41e0c-192">Corea del Sud</span><span class="sxs-lookup"><span data-stu-id="41e0c-192">South Korea</span></span>
- <span data-ttu-id="41e0c-193">Singapore</span><span class="sxs-lookup"><span data-stu-id="41e0c-193">Singapore</span></span>
- <span data-ttu-id="41e0c-194">Malaysia</span><span class="sxs-lookup"><span data-stu-id="41e0c-194">Malaysia</span></span>

<span data-ttu-id="41e0c-195">L'uscita di Internet più lontano dagli utenti rispetto a queste posizioni ridurrà le prestazioni e l'uscita in Cina potrebbe causare problemi di latenza e connettività elevati a causa della congestione oltre i confini.</span><span class="sxs-lookup"><span data-stu-id="41e0c-195">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="41e0c-196">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="41e0c-196">What should I do?</span></span>

<span data-ttu-id="41e0c-197">Per ulteriori informazioni su come ridurre i problemi di prestazioni correlati a queste informazioni, vedere Ottimizzazione delle prestazioni del tenant globale di [Microsoft 365 per gli utenti della Cina.](microsoft-365-networking-china.md)</span><span class="sxs-lookup"><span data-stu-id="41e0c-197">For more information about how to mitigate performance issues related to this insight, see [Microsoft 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="exchange-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="41e0c-198">Connessioni campionate di Exchange influenzate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="41e0c-198">Exchange sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="41e0c-199">Queste informazioni mostrano quando il 50% o più delle connessioni campionate sono influenzate.</span><span class="sxs-lookup"><span data-stu-id="41e0c-199">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="41e0c-200">L'impatto è definito dalla valutazione di Exchange inferiore al 60% per ogni campione.</span><span class="sxs-lookup"><span data-stu-id="41e0c-200">The impact is defined by the Exchange assessment being below 60% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="41e0c-201">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="41e0c-201">What does this mean?</span></span>

<span data-ttu-id="41e0c-202">Si tratta di un'indicazione del fatto che è probabile che la maggior parte degli utenti stia riscontrando problemi di esperienza utente con Outlook che si connette a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="41e0c-202">It is an indication that the majority of your users are likely to be experiencing user experience issues with Outlook connecting to Exchange Online.</span></span> <span data-ttu-id="41e0c-203">La percentuale di campioni rappresenta probabilmente la percentuale di utenti che mostrano meno di 60 punti.</span><span class="sxs-lookup"><span data-stu-id="41e0c-203">The percentage of samples likely represents the percentage of users who show below 60 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="41e0c-204">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="41e0c-204">What should I do?</span></span>

<span data-ttu-id="41e0c-205">Abilitare la visibilità della connettività di rete della posizione dell'ufficio, se non è già stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="41e0c-205">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="41e0c-206">Si desidera identificare gli uffici che sono influenzati da una connettività di rete scadente che influisce su Exchange e trovare modi per migliorare il perimetro di rete in ognuno di essi che connette gli utenti alla rete di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="41e0c-206">You want to identify which offices are impacted by poor network connectivity that is impacting Exchange and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="sharepoint-sampled-connections-impacted-by-connectivity-issues"></a><span data-ttu-id="41e0c-207">Connessioni campionate di SharePoint influenzate da problemi di connettività</span><span class="sxs-lookup"><span data-stu-id="41e0c-207">SharePoint sampled connections impacted by connectivity issues</span></span>

<span data-ttu-id="41e0c-208">Queste informazioni mostrano quando il 50% o più delle connessioni campionate sono influenzate.</span><span class="sxs-lookup"><span data-stu-id="41e0c-208">This insight will show when 50% or more of the sampled connections are impacted.</span></span> <span data-ttu-id="41e0c-209">L'impatto è definito dalla valutazione di SharePoint inferiore al 40% per ogni campione.</span><span class="sxs-lookup"><span data-stu-id="41e0c-209">The impact is defined by the SharePoint assessment being below 40% for each sample.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="41e0c-210">Cosa significa questo messaggio?</span><span class="sxs-lookup"><span data-stu-id="41e0c-210">What does this mean?</span></span>

<span data-ttu-id="41e0c-211">Si tratta di un'indicazione del fatto che è probabile che la maggior parte degli utenti stia riscontrando problemi di esperienza utente con SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="41e0c-211">It is an indication that the majority of your users are likely to be experiencing user experience issues with SharePoint and OneDrive.</span></span> <span data-ttu-id="41e0c-212">La percentuale di campioni rappresenta probabilmente la percentuale di utenti che mostrano meno di 40 punti.</span><span class="sxs-lookup"><span data-stu-id="41e0c-212">The percentage of samples likely represents the percentage of users who show below 40 points.</span></span>  

### <a name="what-should-i-do"></a><span data-ttu-id="41e0c-213">Cosa si può fare?</span><span class="sxs-lookup"><span data-stu-id="41e0c-213">What should I do?</span></span>

<span data-ttu-id="41e0c-214">Abilitare la visibilità della connettività di rete della posizione dell'ufficio, se non è già stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="41e0c-214">Enable office location network connectivity visibility if you have not already done so.</span></span> <span data-ttu-id="41e0c-215">Si desidera identificare gli uffici che sono influenzati da una connettività di rete scadente che influisce su SharePoint e trovare modi per migliorare il perimetro di rete in ognuno di essi che connette gli utenti alla rete di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="41e0c-215">You want to identify which offices are impacted by poor network connectivity that is impacting SharePoint and find ways to improve the network perimeter at each that connects the users to Microsoft's network.</span></span>

## <a name="related-topics"></a><span data-ttu-id="41e0c-216">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="41e0c-216">Related topics</span></span>

[<span data-ttu-id="41e0c-217">Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="41e0c-217">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="41e0c-218">Valutazione della rete di Microsoft 365 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="41e0c-218">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="41e0c-219">Strumento di test della connettività di rete di Microsoft 365 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="41e0c-219">Microsoft 365 network connectivity test tool (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="41e0c-220">Servizi percorso di connettività di rete di Microsoft 365 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="41e0c-220">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
