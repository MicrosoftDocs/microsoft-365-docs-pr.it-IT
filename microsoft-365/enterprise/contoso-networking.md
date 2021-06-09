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
description: Comprendere l'infrastruttura di rete di Contoso e come l'azienda utilizza la tecnologia SD-WAN per ottenere prestazioni di rete ottimali per Microsoft 365 servizi cloud aziendali.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754015"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="2802c-103">Servizi di rete per Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="2802c-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="2802c-104">Per adottare un'infrastruttura inclusiva del cloud, Contoso ha ideato un cambiamento fondamentale nel modo in cui viaggia il traffico di rete verso i servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="2802c-104">To adopt a cloud-inclusive infrastructure, Contoso devised a fundamental shift in how network traffic to cloud services travels.</span></span> <span data-ttu-id="2802c-105">Invece di un modello hub e spoke interno che concentra la connettività di rete e il traffico per il livello successivo della gerarchia degli uffici, ha mappato le posizioni degli utenti all'uscita internet locale e le connessioni locali al percorso di rete Microsoft 365 più vicino su Internet.</span><span class="sxs-lookup"><span data-stu-id="2802c-105">Instead of an internal hub-and-spoke model that focuses network connectivity and traffic for the next level of the office hierarchy, they mapped user locations to local internet egress and local connections to the closest Microsoft 365 network location on the internet.</span></span>

## <a name="networking-infrastructure"></a><span data-ttu-id="2802c-106">Infrastruttura di rete</span><span class="sxs-lookup"><span data-stu-id="2802c-106">Networking infrastructure</span></span>

<span data-ttu-id="2802c-107">Questi sono gli elementi di rete che collegano gli uffici di Contoso in tutto il mondo:</span><span class="sxs-lookup"><span data-stu-id="2802c-107">These are the network elements that link Contoso offices across the globe:</span></span>

- <span data-ttu-id="2802c-108">Rete WAN MPLS (Multiprotocol Label Switching)</span><span class="sxs-lookup"><span data-stu-id="2802c-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="2802c-109">Una rete WAN MPLS connette la sede centrale di Parigi agli uffici regionali e agli uffici regionali agli uffici satellite in una configurazione spoke e hub.</span><span class="sxs-lookup"><span data-stu-id="2802c-109">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke-and-hub configuration.</span></span> <span data-ttu-id="2802c-110">La rete consente agli utenti di accedere ai server locali che costituiscono applicazioni line-of-business nella sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="2802c-110">The network enables users to access on-premises servers that make up line-of-business applications in the Paris headquarters.</span></span> <span data-ttu-id="2802c-111">Inoltre, instrada qualsiasi traffico Internet generico all'ufficio di Parigi, dove i dispositivi di sicurezza di rete pulire le richieste.</span><span class="sxs-lookup"><span data-stu-id="2802c-111">It also routes any generic internet traffic to the Paris office, where network security devices scrub the requests.</span></span> <span data-ttu-id="2802c-112">All'interno di ogni ufficio, i router recapitano il traffico agli host cablati o ai punti di accesso wireless nelle subnet, che utilizzano lo spazio di indirizzi IP privato.</span><span class="sxs-lookup"><span data-stu-id="2802c-112">Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="2802c-113">Accesso a Internet diretto locale per Microsoft 365 traffico</span><span class="sxs-lookup"><span data-stu-id="2802c-113">Local direct internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="2802c-114">Ogni ufficio dispone di un dispositivo WAN (SD-WAN) software-defined che dispone di uno o più circuiti di rete ISP Internet locali con la propria connettività Internet tramite un server proxy.</span><span class="sxs-lookup"><span data-stu-id="2802c-114">Each office has a software-defined WAN (SD-WAN) device that has one or more local internet ISP network circuits with its own internet connectivity through a proxy server.</span></span> <span data-ttu-id="2802c-115">Questa funzionalità viene in genere implementata come collegamento WAN a un ISP locale che fornisce anche indirizzi IP pubblici e un server DNS locale.</span><span class="sxs-lookup"><span data-stu-id="2802c-115">This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="2802c-116">Presenza Internet</span><span class="sxs-lookup"><span data-stu-id="2802c-116">Internet presence</span></span>

  <span data-ttu-id="2802c-117">Contoso è proprietario del nome di dominio pubblico contoso \. com.</span><span class="sxs-lookup"><span data-stu-id="2802c-117">Contoso owns the contoso\.com public domain name.</span></span> <span data-ttu-id="2802c-118">Il sito Web pubblico contoso per l'ordinamento dei prodotti è un set di server in un datacenter connesso a Internet nel campus di Parigi.</span><span class="sxs-lookup"><span data-stu-id="2802c-118">The Contoso public web site for ordering products is a set of servers in an internet-connected datacenter in the Paris campus.</span></span> <span data-ttu-id="2802c-119">Contoso usa un intervallo di indirizzi IP pubblici /24 su Internet.</span><span class="sxs-lookup"><span data-stu-id="2802c-119">Contoso uses a /24 public IP address range on the internet.</span></span>

