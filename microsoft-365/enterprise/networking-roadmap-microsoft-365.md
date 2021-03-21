---
title: Roadmap di rete per Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Roadmap per l'implementazione della rete Di Microsoft 365.
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923553"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="452d8-103">Roadmap di rete per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="452d8-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="452d8-104">Microsoft 365 per le aziende include servizi cloud di collaborazione e produttività, Microsoft Intune e molti servizi di identità e sicurezza di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="452d8-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="452d8-105">Tutti questi servizi basati su cloud si basano su sicurezza, prestazioni e affidabilità delle connessioni dei dispositivi client su Internet o circuiti dedicati.</span><span class="sxs-lookup"><span data-stu-id="452d8-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="452d8-106">Per ospitare questi servizi e renderli disponibili per i clienti in tutto il mondo, Microsoft ha progettato un'infrastruttura di rete che mette in evidenza le prestazioni e l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="452d8-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="452d8-107">Una parte fondamentale dell'onboarding di Microsoft 365 è garantire che la rete e le connessioni Internet siano impostate per l'accesso ottimizzato.</span><span class="sxs-lookup"><span data-stu-id="452d8-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="452d8-108">La configurazione della rete locale per accedere a un cloud SaaS (Software-as-a-Service) distribuito a livello globale è diversa da una rete tradizionale ottimizzata per il traffico verso datacenter locali e una connessione Internet centrale.</span><span class="sxs-lookup"><span data-stu-id="452d8-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="452d8-109">Consultare questi articoli per comprendere le differenze principali e per modificare i dispositivi periferici, i computer client e la rete locale in uso per prestazioni ottimali per gli utenti locali.</span><span class="sxs-lookup"><span data-stu-id="452d8-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="452d8-110">Pianificare</span><span class="sxs-lookup"><span data-stu-id="452d8-110">Plan</span></span>

<span data-ttu-id="452d8-111">Nella fase di pianificazione dell'implementazione di rete:</span><span class="sxs-lookup"><span data-stu-id="452d8-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="452d8-112">Informazioni sul funzionamento della rete di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="452d8-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="452d8-113">Valutare la connettività di rete corrente</span><span class="sxs-lookup"><span data-stu-id="452d8-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="452d8-114">Determinare se ExpressRoute è giusto per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="452d8-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="452d8-115">Pianificare i dispositivi di rete</span><span class="sxs-lookup"><span data-stu-id="452d8-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="452d8-116">Configurare la rete per la migrazione</span><span class="sxs-lookup"><span data-stu-id="452d8-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="452d8-117">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="452d8-117">Deploy</span></span>

<span data-ttu-id="452d8-118">Nella fase di distribuzione dell'implementazione di rete:</span><span class="sxs-lookup"><span data-stu-id="452d8-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="452d8-119">Verificare che la rete aziendale sia ottimizzata per la connettività di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="452d8-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="452d8-120">Aggiungere i domini DNS per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="452d8-120">Add the DNS domains for your organization</span></span>](../admin/setup/add-domain.md)
- [<span data-ttu-id="452d8-121">Ottimizzare la connettività agli endpoint di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="452d8-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="452d8-122">Ottimizzare la connettività per i lavoratori remoti</span><span class="sxs-lookup"><span data-stu-id="452d8-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="452d8-123">Se necessario, [configurare ExpressRoute](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="452d8-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="452d8-124">Gestione</span><span class="sxs-lookup"><span data-stu-id="452d8-124">Manage</span></span>

<span data-ttu-id="452d8-125">Nella fase di gestione dell'implementazione di rete:</span><span class="sxs-lookup"><span data-stu-id="452d8-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="452d8-126">Verificare che i dispositivi di rete utilizzino gli endpoint di Office 365 più recenti</span><span class="sxs-lookup"><span data-stu-id="452d8-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="452d8-127">Monitorare e ottimizzare le prestazioni di rete</span><span class="sxs-lookup"><span data-stu-id="452d8-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="452d8-128">Monitorare le connessioni ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="452d8-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="452d8-129">Fornitori di apparecchiature di rete</span><span class="sxs-lookup"><span data-stu-id="452d8-129">Network equipment vendors</span></span>

<span data-ttu-id="452d8-130">Se si è un fornitore di apparecchiature di rete, partecipare al Programma per i partner di [rete di Microsoft 365.](microsoft-365-networking-partner-program.md)</span><span class="sxs-lookup"><span data-stu-id="452d8-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="452d8-131">Iscriversi al programma per creare i principi di connettività di rete di Microsoft 365 nei prodotti e nelle soluzioni.</span><span class="sxs-lookup"><span data-stu-id="452d8-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="452d8-132">Come Contoso ha fatto rete per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="452d8-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="452d8-133">Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha ottimizzato i propri dispositivi di rete e le connessioni Internet](contoso-networking.md) per i servizi cloud Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="452d8-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="452d8-135">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="452d8-135">Next step</span></span>

<span data-ttu-id="452d8-136">Iniziare la pianificazione della rete con la panoramica della connettività di rete di [Microsoft 365.](microsoft-365-networking-overview.md)</span><span class="sxs-lookup"><span data-stu-id="452d8-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>