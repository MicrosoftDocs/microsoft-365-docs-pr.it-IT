---
title: Endpoint DOD di Office 365 US Government
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: 5d7dce60-4892-4b58-b45e-ee42fe8a907f
f1.keywords:
- NOCSH
description: Office 365 richiede la connettività a Internet. Gli endpoint seguenti devono essere raggiungibili solo per i clienti che usano i piani U.S. Government DoD di Office 365.
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c19aa281dea439f1ae41e6b20f917f8fe7439d3e
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787776"
---
# <a name="office-365-us-government-dod-endpoints"></a>Endpoint di Office 365 U.S. Government DoD

*Si applica a: Amministratore di Office 365*

 Office 365 richiede la connettività a Internet. Gli endpoint seguenti devono essere raggiungibili solo per i clienti che usano i piani U.S. Government DoD di Office 365.
  
 **Endpoint di Office 365:** [Worldwide (compreso GCC)](urls-and-ip-address-ranges.md) | [Office 365 gestito da 21Vianet](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 Germany](microsoft-365-germany-endpoints.md) | *Office 365 U.S. Government DoD* | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Ultimo aggiornamento:** 01/04/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abbonamento al Log delle modifiche](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Download:** elenco completo in [formato JSON](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Iniziare con [la gestione degli endpoint di Office 365](managing-office-365-endpoints.md) per comprendere i suggerimenti per la gestione della connettività di rete tramite questi dati. I dati degli endpoint vengono aggiornati all'inizio di ogni mese con nuovi INDIRIZZI IP e URL pubblicati 30 giorni prima di essere attivi. Ciò consente ai clienti che non dispongono ancora di aggiornamenti automatici di completare i processi prima che sia necessaria una nuova connettività. Gli endpoint possono essere aggiornati anche durante il mese, se necessario per risolvere escalation di supporto, incidenti di sicurezza o altri requisiti operativi immediati. I dati mostrati in questa pagina vengono tutti generati dai servizi Web basati su REST. Se si utilizza uno script o un dispositivo di rete per accedere a questi dati, è consigliabile passare direttamente al [servizio Web.](microsoft-365-ip-web-service.md)

I dati degli endpoint seguenti elencano i requisiti per la connettività dal computer di un utente a Office 365. Non include le connessioni di rete da Microsoft a una rete del cliente, a volte denominate connessioni di rete ibride o in ingresso. Per ulteriori informazioni, vedere [Altri endpoint non inclusi nel servizio Web.](additional-office365-ip-addresses-and-urls.md) 

Gli endpoint sono raggruppati in quattro aree del servizio. Le prime tre aree del servizio possono essere selezionate in modo indipendente per la connessione. La quarta area del servizio è una dipendenza comune (denominata Microsoft 365 Common e Office) e deve avere sempre la connessione di rete.

Le colonne di dati visualizzate sono le seguenti:

- **ID**: il numero ID della riga, noto anche come set di endpoint. Questo ID è uguale a quello restituito dal servizio Web per il set di endpoint.

- **Categoria**: indica se il set di endpoint è categorizzato come "Optimize", "Allow" o "Default". Sono disponibili informazioni su queste categorie e linee guida per la loro gestione nell'articolo [https://aka.ms/pnc](https://aka.ms/pnc). Inoltre, in questa colonna sono elencati i set di endpoint necessari per la connessione di rete. Per i set di endpoint non necessari per la connessione di rete, in questo campo sono fornite delle note che indicano quale funzionalità non sarebbe disponibile se il set di endpoint fosse bloccato. Se si esclude un'intera area del servizio, i set di endpoint elencati come necessari non richiedono la connessione.

- **ER:** sì **se** il set di endpoint è supportato su Azure ExpressRoute con prefissi di route di Office 365. La community BGP che include i prefissi di route mostrati è allineata all'area di servizio elencata. Quando ER è **No,** significa che ExpressRoute non è supportato per questo set di endpoint. Non è tuttavia consigliabile presumere che non siano annunciate route per un set di endpoint in cui il valore ER è **No.** Se si prevede di usare Azure AD Connect, leggere la sezione [considerazioni](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) speciali per assicurarsi di disporre della configurazione di Azure AD Connect appropriata.

- **Indirizzi**: sono elencati i nomi di dominio completo (FQDN) o con caratteri jolly e gli intervalli di indirizzi IP per il set di endpoint. Tenere presente che un intervallo di indirizzi IP è in formato CIDR e potrebbe includere più indirizzi IP nella rete specificata.
 
- **Porte**: sono elencate le porte TCP o UDP combinate con gli indirizzi per formare l'endpoint di rete. Si potrebbero notare dei duplicati negli intervalli di indirizzi IP in cui sono presenti diverse porte.
 
[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
Note per questa tabella:

- Il Centro sicurezza e conformità (SCC) fornisce supporto per Azure ExpressRoute per Office 365. Lo stesso vale per molte funzionalità esposte tramite SCC, ad esempio Reporting, Auditing, Advanced eDiscovery, Unified DLP e Data Governance. Due funzionalità specifiche, l'importazione PST e l'esportazione di eDiscovery, attualmente non supportano Azure ExpressRoute con solo filtri di route di Office 365 a causa della dipendenza dall'archiviazione BLOB di Azure. Per usare queste funzionalità, è necessaria una connettività separata all'archiviazione BLOB di Azure usando tutte le opzioni di connettività di Azure supportate, che includono la connettività Internet o Azure ExpressRoute con filtri di route pubblici di Azure. È necessario valutare la definizione di tale connettività per entrambe le funzionalità. Il team di Office 365 Information Protection è a conoscenza di questa limitazione e sta lavorando attivamente per supportare Azure ExpressRoute per Office 365 come limitato ai filtri di route di Office 365 per entrambe queste funzionalità.

- Esistono altri endpoint facoltativi per Microsoft 365 Apps for enterprise che non sono elencati e non sono necessari per gli utenti per avviare le applicazioni di Microsoft 365 Apps for enterprise e modificare i documenti. Gli endpoint facoltativi sono ospitati nei datacenter Microsoft e non elaborano, trasmettono o archiviano i dati dei clienti. È consigliabile che le connessioni utente a questi endpoint siano dirette al perimetro di uscita Internet predefinito.
