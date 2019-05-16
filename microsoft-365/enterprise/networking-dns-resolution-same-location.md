---
title: 'Passaggio 2: configurare le connessioni Internet locali per ogni sede'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare la risoluzione DNS per migliorare le prestazioni.
ms.openlocfilehash: 2b3c38a9bf259f453121f7878992d1dc50f2ce97
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073266"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="9a7df-103">Passaggio 2: configurare le connessioni Internet locali per ogni sede</span><span class="sxs-lookup"><span data-stu-id="9a7df-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="9a7df-104">*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="9a7df-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="9a7df-p101">Nel Passaggio 2, verificare che ogni sede abbia connessioni Internet locali e usi server DNS locali. Entrambi questi elementi sono obbligatori per ridurre la latenza della connessione e verificare che i computer client locali effettuino connessioni al punto di ingresso più vicino ai servizi basati sul cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a7df-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="9a7df-p102">Nelle reti tradizionali per organizzazioni di grandi dimensioni, il traffico su Internet attraversa il backbone di rete fino a una connessione Internet centrale. Questo non funziona correttamente per l'ottimizzazione delle prestazioni per un'infrastruttura SaaS (Software-as-a-Service) distribuita in modo globale, che include i prodotti di Office 365 ed Enterprise Mobility + Security (EMS) in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a7df-p102">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection. This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Enterprise Mobility + Security (EMS) products in Microsoft 365.</span></span>

<span data-ttu-id="9a7df-p103">La rete Microsoft Global Network include server front-end per il set di servizi cloud per Microsoft 365 a livello globale. Per prestazioni ottimali, i client locali devono accedere al server front-end più vicino a livello geografico, anziché inoltrare il traffico tramite un backbone di rete e al server front-end più vicino alla connessione Internet centrale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a7df-p103">The Microsoft Global Network includes front end servers to the set of cloud services for Microsoft 365 all over the world. For the best performance, on-premises clients should access a front-end server that is geographically closest to them, rather than sending the traffic over a network backbone and to the front-end server that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="9a7df-p104">Per indirizzare una richiesta client al server front-end più vicino a livello geografico, i server DNS di Microsoft usano le query DNS corrispondenti alla richiesta di connessione iniziale del client. Pertanto, per la latenza di rete inferiore:</span><span class="sxs-lookup"><span data-stu-id="9a7df-p104">To direct a client request to the geographically nearest front-end server, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request. Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="9a7df-113">Tutte le sedi dell'organizzazione devvono avere connessioni Internet locali per il traffico di rete della categoria [Ottimizzazione](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="9a7df-113">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="9a7df-114">Ogni connessione Internet locale deve usare un server DNS locale per il traffico Internet in uscita da tale posizione.</span><span class="sxs-lookup"><span data-stu-id="9a7df-114">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="9a7df-115">Per ulteriori informazioni, vedere [Uscire dalle connessione di rete a livello locale](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span><span class="sxs-lookup"><span data-stu-id="9a7df-115">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="9a7df-116">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step2) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="9a7df-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="9a7df-117">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="9a7df-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="9a7df-118">Evitare fenomeni di "hairpinning" di rete</span><span class="sxs-lookup"><span data-stu-id="9a7df-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
