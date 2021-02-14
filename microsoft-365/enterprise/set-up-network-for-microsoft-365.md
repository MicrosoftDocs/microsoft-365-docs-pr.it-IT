---
title: Configurare la rete per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Collegamenti ad articoli con informazioni utili per configurare la rete per Microsoft 365, tra cui una panoramica della connettività di rete e un elenco di endpoint.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691010"
---
# <a name="set-up-your-network-for-microsoft-365"></a><span data-ttu-id="e78a0-103">Configurare la rete per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-103">Set up your network for Microsoft 365</span></span>

<span data-ttu-id="e78a0-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="e78a0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e78a0-105">Una parte importante dell'onboarding di Microsoft 365 è garantire che la rete e le connessioni Internet siano impostate per l'accesso ottimizzato.</span><span class="sxs-lookup"><span data-stu-id="e78a0-105">An important part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="e78a0-106">La configurazione della rete locale per l'accesso a un cloud Software-as-a-Service (SaaS) distribuito a livello globale è diversa da una rete tradizionale ottimizzata per il traffico verso datacenter locali e una connessione Internet centrale.</span><span class="sxs-lookup"><span data-stu-id="e78a0-106">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="e78a0-107">Consultare questi articoli per comprendere le differenze principali e per modificare i dispositivi periferici, i computer client e la rete locale in uso per prestazioni ottimali per gli utenti locali.</span><span class="sxs-lookup"><span data-stu-id="e78a0-107">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="how-microsoft-365-networking-works"></a><span data-ttu-id="e78a0-108">Come funziona la rete di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-108">How Microsoft 365 networking works</span></span>

<span data-ttu-id="e78a0-109">Vedere questi articoli per una panoramica della connettività per Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e78a0-109">See these articles for an overview of connectivity for Microsoft 365:</span></span>

