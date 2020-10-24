---
title: Servizi di rete per Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere l'infrastruttura di rete di Contoso e come la società utilizza la tecnologia SD-WAN per garantire prestazioni di rete ottimali a Microsoft 365 per i servizi cloud aziendali.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754015"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="9e506-103">Servizi di rete per Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="9e506-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="9e506-p101">Per adottare un'infrastruttura cloud-inclusive, Contoso ha messo a punto un passaggio fondamentale per la modalità di spostamento del traffico di rete verso i servizi cloud. Invece di un modello hub-and-spoke interno che concentra la connettività di rete e il traffico per il livello successivo della gerarchia di Office, sono state mappate le posizioni degli utenti all'uscita Internet locale e alle connessioni locali al percorso di rete Microsoft 365 più vicino su Internet.</span><span class="sxs-lookup"><span data-stu-id="9e506-p101">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels. Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="9e506-106">Infrastruttura di rete</span><span class="sxs-lookup"><span data-stu-id="9e506-106">Networking infrastructure</span></span>

<span data-ttu-id="9e506-107">Questi sono gli elementi di rete che collegano gli uffici di Contoso in tutto il mondo:</span><span class="sxs-lookup"><span data-stu-id="9e506-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="9e506-108">Rete WAN MPLS (Multiprotocol Label Switching)</span><span class="sxs-lookup"><span data-stu-id="9e506-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="9e506-p102">Una rete WAN MPLS connette la sede di Parigi agli uffici regionali e alle sedi regionali agli uffici satellite in una configurazione a raggio e Hub. La rete consente agli utenti di accedere a server locali che compongono applicazioni line-of-business nella sede di Parigi. Inoltre, consente di instradare qualsiasi traffico Internet generico all'ufficio di Parigi, dove i dispositivi di sicurezza di rete scrub le richieste. All'interno di ogni ufficio, i router offrono traffico a host cablati o a punti di accesso wireless sulle subnet, che utilizzano lo spazio di indirizzi IP privato.</span><span class="sxs-lookup"><span data-stu-id="9e506-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration. The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters. It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="9e506-113">Accesso Internet diretto locale per il traffico Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e506-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="9e506-p103">Ogni ufficio ha un dispositivo WAN (SD-WAN) definito dal software che dispone di uno o più circuiti di rete Internet ISP locali con la propria connettività Internet tramite un server proxy. Questo è in genere implementato come un collegamento WAN a un ISP locale che fornisce anche indirizzi IP pubblici e un server DNS locale.</span><span class="sxs-lookup"><span data-stu-id="9e506-p103">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="9e506-116">Presenza Internet</span><span class="sxs-lookup"><span data-stu-id="9e506-116">Internet presence</span></span>

  <span data-ttu-id="9e506-p104">Contoso possiede il \. nome di dominio pubblico contoso com. Il sito Web pubblico contoso per l'ordinamento dei prodotti è un set di server in un datacenter connesso a Internet nel campus di Parigi. Contoso utilizza l'intervallo di indirizzi IP pubblici a/24 su Internet.</span><span class="sxs-lookup"><span data-stu-id="9e506-p104">Contoso owns the contoso\.com public domain name. The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="9e506-120">Nella figura 1 viene illustrata l'infrastruttura di rete Contoso e le relative connessioni a Internet.</span><span class="sxs-lookup"><span data-stu-id="9e506-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![La rete contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="9e506-122">**Figura 1: la rete contoso**</span><span class="sxs-lookup"><span data-stu-id="9e506-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="9e506-123">Uso di SD-WAN per la connettività di rete ottimale a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e506-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="9e506-124">Contoso ha seguito i [principi della connettività di rete di Microsoft 365](microsoft-365-network-connectivity-principles.md) per:</span><span class="sxs-lookup"><span data-stu-id="9e506-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="9e506-125">Identificare e differenziare il traffico di rete di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e506-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="9e506-126">Uscire dalle connessione di rete a livello locale</span><span class="sxs-lookup"><span data-stu-id="9e506-126">Egress network connections locally</span></span>