<span data-ttu-id="2802c-120">La figura 1 mostra l'infrastruttura di rete contoso e le relative connessioni a Internet.</span><span class="sxs-lookup"><span data-stu-id="2802c-120">Figure 1 shows the Contoso networking infrastructure and its connections to the internet.</span></span>

![Rete Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="2802c-122">**Figura 1: Rete Contoso**</span><span class="sxs-lookup"><span data-stu-id="2802c-122">**Figure 1: The Contoso network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="2802c-123">Uso di SD-WAN per la connettività di rete ottimale a Microsoft</span><span class="sxs-lookup"><span data-stu-id="2802c-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="2802c-124">Contoso ha seguito i [principi della connettività di rete di Microsoft 365](microsoft-365-network-connectivity-principles.md) per:</span><span class="sxs-lookup"><span data-stu-id="2802c-124">Contoso followed [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) to:</span></span>

- <span data-ttu-id="2802c-125">Identificare e differenziare il traffico di rete di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2802c-125">Identify and differentiate Microsoft 365 network traffic</span></span>
- <span data-ttu-id="2802c-126">Uscire dalle connessione di rete a livello locale</span><span class="sxs-lookup"><span data-stu-id="2802c-126">Egress network connections locally</span></span>
- <span data-ttu-id="2802c-127">Evitare fenomeni di "hairpinning" di rete</span><span class="sxs-lookup"><span data-stu-id="2802c-127">Avoid network hairpins</span></span>
- <span data-ttu-id="2802c-128">Bypassare i dispositivi di protezione di rete duplicati</span><span class="sxs-lookup"><span data-stu-id="2802c-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="2802c-129">Esistono tre categorie di traffico di rete per Microsoft 365: *Optimize,* *Allow* e *Default.*</span><span class="sxs-lookup"><span data-stu-id="2802c-129">There are three categories of network traffic for Microsoft 365: *Optimize*, *Allow*, and *Default*.</span></span> <span data-ttu-id="2802c-130">Ottimizzare e consentire il traffico è un traffico di rete attendibile crittografato e protetto agli endpoint e destinato alla Microsoft 365 rete.</span><span class="sxs-lookup"><span data-stu-id="2802c-130">Optimize and Allow traffic is trusted network traffic that's encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="2802c-131">Contoso ha deciso di:</span><span class="sxs-lookup"><span data-stu-id="2802c-131">Contoso decided to:</span></span>

- <span data-ttu-id="2802c-132">Usa l'uscita internet diretta per Ottimizzare e consentire il traffico di categoria e inoltrare tutto il traffico di categoria predefinito alla connessione Internet centrale con sede a Parigi.</span><span class="sxs-lookup"><span data-stu-id="2802c-132">Use direct internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central internet connection.</span></span>

- <span data-ttu-id="2802c-133">Distribuire dispositivi SD-WAN in ogni ufficio come un modo semplice per seguire questi principi e ottenere prestazioni di rete ottimali per Microsoft 365 servizi basati su cloud.</span><span class="sxs-lookup"><span data-stu-id="2802c-133">Deploy SD-WAN devices at each office as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="2802c-134">I dispositivi SD-WAN sono dotati di una porta LAN per la rete di uffici locale e di più porte WAN.</span><span class="sxs-lookup"><span data-stu-id="2802c-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="2802c-135">Una porta WAN si connette alla rete MPLS.</span><span class="sxs-lookup"><span data-stu-id="2802c-135">One WAN port connects to their MPLS network.</span></span> <span data-ttu-id="2802c-136">Un altro si connette a un circuito ISP locale.</span><span class="sxs-lookup"><span data-stu-id="2802c-136">Another connects to a local ISP circuit.</span></span> <span data-ttu-id="2802c-137">Il dispositivo SD-WAN instrada il traffico di rete delle categorie Optimize e Allow ai collegamenti ISP.</span><span class="sxs-lookup"><span data-stu-id="2802c-137">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="the-contoso-line-of-business-app-infrastructure"></a><span data-ttu-id="2802c-138">Infrastruttura delle app line-of-business contoso</span><span class="sxs-lookup"><span data-stu-id="2802c-138">The Contoso line-of-business app infrastructure</span></span>

<span data-ttu-id="2802c-139">Contoso ha architettato l'infrastruttura Intranet per applicazioni line-of-business e server per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2802c-139">Contoso architected its line-of-business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="2802c-140">Gli uffici secondari si avvalgono dei server di memorizzazione nella cache locale per archiviare documenti con accesso frequente e siti Web interni.</span><span class="sxs-lookup"><span data-stu-id="2802c-140">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="2802c-p107">Gli hub regionali si avvalgono di server applicazioni regionali per gli uffici regionali e quelli secondari. Tali server effettuano la sincronizzazione con i server della sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="2802c-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="2802c-143">I datacenter del campus di Parigi contengono server applicazioni centralizzati che servono l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2802c-143">The Paris campus datacenters contain centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="2802c-144">Nella figura 2 viene mostrata la percentuale di capacità del traffico di rete utilizzata per l'accesso ai server nella rete Intranet di Contoso.</span><span class="sxs-lookup"><span data-stu-id="2802c-144">Figure 2 shows the percentage of network traffic capacity used when accessing servers across the Contoso intranet.</span></span>

![Infrastruttura Contoso per le applicazioni interne](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="2802c-146">**Figura 2: Infrastruttura contoso per le applicazioni interne**</span><span class="sxs-lookup"><span data-stu-id="2802c-146">**Figure 2: The Contoso infrastructure for internal applications**</span></span>

<span data-ttu-id="2802c-147">Per gli uffici hub satellite o regionali, il 60% delle risorse necessarie ai dipendenti può essere servito da server di uffici hub satellite e regionali.</span><span class="sxs-lookup"><span data-stu-id="2802c-147">For the satellite or regional hub offices, 60 percent of the resources needed by employees can be served by satellite and regional hub office servers.</span></span> <span data-ttu-id="2802c-148">Il 40% aggiuntivo delle richieste di risorse deve passare attraverso il collegamento WAN al campus di Parigi.</span><span class="sxs-lookup"><span data-stu-id="2802c-148">The additional 40 percent of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a><span data-ttu-id="2802c-149">Analisi e preparazione della rete per Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="2802c-149">Network analysis and preparation for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="2802c-150">L'adozione corretta Microsoft 365 per i servizi aziendali da parte degli utenti di Contoso dipende dalla connettività a Internet a disponibilità elevata ed efficace o direttamente ai servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2802c-150">Successful adoption of Microsoft 365 for enterprise services by Contoso users depends on highly available and performant connectivity to the internet or directly to Microsoft cloud services.</span></span> <span data-ttu-id="2802c-151">Contoso ha seguito questi passaggi per pianificare e implementare una connettività ottimizzata Microsoft 365 per i servizi cloud aziendali:</span><span class="sxs-lookup"><span data-stu-id="2802c-151">Contoso took these steps to plan and implement optimized connectivity to Microsoft 365 for enterprise cloud services:</span></span>

1. <span data-ttu-id="2802c-152">Creare un diagramma di rete WAN aziendale per facilitare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="2802c-152">Create a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="2802c-153">Per avviare la pianificazione della rete, Contoso ha creato un diagramma che mostra le posizioni dell'ufficio, la connettività di rete esistente, i dispositivi perimetrali di rete esistenti e le classi di servizio gestite nella rete.</span><span class="sxs-lookup"><span data-stu-id="2802c-153">To start their network planning, Contoso created a diagram showing their office locations, existing network connectivity, existing network perimeter devices, and classes of service that are managed on the network.</span></span> <span data-ttu-id="2802c-154">Hanno usato questo diagramma per ogni passaggio successivo della pianificazione e dell'implementazione della connettività di rete.</span><span class="sxs-lookup"><span data-stu-id="2802c-154">They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="2802c-155">Creare un piano per la Microsoft 365 di rete aziendale</span><span class="sxs-lookup"><span data-stu-id="2802c-155">Create a plan for Microsoft 365 for enterprise network connectivity</span></span>

   <span data-ttu-id="2802c-156">Contoso ha utilizzato i [principi Microsoft 365](microsoft-365-network-connectivity-principles.md) di connettività di rete e le architetture di rete di riferimento di esempio per identificare SD-WAN come topologia preferita per Microsoft 365 connettività.</span><span class="sxs-lookup"><span data-stu-id="2802c-156">Contoso used the [Microsoft 365 network connectivity principles](microsoft-365-network-connectivity-principles.md) and sample reference network architectures to identify SD-WAN as their preferred topology for Microsoft 365 connectivity.</span></span>

3. <span data-ttu-id="2802c-157">Analizzare l'utilizzo della connessione Internet e la larghezza di banda MPLS-WAN in ogni ufficio e aumentare la larghezza di banda in base alle esigenze</span><span class="sxs-lookup"><span data-stu-id="2802c-157">Analyze internet-connection utilization and MPLS-WAN bandwidth at each office, and increase bandwidth as needed</span></span>

   <span data-ttu-id="2802c-158">L'utilizzo corrente di ogni ufficio è stato analizzato e i circuiti sono stati aumentati Microsoft 365 modo che il traffico basato su cloud previsto funzionasse con una capacità inutilizzata media del 20%.</span><span class="sxs-lookup"><span data-stu-id="2802c-158">Each office's current usage was analyzed, and circuits were increased so that predicted Microsoft 365 cloud-based traffic would operate with an average of 20-percent unused capacity.</span></span>

4. <span data-ttu-id="2802c-159">Ottimizzare le prestazioni per i servizi di rete Microsoft</span><span class="sxs-lookup"><span data-stu-id="2802c-159">Optimize performance to Microsoft network services</span></span>

   <span data-ttu-id="2802c-160">Contoso ha determinato il set di endpoint Office 365, Intune e Azure e firewall configurati, dispositivi di sicurezza e altri sistemi nel percorso Internet per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="2802c-160">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the internet path for optimal performance.</span></span> <span data-ttu-id="2802c-161">Gli endpoint per Office 365 il traffico di categoria Optimize e Allow sono stati configurati nei dispositivi SD-WAN per il routing sul circuito ISP.</span><span class="sxs-lookup"><span data-stu-id="2802c-161">Endpoints for Office 365 Optimize and Allow category traffic were configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="2802c-162">Configurare DNS interno</span><span class="sxs-lookup"><span data-stu-id="2802c-162">Configure internal DNS</span></span>

   <span data-ttu-id="2802c-163">Il DNS deve essere funzionale e ricercato localmente per il traffico di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2802c-163">DNS is required to be functional and to be looked up locally for Microsoft 365 traffic.</span></span>

6. <span data-ttu-id="2802c-164">Convalidare l'endpoint di rete e la connettività delle porte</span><span class="sxs-lookup"><span data-stu-id="2802c-164">Validate network endpoint and port connectivity</span></span>

   <span data-ttu-id="2802c-165">Contoso ha eseguito strumenti di test della connettività di rete Microsoft per convalidare la connettività Microsoft 365 per i servizi cloud aziendali.</span><span class="sxs-lookup"><span data-stu-id="2802c-165">Contoso ran Microsoft network connectivity test tools to validate connectivity for Microsoft 365 for enterprise cloud services.</span></span>

7. <span data-ttu-id="2802c-166">Ottimizzare i computer dei dipendenti per la connettività di rete</span><span class="sxs-lookup"><span data-stu-id="2802c-166">Optimize employee computers for network connectivity</span></span>

   <span data-ttu-id="2802c-167">I singoli computer sono stati controllati per verificare che siano stati installati gli aggiornamenti più recenti del sistema operativo e che il monitoraggio della sicurezza degli endpoint sia attivo in tutti i client.</span><span class="sxs-lookup"><span data-stu-id="2802c-167">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring was active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="2802c-168">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="2802c-168">Next step</span></span>

<span data-ttu-id="2802c-169">Informazioni su come Contoso sta sfruttando i servizi di dominio [Active Directory locali](contoso-identity.md) nel cloud per i dipendenti e l'autenticazione federata per clienti e partner commerciali.</span><span class="sxs-lookup"><span data-stu-id="2802c-169">Learn how Contoso is [leveraging its on-premises Active Directory Domain Services in the cloud](contoso-identity.md) for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="2802c-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2802c-170">See also</span></span>

[<span data-ttu-id="2802c-171">Roadmap di rete per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2802c-171">Networking roadmap for Microsoft 365</span></span>](networking-roadmap-microsoft-365.md)

[<span data-ttu-id="2802c-172">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="2802c-172">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2802c-173">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="2802c-173">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
