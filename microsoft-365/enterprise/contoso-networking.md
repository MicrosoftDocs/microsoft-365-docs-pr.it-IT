---
title: Servizi di rete per Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere l'infrastruttura di rete di Contoso e come utilizza la tecnologia SD-WAN per prestazioni di rete ottimali per i servizi cloud di Microsoft 365 Enterprise.
ms.openlocfilehash: 20279ac0aed1b7ad86e1fc8e1d78a412230eba52
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068343"
---
# <a name="networking-for-the-contoso-corporation"></a><span data-ttu-id="0d99c-103">Servizi di rete per Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="0d99c-103">Networking for the Contoso Corporation</span></span>

<span data-ttu-id="0d99c-p101">Per adottare un'infrastruttura cloud globale, i tecnici di rete di Contoso hanno realizzato un cambiamento fondamentale nel modo in cui il traffico di rete si sposta verso i servizi cloud. Invece di un modello hub e spoke interno, incentrato sulla connettività di rete e sul traffico per il livello successivo della gerarchia di uffici di Contoso, si sono adoperati per mappare le posizioni degli utenti al punto di uscita Internet locale e le connessioni locali alla posizione di rete Microsoft 365 più vicina su Internet.</span><span class="sxs-lookup"><span data-stu-id="0d99c-p101">To adopt a cloud-inclusive infrastructure, Contoso's network engineers realized the fundamental shift in the way that network traffic to cloud services travels. Instead of an internal hub and spoke model that focusses network connectivity and traffic for the next level of the Contoso office hierarchy, they worked to map user locations to local Internet egress and local connections to the closest Microsoft 365 network location on the Internet.</span></span>

## <a name="contosos-networking-infrastructure"></a><span data-ttu-id="0d99c-106">Infrastruttura di rete di Contoso</span><span class="sxs-lookup"><span data-stu-id="0d99c-106">Contoso's networking infrastructure</span></span>

<span data-ttu-id="0d99c-107">Gli elementi della rete di Contoso che collega gli uffici in tutto il mondo sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d99c-107">The elements of Contoso's network that links their offices across the globe are the following:</span></span>

- <span data-ttu-id="0d99c-108">Rete WAN MPLS (Multiprotocol Label Switching)</span><span class="sxs-lookup"><span data-stu-id="0d99c-108">Multiprotocol Label Switching (MPLS) WAN network</span></span>

  <span data-ttu-id="0d99c-p102">Una rete WAN MPLS collega la sede di Parigi alle filiali e le filiali agli uffici secondari in una configurazione spoke e hub. Si tratta di un collegamento che consente agli utenti di accedere ai server locali che costituiscono le applicazioni line-of-business dell'ufficio di Parigi. Lo stesso collegamento, inoltre, instrada il traffico Internet generico all'ufficio di Parigi dove i dispositivi per la sicurezza della rete eseguono lo scrubbing delle richieste. All'interno di ciascun ufficio, i router inviano il traffico agli host cablati o ai punti di accesso wireless sulle subnet, che utilizzano lo spazio di indirizzi IP privato.</span><span class="sxs-lookup"><span data-stu-id="0d99c-p102">An MPLS WAN network connects the Paris headquarters to regional offices and regional offices to satellite offices in a spoke and hub configuration. This is for users to access on-premises servers that make up line of business applications in the Paris office. It also routes any generic Internet traffic to the Paris office where network security devices scrub the requests. Within each office, routers deliver traffic to wired hosts or wireless access points on subnets, which use the private IP address space.</span></span>

