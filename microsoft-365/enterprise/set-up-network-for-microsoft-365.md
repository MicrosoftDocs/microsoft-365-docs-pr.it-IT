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
description: Sono disponibili collegamenti ad articoli contenenti informazioni utili per configurare la rete per Microsoft 365, tra cui una panoramica della connettività di rete e un elenco di endpoint.
ms.openlocfilehash: f0e0499c70745d31399240372c190758285408aa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691010"
---
# <a name="set-up-your-network-for-microsoft-365"></a>Configurare la rete per Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Una parte importante dell'onboarding di Microsoft 365 è garantire che le connessioni di rete e Internet siano configurate per l'accesso ottimizzato. La configurazione della rete locale per l'accesso a un cloud SaaS (software-as-a-Service) distribuito a livello globale è diversa da una rete tradizionale ottimizzata per il traffico verso i centri dati locali e una connessione Internet centralizzata. 

Consultare questi articoli per comprendere le differenze principali e per modificare i dispositivi periferici, i computer client e la rete locale in uso per prestazioni ottimali per gli utenti locali.

## <a name="how-microsoft-365-networking-works"></a>Funzionamento della rete Microsoft 365

Per una panoramica della connettività per Microsoft 365, vedere gli articoli seguenti:

- [Informazioni generali sulla connettività di rete di Microsoft 365](microsoft-365-networking-overview.md)
- [Principi di connettività di rete Microsoft 365](microsoft-365-network-connectivity-principles.md)
- [Valutazione della connettività di rete di Microsoft 365](assessing-network-connectivity.md)

Per informazioni su come migliorare le prestazioni, vedere [pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](network-planning-and-performance.md).

## <a name="support-microsoft-365-networking-as-a-network-equipment-vendor"></a>Supporto di Microsoft 365 networking come fornitore di apparecchiature di rete

Se si è un fornitore di apparecchiature di rete, partecipare a [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md). Iscriversi al programma per creare i principi di connettività di rete Office 365 ne propri prodotti e soluzioni. 

## <a name="office-365-endpoints"></a>Endpoint di Office 365

Gli endpoint sono il set di indirizzi IP di destinazione, i nomi di dominio DNS e gli URL per il traffico di Office 365 su Internet. 

Per ottimizzare le prestazioni di servizi basati sul cloud di Office 365, alcuni endpoint richiedono una gestione speciale da parte dei i browser client e dei dispositivi nella propria rete perimetrale. Questi dispositivi includono firewall, SSL Break and Inspect, dispositivi di ispezione dei pacchetti e sistemi di prevenzione della perdita di dati.

Vedere [Gestione degli endpoint di Office 365](managing-office-365-endpoints.md) per i dettagli.

Esistono attualmente cinque cloud di Office 365 diversi. Questa tabella consente di accedere all'elenco di endpoint per ciascuno di essi.

| Endpoint | Descrizione |
|:-------|:-----|
| [Endpoint in tutto il mondo](urls-and-ip-address-ranges.md) | Gli endpoint per abbonamenti a Office 365 nel mondo, tra cui US Government Community Cloud (GCC). |
| [Endpoint del U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) | Gli endpoint per gli abbonamenti del Dipartimento della Difesa degli Stati Uniti (DoD). |
| [Endpoint del U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) | Gli endpoint per gli abbonamenti di US Government Community Cloud High (GCC High). |
| [Office 365 gestito dagli endpoint di 21Vianet](urls-and-ip-address-ranges-21vianet.md) | Gli endpoint di Office 365 gestiti da 21Vianet, progettato per soddisfare le esigenze di Office 365 in Cina. |
| [Endpoint di Office 365 Germany](microsoft-365-germany-endpoints.md) | Gli endpoint di un cloud separato in Europa per i clienti più regolamentati in Germania, l’Unione Europea (UE) e l'Associazione europea di libero scambio (EFTA). |
|||

Per ottenere automaticamente l'elenco più recente degli endpoint per il cloud di Office 365, vedere il [Servizio Web di indirizzo IP e URL di Office 365](microsoft-365-ip-web-service.md).

Per altri endpoint, vedere gli articoli:

- [Altri endpoint non inclusi nel servizio Web](additional-office365-ip-addresses-and-urls.md)
- [Richieste di rete in Office 2016 per Mac](network-requests-in-office-2016-for-mac.md)


## <a name="additional-topics-for-microsoft-365-networking"></a>Ulteriori argomenti per Microsoft 365 networking

Per ulteriori informazioni, vedere gli articoli relativi a argomenti specializzati in Microsoft 365 Networking:

- [Reti per la distribuzione di contenuti](content-delivery-networks.md)
- [Supporto IPv6 nei servizi Office 365](ipv6-support.md)
- [Supporto NAT con Office 365](nat-support-with-microsoft-365.md)

## <a name="expressroute-for-microsoft-365"></a>ExpressRoute per Microsoft 365

Per informazioni sull'uso di ExpressRoute per il traffico di Office 365, consultare gli articoli seguenti:

- [Azure ExpressRoute per Office 365](azure-expressroute.md)
- [Implementazione di ExpressRoute per Office 365](implementing-expressroute.md)
- [Pianificazione della rete con ExpressRoute per Office 365](network-planning-with-expressroute.md)
- [Routing con ExpressRoute per Office 365](routing-with-expressroute.md)