- <span data-ttu-id="9e506-127">Evitare fenomeni di "hairpinning" di rete</span><span class="sxs-lookup"><span data-stu-id="9e506-127">Avoid network hairpins</span></span>
- <span data-ttu-id="9e506-128">Bypassare i dispositivi di protezione di rete duplicati</span><span class="sxs-lookup"><span data-stu-id="9e506-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="9e506-129">Esistono tre categorie di traffico di rete per Microsoft 365: *optimize*, *Allow*e *default*.</span><span class="sxs-lookup"><span data-stu-id="9e506-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="9e506-130">Ottimizzare e consentire il traffico è il traffico di rete attendibile crittografato e protetto negli endpoint ed è destinato alla rete Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e506-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="9e506-131">Contoso ha deciso di:</span><span class="sxs-lookup"><span data-stu-id="9e506-131">Contoso decided to:</span></span>

- <span data-ttu-id="9e506-132">Utilizzare l'uscita Internet diretta per ottimizzare e consentire il traffico delle categorie e inoltrare tutto il traffico di categoria predefinito alla connessione Internet centralizzata basata su Parigi.</span><span class="sxs-lookup"><span data-stu-id="9e506-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="9e506-133">Distribuire i dispositivi SD-WAN in ogni ufficio come un modo semplice per seguire questi principi e ottenere prestazioni di rete ottimali per i servizi basati su cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e506-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="9e506-134">I dispositivi SD-WAN sono dotati di una porta LAN per la rete di uffici locale e di più porte WAN.</span><span class="sxs-lookup"><span data-stu-id="9e506-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="9e506-135">Una porta WAN si connette alla rete MPLS.</span><span class="sxs-lookup"><span data-stu-id="9e506-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="9e506-136">Un altro si connette a un circuito ISP locale.</span><span class="sxs-lookup"><span data-stu-id="9e506-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="9e506-137">Il dispositivo SD-WAN instrada il traffico di rete delle categorie Optimize e Allow ai collegamenti ISP.</span><span class="sxs-lookup"><span data-stu-id="9e506-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="9e506-138">L'infrastruttura delle app line-of-business di contoso</span><span class="sxs-lookup"><span data-stu-id="9e506-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="9e506-139">Contoso ha architettato l'infrastruttura Intranet del server e dell'applicazione line-of-business per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e506-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="9e506-140">Gli uffici secondari si avvalgono dei server di memorizzazione nella cache locale per archiviare documenti con accesso frequente e siti Web interni.</span><span class="sxs-lookup"><span data-stu-id="9e506-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="9e506-p107">Gli hub regionali si avvalgono di server applicazioni regionali per gli uffici regionali e quelli secondari. Tali server effettuano la sincronizzazione con i server della sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="9e506-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="9e506-143">I centri dati di Paris Campus contengono server applicazioni centralizzati che servono l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9e506-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="9e506-144">Nella figura 2 viene illustrata la percentuale di capacità del traffico di rete utilizzata per l'accesso ai server nell'Intranet contoso.</span><span class="sxs-lookup"><span data-stu-id="9e506-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![L'infrastruttura di Contoso per applicazioni interne](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="9e506-146">**Figura 2: infrastruttura di Contoso per applicazioni interne**</span><span class="sxs-lookup"><span data-stu-id="9e506-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="9e506-147">Per le sedi degli hub satellite o regionale, il 60% delle risorse necessarie per i dipendenti può essere utilizzato dai server di Office Hub satellite e Regional.</span><span class="sxs-lookup"><span data-stu-id="9e506-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="9e506-148">L'ulteriore 40% delle richieste di risorse deve superare il collegamento WAN al campus di Parigi.</span><span class="sxs-lookup"><span data-stu-id="9e506-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="9e506-149">Analisi di rete e preparazione per Microsoft 365 per Enterprise</span><span class="sxs-lookup"><span data-stu-id="9e506-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="9e506-150">L'adozione corretta di Microsoft 365 per i servizi Enterprise da parte degli utenti di Contoso dipende da una connettività estremamente disponibile e performante a Internet o direttamente ai servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e506-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="9e506-151">Contoso ha eseguito questa procedura per pianificare e implementare la connettività ottimizzata a Microsoft 365 per i servizi cloud aziendali:</span><span class="sxs-lookup"><span data-stu-id="9e506-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="9e506-152">Creare un diagramma della rete WAN aziendale per agevolare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="9e506-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="9e506-153">Per avviare la pianificazione della rete, Contoso ha creato un diagramma che mostra le posizioni di Office, la connettività di rete esistente, i dispositivi perimetrali di rete esistenti e le classi di servizi gestiti sulla rete.</span><span class="sxs-lookup"><span data-stu-id="9e506-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="9e506-154">Questo diagramma è stato utilizzato per ogni passaggio successivo nella pianificazione e nell'implementazione della connettività di rete.</span><span class="sxs-lookup"><span data-stu-id="9e506-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="9e506-155">Creare un piano per Microsoft 365 per la connettività di rete aziendale</span><span class="sxs-lookup"><span data-stu-id="9e506-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="9e506-156">Contoso ha usato i [principi di connettività di rete di microsoft 365](microsoft-365-network-connectivity-principles.md) e le architetture di rete di riferimento di esempio per identificare SD-WAN come topologia preferita per la connettività di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e506-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="9e506-157">Analizzare l'utilizzo della connessione Internet e la larghezza di banda della rete WAN MPLS in ogni ufficio e aumentare la larghezza di banda in base alle esigenze</span><span class="sxs-lookup"><span data-stu-id="9e506-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="9e506-158">Ogni utilizzo corrente di Office è stato analizzato e i circuiti sono stati aumentati in modo che il traffico basato sul cloud previsto per Microsoft 365 funzionerebbe con una media della capacità inutilizzata del 20%.</span><span class="sxs-lookup"><span data-stu-id="9e506-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="9e506-159">Ottimizzare le prestazioni per i servizi di rete Microsoft</span><span class="sxs-lookup"><span data-stu-id="9e506-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="9e506-160">Contoso ha determinato l'insieme degli endpoint di Office 365, Intune e Azure e dei firewall configurati, dei dispositivi di sicurezza e di altri sistemi nel percorso Internet per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="9e506-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="9e506-161">Gli endpoint per il traffico di categoria di Office 365 optimize and allow sono stati configurati nei dispositivi SD-WAN per il routing sul circuito dell'ISP.</span><span class="sxs-lookup"><span data-stu-id="9e506-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="9e506-162">Configurare il DNS interno</span><span class="sxs-lookup"><span data-stu-id="9e506-162">Configure internal DNS</span></span>

   <span data-ttu-id="9e506-163">Il DNS deve essere funzionale e ricercato localmente per il traffico di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e506-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="9e506-164">Convalidare l'endpoint di rete e la connettività delle porte</span><span class="sxs-lookup"><span data-stu-id="9e506-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="9e506-165">Contoso ha eseguito strumenti di test della connettività di rete Microsoft per convalidare la connettività per Microsoft 365 per i servizi cloud aziendali.</span><span class="sxs-lookup"><span data-stu-id="9e506-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="9e506-166">Ottimizzare i computer dei dipendenti per la connettività di rete</span><span class="sxs-lookup"><span data-stu-id="9e506-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="9e506-167">Sono stati controllati singoli computer per garantire che gli aggiornamenti del sistema operativo più recenti siano stati installati e che il monitoraggio della sicurezza di endpoint fosse attivo su tutti i client.</span><span class="sxs-lookup"><span data-stu-id="9e506-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="9e506-168">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="9e506-168">Next step</span></span>

<span data-ttu-id="9e506-169">Informazioni su come Contoso sta facendo [leva sui servizi di dominio Active Directory locali nel cloud](contoso-identity.md) per i dipendenti e l'autenticazione federata per clienti e partner commerciali.</span><span class="sxs-lookup"><span data-stu-id="9e506-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e506-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e506-170">See also</span></span>

[<span data-ttu-id="9e506-171">Roadmap di rete per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9e506-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="9e506-172">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="9e506-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="9e506-173">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="9e506-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