- <span data-ttu-id="0d99c-113">Accesso locale diretto a Internet per il traffico di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0d99c-113">Local direct Internet access for Microsoft 365 traffic</span></span>

  <span data-ttu-id="0d99c-p103">Ciascun ufficio è dotato di un dispositivo SD-WAN (Software-Defined WAN) con uno o più circuiti di rete ISP Internet, con una connettività Internet specifica tramite un server proxy. Questo in genere viene implementato come collegamento WAN a un ISP locale che fornisce anche gli indirizzi IP pubblici e un server DNS locale.</span><span class="sxs-lookup"><span data-stu-id="0d99c-p103">Each office has a Software-Defined WAN (SD-WAN) device with one of more local Internet ISP network circuits, with its own Internet connectivity through a proxy server. This is typically implemented as a WAN link to a local ISP that also provides public IP addresses and a local DNS server.</span></span>

- <span data-ttu-id="0d99c-116">Presenza Internet</span><span class="sxs-lookup"><span data-stu-id="0d99c-116">Internet presence</span></span>

  <span data-ttu-id="0d99c-p104">Contoso possiede il nome di dominio pubblico contoso.com. Il sito Web pubblico di Contoso per ordinare prodotti è un set di server in un datacenter connesso a Internet nel campus di Parigi. Contoso utilizza un intervallo di indirizzi IP pubblico /24 su Internet.</span><span class="sxs-lookup"><span data-stu-id="0d99c-p104">Contoso owns the contoso.com public domain name. The Contoso public web site for ordering products is a set of servers in an Internet-connected datacenter in the Paris campus. Contoso uses a /24 public IP address range on the Internet.</span></span>

<span data-ttu-id="0d99c-120">La figura 1 mostra l’infrastruttura di rete di Contoso e le relative connessioni a Internet.</span><span class="sxs-lookup"><span data-stu-id="0d99c-120">Figure 1 shows Contoso's networking infrastructure and its connections to the Internet.</span></span>

