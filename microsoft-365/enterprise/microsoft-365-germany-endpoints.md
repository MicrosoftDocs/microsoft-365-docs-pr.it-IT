---
title: Office 365 endpoint per la Germania
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/01/2020
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
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 8a113a50-0071-4155-bb8e-eba5a8dbd4c8
description: In questo articolo sono disponibili endpoint raggiungibili per i clienti che usano Office 365 in Germania.
hideEdit: true
ms.openlocfilehash: 27d7b3c895cb3a8cae148262ce3962f03fb417aa
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925821"
---
# <a name="office-365-germany-endpoints"></a>Endpoint di Office 365 Germany

 *Si applica a: Amministrazione di Office 365*

Office 365 richiede connettività a Internet. Gli endpoint riportati di seguito devono essere raggiungibili solo per i clienti **che Office 365 solo i piani germania.**

> [!NOTE]
> Per i clienti, che sono in fase di transizione alla nuova area Microsoft 365 datacenter in Germania, gli endpoint cambieranno.
> Per ulteriori informazioni, fare riferimento alla migrazione da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree [data center tedesche.](ms-cloud-germany-transition.md)
  
 **Endpoint di Office 365:** [Worldwide (compreso GCC)](urls-and-ip-address-ranges.md)  | [Office 365 gestito da 21Vianet](urls-and-ip-address-ranges-21vianet.md)  | *Office 365 Germany* | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
**Last updated:** 12/01/2020 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [subscription](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)

**Download:** tutte le destinazioni necessarie e facoltative in un unico elenco [JSON formattato](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).

Iniziare con [Gestione degli endpoint di Office 365](managing-office-365-endpoints.md) per i suggerimenti per la gestione della connettività di rete tramite questi dati. I dati degli endpoint vengono aggiornati in base alle esigenze all'inizio del mese con nuovi indirizzi IP e URL pubblicati 30 giorni prima di essere attivati. In questo modo i clienti che non dispongono ancora di aggiornamenti automatici possono completare i processi prima che sia necessaria una nuova connettività. Gli endpoint possono anche essere aggiornati durante il mese, se necessario, per affrontare richieste di supporto, eventi imprevisti di sicurezza o altri requisiti operativi immediati. È sempre possibile fare riferimento alla [sottoscrizione del log delle modifiche.](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)

I dati visualizzati in questa pagina sono tutti generati dai servizi Web basati su REST. Se si usa uno script o un dispositivo di rete per accedere ai dati, è necessario accedere direttamente al [servizio Web](microsoft-365-ip-web-service.md).

I dati degli endpoint riportati di seguito elencano i requisiti per la connettività dal computer di un utente a Office 365. Non include connessioni di rete da Microsoft a una rete cliente, a volte denominata connessioni di rete ibride o in ingresso.

Gli endpoint sono raggruppati in quattro aree del servizio. Le prime tre aree del servizio possono essere selezionate in modo indipendente per la connessione. La quarta area del servizio è una dipendenza comune (denominata Microsoft 365 Common e Office) e deve avere sempre la connessione di rete.

Le colonne di dati visualizzate sono le seguenti:

- **ID**: il numero ID della riga, noto anche come set di endpoint. Questo ID è uguale a quello restituito dal servizio Web per il set di endpoint.

- **Categoria**: indica se il set di endpoint è categorizzato come "Optimize", "Allow" o "Default". Sono disponibili informazioni su queste categorie e linee guida per la loro gestione nell'articolo [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). Inoltre, in questa colonna sono elencati i set di endpoint necessari per la connessione di rete. Per i set di endpoint non necessari per la connessione di rete, in questo campo sono fornite delle note che indicano quale funzionalità non sarebbe disponibile se il set di endpoint fosse bloccato. Se si esclude un'intera area del servizio, i set di endpoint elencati come necessari non richiedono la connessione.

- **ER**: presenta **Sì** se il set di endpoint è supportato su Azure ExpressRoute con i prefissi di route Office 365. La community BGP che include i prefissi di route mostrati si allinea con l'area del servizio elencata. Se ER presenta **No**, significa che ExpressRoute non è supportata per il set di endpoint. Tuttavia, non è detto che non vengano annunciate route per un set di endpoint in cui ER presenta **No**.

- **Indirizzi**: sono elencati i nomi di dominio completo (FQDN) o con caratteri jolly e gli intervalli di indirizzi IP per il set di endpoint. Tenere presente che un intervallo di indirizzi IP è in formato CIDR e potrebbe includere più indirizzi IP nella rete specificata.
 
- **Porte**: sono elencate le porte TCP o UDP combinate con gli indirizzi per formare l'endpoint di rete. Si potrebbero notare dei duplicati negli intervalli di indirizzi IP in cui sono presenti diverse porte.

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

