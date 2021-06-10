---
title: URL e intervalli di indirizzi IP per Office 365 gestito da 21Vianet
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/29/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- GMA150
- GPA150
- GEA150
ms.assetid: 5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
description: In questo articolo vengono elencati gli URL e gli intervalli di indirizzi IP Office 365 se gestiti da 21Vianet in Cina.
hideEdit: true
ms.openlocfilehash: ed9b6fdbef1ca121ccf53b635768ebdaab89763a
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418050"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a>URL e intervalli di indirizzi IP per Office 365 gestito da 21Vianet

 *Si applica a: Amministrazione di Office 365 gestito da 21Vianet - Small Business, Amministrazione di Office 365 gestito da 21Vianet*

**Riepilogo**: i seguenti endpoint (FQDN, porte, URL, prefissi IPv4 e IPv6) si applicano a Office 365 gestito da 21Vianet e sono progettati per offrire servizi di produttività alle organizzazioni che usano solo questi piani.
  
 **Endpoint di Office 365:** [Worldwide (compreso GCC)](urls-and-ip-address-ranges.md)  | *Office 365 gestito da 21Vianet* | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Last updated:** 29/03/2021 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [subscription](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Download:** tutte le destinazioni obbligatorie e facoltative in un unico elenco in [formato JSON](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> |

Iniziare con [Gestione degli endpoint di Office 365](managing-office-365-endpoints.md) per conoscere i nostri consigli sulla gestione della connessione di rete con questi dati. I dati degli endpoint vengono aggiornati in base alle esigenze all'inizio di ogni mese con i nuovi URL e indirizzi IP pubblicati 30 giorni prima di essere attivi. In questo modo, i clienti che non hanno ancora automatizzato gli aggiornamenti possono completare le loro procedure prima che sia necessaria una nuova connessione. Inoltre, gli endpoint potrebbero essere aggiornati anche durante il mese qualora fosse necessario gestire problemi di supporto, problemi di sicurezza o altri requisiti operativi immediati. I dati mostrati più avanti in questa pagina sono tutti generati dai servizi Web basati su REST. Se si utilizza uno script o un dispositivo di rete per accedere a questi dati, passare direttamente al [servizio Web](microsoft-365-ip-web-service.md).

I dati degli endpoint riportati di seguito elencano i requisiti di connessione del computer di un utente a Office 365. Non sono incluse le connessioni di rete da Microsoft a una rete cliente, a volte chiamate connessioni di rete ibride o in ingresso.

Gli endpoint sono raggruppati in quattro aree del servizio. Le prime tre aree del servizio possono essere selezionate in modo indipendente per la connessione. La quarta area del servizio è una dipendenza comune (denominata Microsoft 365 Common e Office) e deve avere sempre la connessione di rete.

Le colonne di dati visualizzate sono le seguenti:

- **ID**: il numero ID della riga, noto anche come set di endpoint. Questo ID è uguale a quello restituito dal servizio Web per il set di endpoint.

- **Categoria**: indica se il set di endpoint è categorizzato come "Optimize", "Allow" o "Default". Sono disponibili informazioni su queste categorie e linee guida per la loro gestione nell'articolo [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). Inoltre, in questa colonna sono elencati i set di endpoint necessari per la connessione di rete. Per i set di endpoint non necessari per la connessione di rete, in questo campo sono fornite delle note che indicano quale funzionalità non sarebbe disponibile se il set di endpoint fosse bloccato. Se si esclude un'intera area del servizio, i set di endpoint elencati come necessari non richiedono la connessione.

- **ER**: presenta **Sì** se il set di endpoint è supportato su Azure ExpressRoute con i prefissi di route Office 365. La community BGP che include i prefissi di route mostrati si allinea con l'area del servizio elencata. Se ER presenta **No**, significa che ExpressRoute non è supportata per il set di endpoint. Tuttavia, non è detto che non vengano annunciate route per un set di endpoint in cui ER presenta **No**.

- **Indirizzi**: sono elencati i nomi di dominio completo (FQDN) o con caratteri jolly e gli intervalli di indirizzi IP per il set di endpoint. Tenere presente che un intervallo di indirizzi IP è in formato CIDR e potrebbe includere più indirizzi IP nella rete specificata.
 
- **Porte**: sono elencate le porte TCP o UDP combinate con gli indirizzi per formare l'endpoint di rete. Si potrebbero notare dei duplicati negli intervalli di indirizzi IP in cui sono presenti diverse porte.

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]