![La rete di Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
<span data-ttu-id="0d99c-122">**Figura 1: la rete di Contoso**</span><span class="sxs-lookup"><span data-stu-id="0d99c-122">**Figure 1: Contoso's network**</span></span>

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a><span data-ttu-id="0d99c-123">Uso di SD-WAN per la connettività di rete ottimale a Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d99c-123">Use of SD-WAN for optimal network connectivity to Microsoft</span></span>

<span data-ttu-id="0d99c-124">Contoso ha seguito i [principi della connettività di rete di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) per:</span><span class="sxs-lookup"><span data-stu-id="0d99c-124">Contoso followed [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) to:</span></span>

1. <span data-ttu-id="0d99c-125">Identificare e differenziare il traffico di rete di Office 365</span><span class="sxs-lookup"><span data-stu-id="0d99c-125">Identify and differentiate Office 365 network traffic</span></span>
2. <span data-ttu-id="0d99c-126">Uscire dalle connessione di rete a livello locale</span><span class="sxs-lookup"><span data-stu-id="0d99c-126">Egress network connections locally</span></span>
3. <span data-ttu-id="0d99c-127">Evitare fenomeni di "hairpinning" di rete</span><span class="sxs-lookup"><span data-stu-id="0d99c-127">Avoid network hairpins</span></span>
4. <span data-ttu-id="0d99c-128">Bypassare i dispositivi di protezione di rete duplicati</span><span class="sxs-lookup"><span data-stu-id="0d99c-128">Bypass duplicate network security devices</span></span>

<span data-ttu-id="0d99c-129">Esistono tre categorie di traffico di rete per Office 365: Optimize, Allow e Default.</span><span class="sxs-lookup"><span data-stu-id="0d99c-129">There are three categories of network traffic for Office 365: Optimize, Allow, and Default.</span></span> <span data-ttu-id="0d99c-130">Il traffico della prima e della seconda categoria è un traffico di rete attendibile che viene crittografato e protetto a livello di endpoint ed è destinato alla rete Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d99c-130">Optimize and Allow traffic is trusted network traffic that is encrypted and secured at the endpoints and is destined for the Microsoft 365 network.</span></span>

<span data-ttu-id="0d99c-131">Contoso ha deciso di:</span><span class="sxs-lookup"><span data-stu-id="0d99c-131">Contoso decided to:</span></span>

- <span data-ttu-id="0d99c-132">Utilizzare il punto di uscita Internet diretto per il traffico delle categorie Optimize e Allow e di inoltrare tutto il traffico della categoria Default alla connessione Internet centrale di Parigi.</span><span class="sxs-lookup"><span data-stu-id="0d99c-132">Use direct Internet egress for Optimize and Allow category traffic and to forward all Default category traffic to the Paris-based central Internet connection.</span></span>

- <span data-ttu-id="0d99c-133">Distribuire dispositivi SD-WAN in ognuno degli uffici per seguire facilmente questi principi e ottenere prestazioni di rete ottimali per i servizi basati su cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d99c-133">Deploy SD-WAN devices at each of their office locations as a simple way to follow these principles and achieve optimal network performance for Microsoft 365 cloud-based services.</span></span>

  <span data-ttu-id="0d99c-134">I dispositivi SD-WAN sono dotati di una porta LAN per la rete di uffici locale e di più porte WAN.</span><span class="sxs-lookup"><span data-stu-id="0d99c-134">The SD-WAN devices have a LAN port for the local office network and multiple WAN ports.</span></span> <span data-ttu-id="0d99c-135">Una porta WAN si connette alla rete MPLS e le altre ai circuiti ISP locali.</span><span class="sxs-lookup"><span data-stu-id="0d99c-135">One WAN port connects to their MPLS network and another WAN port connects to a local ISP circuit.</span></span> <span data-ttu-id="0d99c-136">Il dispositivo SD-WAN instrada il traffico di rete delle categorie Optimize e Allow ai collegamenti ISP.</span><span class="sxs-lookup"><span data-stu-id="0d99c-136">The SD-WAN device routes Optimize and Allow category network traffic over the ISP link.</span></span>

## <a name="contosos-line-of-business-app-infrastructure"></a><span data-ttu-id="0d99c-137">Infrastruttura delle app line-of-business di Contoso</span><span class="sxs-lookup"><span data-stu-id="0d99c-137">Contoso's line of business app infrastructure</span></span>

<span data-ttu-id="0d99c-138">Contoso ha progettato l'infrastruttura Internet di applicazioni line-of-business e server per i seguenti motivi:</span><span class="sxs-lookup"><span data-stu-id="0d99c-138">Contoso has architected its line of business application and server intranet infrastructure for the following:</span></span>

- <span data-ttu-id="0d99c-139">Gli uffici secondari si avvalgono dei server di memorizzazione nella cache locale per archiviare documenti con accesso frequente e siti Web interni.</span><span class="sxs-lookup"><span data-stu-id="0d99c-139">Satellite offices use local caching servers to store frequently accessed documents and internal web sites.</span></span>
- <span data-ttu-id="0d99c-p107">Gli hub regionali si avvalgono di server applicazioni regionali per gli uffici regionali e quelli secondari. Tali server effettuano la sincronizzazione con i server della sede di Parigi.</span><span class="sxs-lookup"><span data-stu-id="0d99c-p107">Regional hubs use regional application servers for the regional and satellite offices. These servers synchronize with servers in the Paris headquarters.</span></span>
- <span data-ttu-id="0d99c-142">Il campus di Parigi dispone di data center che contengono i server applicazioni centralizzati che servono l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d99c-142">The Paris campus has the datacenters that contain the centralized application servers that serve the entire organization.</span></span>

<span data-ttu-id="0d99c-143">La Figura 2 mostra la percentuale di traffico di rete quando si accede ai server nell'Intranet di Contoso.</span><span class="sxs-lookup"><span data-stu-id="0d99c-143">Figure 2 shows the percentage of network traffic when accessing servers across Contoso’s intranet.</span></span>

![Infrastruttura di Contoso per applicazioni interne](../media/contoso-networking/contoso-networking-fig2.png)
 
<span data-ttu-id="0d99c-145">**Figura 2: infrastruttura di Contoso per applicazioni interne**</span><span class="sxs-lookup"><span data-stu-id="0d99c-145">**Figure 2: Contoso's infrastructure for internal applications**</span></span>

<span data-ttu-id="0d99c-p108">Per gli utenti negli uffici secondari o negli hub regionali, il 60% delle risorse necessarie ai dipendenti può essere fornito da server degli uffici secondari e degli hub regionali. Il restante 40% delle richieste di risorse deve passare attraverso un collegamento WAN al campus di Parigi.</span><span class="sxs-lookup"><span data-stu-id="0d99c-p108">For users in satellite or regional hub offices, 60% of the resources needed by employees can be served by satellite and regional hub office servers. The additional 40% of resource requests must go over the WAN link to the Paris campus.</span></span>

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a><span data-ttu-id="0d99c-148">Analisi della rete di Contoso e preparazione della rete per Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0d99c-148">Contoso's network analysis and preparation of their network for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0d99c-p109">La riuscita dell'adozione dei servizi di Microsoft 365 Enterprise da parte degli utenti di Contoso dipende dalla disponibilità e dalle prestazioni della connettività a Internet o direttamente ai servizi cloud Microsoft. Per pianificare e implementare la connettività ottimizzata ai servizi cloud Microsoft 365 Enterprise, Contoso ha intrapreso i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="0d99c-p109">Successful adoption of Microsoft 365 Enterprise services by Contoso’s users depend on highly available and performant connectivity to the Internet, or directly to Microsoft cloud services. Contoso took these steps to plan for and implement optimized connectivity to Microsoft 365 Enterprise cloud services:</span></span>

1. <span data-ttu-id="0d99c-151">Creazione di un diagramma reticolare WAN aziendale per semplificare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="0d99c-151">Created a company WAN network diagram to aid with planning</span></span>

   <span data-ttu-id="0d99c-p110">Contoso ha avviato la pianificazione della rete creando un diagramma che mostra le posizioni, la connettività di rete esistente, i dispositivi perimetrali di rete presenti e le classi di servizio gestite nella rete. Questo diagramma è stato utilizzato per ogni passaggio successivo nella pianificazione e nell'implementazione della connettività di rete.</span><span class="sxs-lookup"><span data-stu-id="0d99c-p110">Contoso started their network planning by creating a diagram showing their locations, the existing network connectivity, their existing network perimeter devices and classes of service that are managed on the network. They used this diagram for each subsequent step in the planning and implementation of networking connectivity.</span></span>

2. <span data-ttu-id="0d99c-154">Creazione di un piano per la connettività di rete di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0d99c-154">Created a plan for Microsoft 365 Enterprise network connectivity</span></span>

   <span data-ttu-id="0d99c-155">Contoso ha usato i [principi di connettività di rete di Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) e ha fornito le architetture di rete di riferimento per determinare la topologia SD-WAN come topologia preferita per la connettività di Office 365.</span><span class="sxs-lookup"><span data-stu-id="0d99c-155">Contoso used the [Office 365 network connectivity principles](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) and provided reference network architectures to determine SD-WAN as their preferred topology for Office 365 connectivity.</span></span>

3. <span data-ttu-id="0d99c-156">Analisi dell'utilizzo della connessione Internet e della larghezza di banda WAN MPLS in ogni ufficio e maggiore larghezza di banda in base alle esigenze</span><span class="sxs-lookup"><span data-stu-id="0d99c-156">Analyzed Internet connection utilization and MPLS WAN bandwidth at each office and increased bandwidth as needed</span></span>

   <span data-ttu-id="0d99c-157">È stato analizzato l'uso corrente di ogni ufficio e sono stati incrementati i circuiti in modo da rendere operativo il traffico basato sul cloud previsto di Microsoft 365 con una media del 20% della capacità inutilizzata.</span><span class="sxs-lookup"><span data-stu-id="0d99c-157">Each office was analyzed for the current usage and circuits were increased so that predicted Microsoft 365 cloud-based traffic would be operating with an average of 20% of unused capacity.</span></span>

4. <span data-ttu-id="0d99c-158">Ottimizzazione delle prestazioni per i servizi di rete Microsoft</span><span class="sxs-lookup"><span data-stu-id="0d99c-158">Optimized performance to Microsoft network services</span></span>

   <span data-ttu-id="0d99c-159">Contoso ha definito il set di endpoint di Office 365, Intune e Azure e ha configurato firewall, dispositivi di sicurezza e altri sistemi nel percorso Internet per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="0d99c-159">Contoso determined the set of Office 365, Intune, and Azure endpoints and configured firewalls, security devices, and other systems in the Internet path for optimal performance.</span></span> <span data-ttu-id="0d99c-160">Gli endpoint per il traffico di Office 365 delle categorie Optimize e Allow è stato configurato nei dispositivi SD-WAN per il routing sul circuito ISP.</span><span class="sxs-lookup"><span data-stu-id="0d99c-160">Endpoints for Office 365 Optimize and Allow category traffic was configured into the SD-WAN devices for routing over the ISP circuit.</span></span>

5. <span data-ttu-id="0d99c-161">Configurazione del DNS interno</span><span class="sxs-lookup"><span data-stu-id="0d99c-161">Configured internal DNS</span></span>

   <span data-ttu-id="0d99c-162">Il DNS deve essere funzionale e ricercato localmente per il traffico di Office 365.</span><span class="sxs-lookup"><span data-stu-id="0d99c-162">DNS is required to be functional and to be looked up locally for Office 365 traffic.</span></span>

6. <span data-ttu-id="0d99c-163">Convalida della connettività degli endpoint di rete e delle porte</span><span class="sxs-lookup"><span data-stu-id="0d99c-163">Validated network endpoint and port connectivity</span></span>

   <span data-ttu-id="0d99c-164">Contoso ha eseguito strumenti di test della connettività di rete forniti da Microsoft per convalidare la connettività per i servizi cloud di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0d99c-164">Contoso ran network connectivity test tools provided by Microsoft to validate connectivity for Microsoft 365 Enterprise cloud services.</span></span>

7. <span data-ttu-id="0d99c-165">Ottimizzazione dei computer dei dipendenti per la connettività di rete</span><span class="sxs-lookup"><span data-stu-id="0d99c-165">Optimized employee computers for network connectivity</span></span>

   <span data-ttu-id="0d99c-166">I singoli computer sono stati controllati per verificare che sino installati gli aggiornamenti più recenti del sistema operativo e che il monitoraggio della sicurezza degli endpoint sia attivo in tutti i client.</span><span class="sxs-lookup"><span data-stu-id="0d99c-166">Individual computers were checked to ensure that the latest operating system updates were installed and that endpoint security monitoring is active on all clients.</span></span>

## <a name="next-step"></a><span data-ttu-id="0d99c-167">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="0d99c-167">Next step</span></span>

<span data-ttu-id="0d99c-168">[Informazioni su](contoso-identity.md) come Contoso si avvale di Active Directory Domain Services (AD DS) locale nel cloud per i dipendenti dell'autenticazione federata per clienti e partner commerciali.</span><span class="sxs-lookup"><span data-stu-id="0d99c-168">[Learn](contoso-identity.md) how Contoso is leveraging its on-premises Active Directory Domain Services (AD DS) in the cloud for employees and federating authentication for customers and business partners.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d99c-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d99c-169">See also</span></span>

[<span data-ttu-id="0d99c-170">Servizi di rete per Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="0d99c-170">Networking for Microsoft 365 Enterprise</span></span>](networking-infrastructure.md)

[<span data-ttu-id="0d99c-171">Guida alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="0d99c-171">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="0d99c-172">Guide dei laboratori di testing</span><span class="sxs-lookup"><span data-stu-id="0d99c-172">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
