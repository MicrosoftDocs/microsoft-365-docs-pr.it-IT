---
title: 'Passaggio 2: configurare le connessioni Internet locali per ogni sede'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare la risoluzione DNS per migliorare le prestazioni.
ms.openlocfilehash: 8b4302c06e75c59a1b99eb60399c9df897ad17ea
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066663"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="c9361-103">Passaggio 2: configurare le connessioni Internet locali per ogni sede</span><span class="sxs-lookup"><span data-stu-id="c9361-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="c9361-104">*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c9361-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1: collegamento in rete](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="c9361-p101">Nel Passaggio 2, verificare che ogni sede abbia connessioni Internet locali e usi server DNS locali. Entrambi questi elementi sono obbligatori per ridurre la latenza della connessione e verificare che i computer client locali effettuino connessioni al punto di ingresso più vicino ai servizi basati sul cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9361-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="c9361-108">Nelle reti tradizionali per le aziende il traffico Internet viaggia lungo il backbone della rete verso una connessione Internet centrale.</span><span class="sxs-lookup"><span data-stu-id="c9361-108">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection.</span></span> <span data-ttu-id="c9361-109">Questo comportamento non è ideale per ottimizzare le prestazioni di un'infrastruttura SaaS (Software-as-a-Service) distribuita a livello globale, che include i prodotti Office 365 e Intune in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9361-109">This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Intune products in Microsoft 365.</span></span>

<span data-ttu-id="c9361-110">La rete globale di Microsoft include un'infrastruttura *frontdoor di servizi distribuiti*, un server perimetrale di rete a disponibilità e scalabilità elevata con posizioni geograficamente distribuite.</span><span class="sxs-lookup"><span data-stu-id="c9361-110">The Microsoft Global Network includes a *Distributed Service Front Door* infrastructure, a highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="c9361-111">Tale infrastruttura termina le connessioni degli utenti finali presso un server frontdoor e instrada in modo efficiente il traffico degli utenti finali all'interno della rete globale Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9361-111">It terminates end user connections at a front door server and efficiently routes end user traffic within the Microsoft Global Network.</span></span>

![Rete globale Microsoft](../media/networking-dns-resolution-same-location/microsoft-global-network.png)

<span data-ttu-id="c9361-113">Per prestazioni ottimali, i client locali devono accedere a una posizione di frontdoor più vicina a livello geografico, anziché inoltrare il traffico tramite un backbone di rete e al frontdoor più vicino alla connessione Internet centrale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9361-113">For the best performance, on-premises clients should access a front door location that is geographically closest to them, rather than sending the traffic over a network backbone and to the front door that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="c9361-114">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="c9361-114">Here’s an example.</span></span>

![Esempio di utilizzo della rete globale Microsoft](../media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

<span data-ttu-id="c9361-116">Quando un utente della filiale di Parigi vuole accedere a un sito di SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="c9361-116">When a user in the Paris branch office wants to access a SharePoint Online site:</span></span>

1. <span data-ttu-id="c9361-117">Invia una query DNS per risolvere un nome, ad esempio contoso.sharepoint.com.</span><span class="sxs-lookup"><span data-stu-id="c9361-117">It sends a DNS query to resolve a name, such as contoso.sharepoint.com.</span></span> 
2. <span data-ttu-id="c9361-118">Il server DNS fornito dall'ISP inoltra tale query a un server DNS Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9361-118">The DNS server provided by the ISP forwards that query to a Microsoft DNS server.</span></span>
3. <span data-ttu-id="c9361-119">I server DNS Microsoft abbinano l'indirizzo IP di origine della query DNS inoltrata all'area geografica assegnata all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c9361-119">Microsoft’s DNS servers match the source IP address of the forwarded DNS query to the region of the world assigned that address.</span></span> <span data-ttu-id="c9361-120">Il server DNS Microsoft risponde con l'indirizzo IP del frontdoor della rete Microsoft più vicino in Europa.</span><span class="sxs-lookup"><span data-stu-id="c9361-120">The Microsoft DNS server responds with the IP address of the nearest Microsoft Network front door in Europe.</span></span>
4. <span data-ttu-id="c9361-121">Il server DNS ISP invia tale indirizzo IP all'utente.</span><span class="sxs-lookup"><span data-stu-id="c9361-121">The ISP DNS server sends that IP address to the user.</span></span>
5. <span data-ttu-id="c9361-122">L'utente avvia una connessione al server di SharePoint tramite il frontdoor europeo.</span><span class="sxs-lookup"><span data-stu-id="c9361-122">The user initiates a connection to the SharePoint server through the Europe front door.</span></span>

<span data-ttu-id="c9361-123">Per indirizzare una richiesta client al frontdoor più vicino a livello geografico, i server DNS di Microsoft usano le query DNS corrispondenti alla richiesta di connessione iniziale del client.</span><span class="sxs-lookup"><span data-stu-id="c9361-123">To direct a client request to the geographically nearest front door, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request.</span></span> <span data-ttu-id="c9361-124">Pertanto, per la latenza di rete inferiore:</span><span class="sxs-lookup"><span data-stu-id="c9361-124">Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="c9361-125">Tutte le sedi dell'organizzazione devvono avere connessioni Internet locali per il traffico di rete della categoria [Ottimizzazione](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="c9361-125">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="c9361-126">Ogni connessione Internet locale deve usare un server DNS locale per il traffico Internet in uscita da tale posizione.</span><span class="sxs-lookup"><span data-stu-id="c9361-126">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="c9361-127">Per ulteriori informazioni, vedere [Uscire dalle connessione di rete a livello locale](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span><span class="sxs-lookup"><span data-stu-id="c9361-127">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="c9361-128">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step2) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="c9361-128">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c9361-129">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="c9361-129">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="c9361-131">Evitare fenomeni di "hairpinning" di rete</span><span class="sxs-lookup"><span data-stu-id="c9361-131">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
