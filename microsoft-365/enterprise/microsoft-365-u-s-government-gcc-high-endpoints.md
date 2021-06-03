---
title: Office 365 U.S. Government GCC High endpoints
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 05/28/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid: MET150
ms.assetid: cbd2369c-fd96-464c-bf48-c99826b459ee
description: In questo articolo, troverai gli endpoint raggiungibili per i clienti che usano Office 365 piano High government GCC Stati Uniti.
hideEdit: true
ms.openlocfilehash: da721d7d0a8965c4dea9bc812df755f19e69ea55
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730163"
---
# <a name="office-365-us-government-gcc-high-endpoints"></a>Office 365 U.S. Government GCC High endpoints

 *Si applica a: Amministrazione di Office 365*

Office 365 richiede connettività a Internet. Gli endpoint riportati di seguito devono essere raggiungibili solo per i clienti che usano Office 365 piano High per il governo GCC Stati Uniti.
  
 **Endpoint di Office 365:** [Worldwide (compreso GCC)](urls-and-ip-address-ranges.md) | [Office 365 gestito da 21Vianet](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 Germany](microsoft-365-germany-endpoints.md)  | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) | *Office 365 U.S. Government GCC High* |
  
|||
|:-----|:-----|
|**Last updated:** 28/05/2021 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [subscription](https://endpoints.office.com/version/USGOVGCCHigh?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Download:** elenco completo in [formato JSON](https://endpoints.office.com/endpoints/USGOVGCCHigh?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Iniziare con [Gestione degli endpoint di Office 365](managing-office-365-endpoints.md) per i suggerimenti per la gestione della connettività di rete tramite questi dati. I dati degli endpoint vengono aggiornati in base alle esigenze all'inizio del mese con nuovi indirizzi IP e URL pubblicati 30 giorni prima di essere attivati. In questo modo i clienti che non dispongono ancora di aggiornamenti automatici possono completare i processi prima che sia necessaria una nuova connettività. Gli endpoint possono anche essere aggiornati durante il mese, se necessario, per affrontare richieste di supporto, eventi imprevisti di sicurezza o altri requisiti operativi immediati. I dati visualizzati in questa pagina sono tutti generati dai servizi Web basati su REST. Se si usa uno script o un dispositivo di rete per accedere ai dati, è necessario accedere direttamente al [servizio Web](microsoft-365-ip-web-service.md).

I dati degli endpoint riportati di seguito elencano i requisiti di connessione del computer di un utente a Office 365. Non sono incluse le connessioni di rete da Microsoft a una rete cliente, a volte chiamate connessioni di rete ibride o in ingresso.

Gli endpoint sono raggruppati in quattro aree del servizio. Le prime tre aree del servizio possono essere selezionate in modo indipendente per la connessione. La quarta area del servizio è una dipendenza comune (denominata Microsoft 365 Common e Office) e deve avere sempre la connessione di rete.

Le colonne di dati visualizzate sono le seguenti:

- **ID**: il numero ID della riga, noto anche come set di endpoint. Questo ID è uguale a quello restituito dal servizio Web per il set di endpoint.

- **Categoria**: indica se il set di endpoint è categorizzato come "Optimize", "Allow" o "Default". Sono disponibili informazioni su queste categorie e linee guida per la loro gestione nell'articolo [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). Inoltre, in questa colonna sono elencati i set di endpoint necessari per la connessione di rete. Per i set di endpoint non necessari per la connessione di rete, in questo campo sono fornite delle note che indicano quale funzionalità non sarebbe disponibile se il set di endpoint fosse bloccato. Se si esclude un'intera area del servizio, i set di endpoint elencati come necessari non richiedono la connessione.

- **ER:** questo è **Sì** se il set di endpoint è supportato su Azure ExpressRoute con Office 365 prefissi di route. La community BGP che include i prefissi di route mostrati è allineata all'area di servizio elencata. Quando ER è **No,** significa che ExpressRoute non è supportato per questo set di endpoint. Tuttavia, non è consigliabile presumere che non siano annunciate route per un set di endpoint in cui ER è **No**. Se si prevede di usare Azure AD [](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) Connessione, leggere la sezione considerazioni speciali per assicurarsi di avere la configurazione di Azure AD Connessione appropriata.

- **Indirizzi**: sono elencati i nomi di dominio completo (FQDN) o con caratteri jolly e gli intervalli di indirizzi IP per il set di endpoint. Tenere presente che un intervallo di indirizzi IP è in formato CIDR e potrebbe includere più indirizzi IP nella rete specificata.
 
- **Porte**: sono elencate le porte TCP o UDP combinate con gli indirizzi per formare l'endpoint di rete. Si potrebbero notare dei duplicati negli intervalli di indirizzi IP in cui sono presenti diverse porte.
 
[!INCLUDE [Office 365 U.S. Government GCC High endpoints](../includes/office-365-u.s.-government-gcc-high-endpoints.md)]

Note per questa tabella:

- Il Centro sicurezza e conformità (SCC) fornisce supporto per Azure ExpressRoute per Office 365. Lo stesso vale per molte funzionalità esposte tramite SCC, ad esempio Reporting, Auditing, Advanced eDiscovery, UNIFIED DLP e Data Governance. Due funzionalità specifiche, l'importazione PST e l'esportazione di eDiscovery, attualmente non supportano Azure ExpressRoute con solo filtri di route di Office 365 a causa della loro dipendenza dal blob di Azure Archiviazione. Per usare queste funzionalità, è necessaria una connettività separata al servizio BLOB di Azure Archiviazione usando tutte le opzioni di connettività di Azure supportate, che includono la connettività Internet o Azure ExpressRoute con i filtri di route pubblici di Azure. È necessario valutare la definizione di tale connettività per entrambe le funzionalità. Il team di Office 365 Information Protection è a conoscenza di questa limitazione e sta lavorando attivamente per supportare Azure ExpressRoute per Office 365 solo Office 365 filtri di route per entrambe queste funzionalità.

- Esistono altri endpoint facoltativi per Microsoft 365 Apps for enterprise che non sono elencati e non sono necessari per consentire agli utenti di avviare Microsoft 365 Apps for enterprise applicazioni e modificare i documenti. Gli endpoint facoltativi sono ospitati nei datacenter Microsoft e non elaborano, trasmettono o archiviano i dati dei clienti. È consigliabile che le connessioni utente a questi endpoint siano indirizzate al perimetro di uscita Internet predefinito.