- [<span data-ttu-id="e78a0-110">Informazioni generali sulla connettività di rete di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-110">Microsoft 365 networking connectivity overview</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="e78a0-111">Principi di connettività di rete di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-111">Microsoft 365 network connectivity principles</span></span>](microsoft-365-network-connectivity-principles.md)
- [<span data-ttu-id="e78a0-112">Valutazione della connettività di rete di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-112">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)

<span data-ttu-id="e78a0-113">Per consigli su come migliorare le prestazioni, vedere [Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="e78a0-113">For advice on enhancing performance, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a><span data-ttu-id="e78a0-114">Supportare la rete di Microsoft 365 come fornitore di apparecchiature di rete</span><span class="sxs-lookup"><span data-stu-id="e78a0-114">Support Microsoft 365 networking as a network equipment vendor</span></span>

<span data-ttu-id="e78a0-p102">Se si è un fornitore di apparecchiature di rete, partecipare a [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md). Iscriversi al programma per creare i principi di connettività di rete Office 365 ne propri prodotti e soluzioni.</span><span class="sxs-lookup"><span data-stu-id="e78a0-p102">If you are a network equipment vendor, join the [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md). Enroll in the program to build Office 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="office-365-endpoints"></a><span data-ttu-id="e78a0-117">Endpoint di Office 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-117">Office 365 endpoints</span></span>

<span data-ttu-id="e78a0-118">Gli endpoint sono il set di indirizzi IP di destinazione, i nomi di dominio DNS e gli URL per il traffico di Office 365 su Internet.</span><span class="sxs-lookup"><span data-stu-id="e78a0-118">Endpoints are the set of destination IP addresses, DNS domain names, and URLs for Office 365 traffic on the Internet.</span></span> 

<span data-ttu-id="e78a0-p103">Per ottimizzare le prestazioni di servizi basati sul cloud di Office 365, alcuni endpoint richiedono una gestione speciale da parte dei i browser client e dei dispositivi nella propria rete perimetrale. Questi dispositivi includono firewall, SSL Break and Inspect, dispositivi di ispezione dei pacchetti e sistemi di prevenzione della perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="e78a0-p103">To optimize performance to Office 365 cloud-based services, some endpoints need special handling by your client browsers and the devices in your edge network. These devices include firewalls, SSL Break and Inspect and packet inspection devices, and data loss prevention systems.</span></span>

<span data-ttu-id="e78a0-121">Vedere [Gestione degli endpoint di Office 365](managing-office-365-endpoints.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="e78a0-121">See [Managing Office 365 endpoints](managing-office-365-endpoints.md) for the details.</span></span>

<span data-ttu-id="e78a0-p104">Esistono attualmente cinque cloud di Office 365 diversi. Questa tabella consente di accedere all'elenco di endpoint per ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="e78a0-p104">There are currently five different Office 365 clouds. This table takes you to the list of endpoints for each one.</span></span>

| <span data-ttu-id="e78a0-124">Endpoint</span><span class="sxs-lookup"><span data-stu-id="e78a0-124">Endpoints</span></span> | <span data-ttu-id="e78a0-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e78a0-125">Description</span></span> |
|:-------|:-----|
| [<span data-ttu-id="e78a0-126">Endpoint in tutto il mondo</span><span class="sxs-lookup"><span data-stu-id="e78a0-126">Worldwide endpoints</span></span>](urls-and-ip-address-ranges.md) | <span data-ttu-id="e78a0-127">Gli endpoint per abbonamenti a Office 365 nel mondo, tra cui US Government Community Cloud (GCC).</span><span class="sxs-lookup"><span data-stu-id="e78a0-127">The endpoints for worldwide Office 365 subscriptions, which include the United States Government Community Cloud (GCC).</span></span> |
| [<span data-ttu-id="e78a0-128">Endpoint del U.S. Government DoD</span><span class="sxs-lookup"><span data-stu-id="e78a0-128">U.S. Government DoD endpoints</span></span>](microsoft-365-u-s-government-dod-endpoints.md) | <span data-ttu-id="e78a0-129">Gli endpoint per gli abbonamenti del Dipartimento della Difesa degli Stati Uniti (DoD).</span><span class="sxs-lookup"><span data-stu-id="e78a0-129">The endpoints for United States Department of Defense (DoD) subscriptions.</span></span> |
| [<span data-ttu-id="e78a0-130">Endpoint del U.S. Government GCC High</span><span class="sxs-lookup"><span data-stu-id="e78a0-130">U.S. Government GCC High endpoints</span></span>](microsoft-365-u-s-government-gcc-high-endpoints.md) | <span data-ttu-id="e78a0-131">Gli endpoint per gli abbonamenti di US Government Community Cloud High (GCC High).</span><span class="sxs-lookup"><span data-stu-id="e78a0-131">The endpoints for United States Government Community Cloud High (GCC High) subscriptions.</span></span> |
| [<span data-ttu-id="e78a0-132">Office 365 gestito dagli endpoint di 21Vianet</span><span class="sxs-lookup"><span data-stu-id="e78a0-132">Office 365 operated by 21Vianet endpoints</span></span>](urls-and-ip-address-ranges-21vianet.md) | <span data-ttu-id="e78a0-133">Gli endpoint di Office 365 gestiti da 21Vianet, progettato per soddisfare le esigenze di Office 365 in Cina.</span><span class="sxs-lookup"><span data-stu-id="e78a0-133">The endpoints for Office 365 operated by 21Vianet, which is designed to meet the needs for Office 365 in China.</span></span> |
| [<span data-ttu-id="e78a0-134">Endpoint di Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="e78a0-134">Office 365 Germany endpoints</span></span>](microsoft-365-germany-endpoints.md) | <span data-ttu-id="e78a0-135">Gli endpoint di un cloud separato in Europa per i clienti più regolamentati in Germania, l’Unione Europea (UE) e l'Associazione europea di libero scambio (EFTA).</span><span class="sxs-lookup"><span data-stu-id="e78a0-135">The endpoints for a separate cloud in Europe for the most regulated customers in Germany, the European Union (EU), and the European Free Trade Association (EFTA).</span></span> |
|||

<span data-ttu-id="e78a0-136">Per ottenere automaticamente l'elenco più recente degli endpoint per il cloud di Office 365, vedere il [Servizio Web di indirizzo IP e URL di Office 365](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="e78a0-136">To automate getting the latest list of endpoints for your Office 365 cloud, see the [Office 365 IP Address and URL Web service](microsoft-365-ip-web-service.md).</span></span>

<span data-ttu-id="e78a0-137">Per altri endpoint, vedere gli articoli:</span><span class="sxs-lookup"><span data-stu-id="e78a0-137">For additional endpoints, see these articles:</span></span>

- [<span data-ttu-id="e78a0-138">Altri endpoint non inclusi nel servizio Web</span><span class="sxs-lookup"><span data-stu-id="e78a0-138">Additional endpoints not included in the Web service</span></span>](additional-office365-ip-addresses-and-urls.md)
- [<span data-ttu-id="e78a0-139">Richieste di rete in Office 2016 per Mac</span><span class="sxs-lookup"><span data-stu-id="e78a0-139">Network requests in Office 2016 for Mac</span></span>](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a><span data-ttu-id="e78a0-140">Argomenti aggiuntivi per la rete di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-140">Additional topics for Microsoft 365 networking</span></span>

<span data-ttu-id="e78a0-141">Vedere questi articoli per argomenti specializzati nella rete di Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="e78a0-141">See these articles for specialized topics in Microsoft 365 networking:</span></span>

- [<span data-ttu-id="e78a0-142">Reti per la distribuzione di contenuti</span><span class="sxs-lookup"><span data-stu-id="e78a0-142">Content delivery networks</span></span>](content-delivery-networks.md)
- [<span data-ttu-id="e78a0-143">Supporto IPv6 nei servizi Office 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-143">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
- [<span data-ttu-id="e78a0-144">Supporto NAT con Office 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-144">NAT support with Office 365</span></span>](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a><span data-ttu-id="e78a0-145">ExpressRoute per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-145">ExpressRoute for Microsoft 365</span></span>

<span data-ttu-id="e78a0-146">Per informazioni sull'uso di ExpressRoute per il traffico di Office 365, consultare gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="e78a0-146">See these articles for information on the use of ExpressRoute for Office 365 traffic:</span></span>

- [<span data-ttu-id="e78a0-147">Azure ExpressRoute per Office 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-147">Azure ExpressRoute for Office 365</span></span>](azure-expressroute.md)
- [<span data-ttu-id="e78a0-148">Implementazione di ExpressRoute per Office 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-148">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)
- [<span data-ttu-id="e78a0-149">Pianificazione della rete con ExpressRoute per Office 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-149">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="e78a0-150">Routing con ExpressRoute per Office 365</span><span class="sxs-lookup"><span data-stu-id="e78a0-150">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)
