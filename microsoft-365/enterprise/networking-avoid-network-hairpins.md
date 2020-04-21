---
title: 'Passaggio 3: evitare fenomeni di "hairpinning" di rete'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e rimuovere fenomeni di "hairpinning" di rete per prestazioni migliori.
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583426"
---
# <a name="step-3-avoid-network-hairpins"></a><span data-ttu-id="eccb3-103">Passaggio 3: evitare fenomeni di "hairpinning" di rete</span><span class="sxs-lookup"><span data-stu-id="eccb3-103">Step 3: Avoid network hairpins</span></span>

<span data-ttu-id="eccb3-104">*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="eccb3-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1: collegamento in rete](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="eccb3-106">Si verifica un ["hairpinning" di rete](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) quando il traffico associato per una destinazione viene prima indirizzato a un'altra posizione intermedia, ad esempio uno stack di sicurezza locale, un broker di accesso cloud o un gateway Web basato sul cloud.</span><span class="sxs-lookup"><span data-stu-id="eccb3-106">A [network hairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) happens when traffic bound for a destination is first directed to another intermediate location, such as an on-premises security stack, cloud access broker, or cloud-based web gateway.</span></span> <span data-ttu-id="eccb3-107">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="eccb3-107">Here is an example.</span></span>

![Esempio di "hairpinning" di rete](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

<span data-ttu-id="eccb3-109">Un "hairpinning" di rete può dipendere anche da un routing insufficiente in Internet causato dai provider di servizi di rete.</span><span class="sxs-lookup"><span data-stu-id="eccb3-109">A network hairpin could also be caused by poor routing on the Internet due to network service providers.</span></span> 

<span data-ttu-id="eccb3-110">Un "hairpinning" aggiunge latenza e può potenzialmente reindirizzare il traffico a una posizione geograficamente distante.</span><span class="sxs-lookup"><span data-stu-id="eccb3-110">A hairpin adds latency and can potentially redirect traffic to a geographically distant location.</span></span>

<span data-ttu-id="eccb3-p102">Per ottimizzare le prestazioni per il traffico verso i servizi basati sul cloud di Microsoft 365, verificare se l'ISP che fornisce la connessione Internet locale dispone di una relazione di peering diretto con Microsoft Global Network nelle immediate vicinanze della posizione in questione. Tali connessioni non hanno hairpin.</span><span class="sxs-lookup"><span data-stu-id="eccb3-p102">To optimize performance for traffic to Microsoft 365 cloud-based services, check whether the ISP providing the local Internet connection has a direct peering relationship with the Microsoft Global Network in close proximity to that location. These connections do not have hairpins.</span></span>

<span data-ttu-id="eccb3-p103">Se si utilizza una rete basata sul cloud o servizi di sicurezza per il traffico di Microsoft 365, verificare che venga valutato l'effetto di hairpinning e che venga interpretato il suo impatto sulle prestazioni. Esaminare quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="eccb3-p103">If you use cloud-based network or security services for your Microsoft 365 traffic, ensure that the hairpinning effect is evaluated and its impact on performance is understood. Examine the following:</span></span>

- <span data-ttu-id="eccb3-115">Il numero e le posizioni dei provider di servizi con cui viene inoltrato il traffico in relazione alle succursali e ai punti di peering di Microsoft Global Network</span><span class="sxs-lookup"><span data-stu-id="eccb3-115">The number and locations of your service providers through which the traffic is forwarded in relationship to your branch offices and Microsoft Global Network peering points</span></span> 
- <span data-ttu-id="eccb3-116">La qualità della relazione di peering della rete del provider di servizi con l'ISP e Microsoft</span><span class="sxs-lookup"><span data-stu-id="eccb3-116">The quality of the network peering relationship of the service provider with your ISP and Microsoft</span></span> 
- <span data-ttu-id="eccb3-117">L'impatto del backhauling sulle prestazioni nell'infrastruttura del provider di servizi</span><span class="sxs-lookup"><span data-stu-id="eccb3-117">The performance impact of backhauling in the service provider infrastructure</span></span>

<span data-ttu-id="eccb3-118">Ove possibile, configurare i router periferici in modo da inviare direttamente il traffico di Microsoft 365 attendibile, anziché inoltrarlo tramite proxy o tunneling attraverso un fornitore di sicurezza di rete basato sul cloud o un cloud di terze parti che elabora il traffico di Internet.</span><span class="sxs-lookup"><span data-stu-id="eccb3-118">Whenever possible, configure your edge routers to send trusted Microsoft 365 traffic directly, instead of proxying or tunneling through a third-party cloud or cloud-based network security vendor that processes your Internet traffic.</span></span> 

![Esempio di bypass dell'"hairpinning" di rete](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

<span data-ttu-id="eccb3-120">Per testare la vicinanza a un punto di ingresso per la rete globale di Microsoft e quanto si è vicini al punto in cui la rete aziendale si collega all'ISP, usare lo [strumento di onboarding della rete di Office 365](https://connectivity.office.com/).</span><span class="sxs-lookup"><span data-stu-id="eccb3-120">To test how close you are to an entry point for Microsoft’s global network and how close you are to the point where your organization network connects to your ISP, use the [Office 365 Network Onboarding tool](https://connectivity.office.com/).</span></span>

<span data-ttu-id="eccb3-121">Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step3) per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="eccb3-121">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step3) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="eccb3-122">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="eccb3-122">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="eccb3-124">Configurare il bypass di traffico</span><span class="sxs-lookup"><span data-stu-id="eccb3-124">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
