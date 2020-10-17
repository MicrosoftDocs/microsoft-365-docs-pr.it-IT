---
title: URL e intervalli di indirizzi IP di Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/29/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Riepilogo: Office 365 richiede la connessione a Internet. Gli endpoint riportati di seguito dovrebbero essere raggiungibili per i clienti che usano i piani di Office 365, compreso Government Community Cloud (GCC).'
hideEdit: true
ms.openlocfilehash: d9b0befaa7142729911ba46d0a3492bec9532535
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487613"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Intervalli di indirizzi IP e URL di Office 365

Office 365 richiede la connessione a Internet. Gli endpoint riportati di seguito dovrebbero essere raggiungibili per i clienti che usano i piani di Office 365, compreso Government Community Cloud (GCC).
  
*Office 365 internazionale (+GCC)* | [Office 365 gestito da 21Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |

||||
|:-----|:-----|:-----|
|**Ultimo aggiornamento:** 29/09/2020 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abbonamento al Log delle modifiche](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Download:** tutte le destinazioni obbligatorie e facoltative in un unico elenco in [formato JSON](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> | **Uso:** i nostri [file PAC ](managing-office-365-endpoints.md#pacfiles) proxy <br/> |

 Iniziare con [Gestione degli endpoint di Office 365](managing-office-365-endpoints.md) per conoscere i nostri consigli sulla gestione della connessione di rete con questi dati. I dati degli endpoint vengono aggiornati all'inizio di ogni mese con i nuovi URL e indirizzi IP pubblicati 30 giorni prima di essere attivi. In questo modo, i clienti che non hanno ancora automatizzato gli aggiornamenti possono completare le loro procedure prima che sia necessaria una nuova connessione. Inoltre, gli endpoint potrebbero essere aggiornati anche durante il mese qualora fosse necessario gestire problemi di supporto, problemi di sicurezza o altri requisiti operativi immediati. I dati mostrati più avanti in questa pagina sono tutti generati dai servizi Web basati su REST. Se si utilizza uno script o un dispositivo di rete per accedere a questi dati, passare direttamente al [servizio Web](microsoft-365-ip-web-service.md).

I dati endpoint riportati di seguito elencano i requisiti di connettività dal computer dell'utente a Office 365. Ma non includono le connessioni di rete da Microsoft a una rete del cliente, dette ibridi o connessioni di rete in ingresso. Vedere [Altri endpoint](additional-office365-ip-addresses-and-urls.md) per ulteriori informazioni.

Gli endpoint sono raggruppati in quattro aree del servizio. Le prime tre aree del servizio possono essere selezionate in modo indipendente per la connessione. La quarta area del servizio è una dipendenza comune (denominata Microsoft 365 Common e Office) e deve avere sempre la connessione di rete.

Le colonne di dati visualizzate sono le seguenti:

- **ID**: il numero ID della riga, noto anche come set di endpoint. Questo ID è uguale a quello restituito dal servizio Web per il set di endpoint.

- **Categoria**: indica se il set di endpoint è categorizzato come "Optimize", "Allow" o "Default". Sono disponibili informazioni su queste categorie e linee guida per la loro gestione nell'articolo [Nuove categorie di endpoint di Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). Inoltre, in questa colonna sono elencati i set di endpoint necessari per la connessione di rete. Per i set di endpoint non necessari per la connessione di rete, in questo campo sono fornite delle note che indicano quale funzionalità non sarebbe disponibile se il set di endpoint fosse bloccato. Se si esclude un'intera area del servizio, i set di endpoint elencati come necessari non richiedono la connessione.

- **ER**: presenta **Sì** se il set di endpoint è supportato su Azure ExpressRoute con i prefissi di route Office 365. La community BGP che include i prefissi di route mostrati si allinea con l'area del servizio elencata. Se ER presenta **No**, significa che ExpressRoute non è supportata per il set di endpoint. Tuttavia, non è detto che non vengano annunciate route per un set di endpoint in cui ER presenta **No**.

- **Indirizzi**: sono elencati i nomi di dominio completo (FQDN) o con caratteri jolly e gli intervalli di indirizzi IP per il set di endpoint. Tenere presente che un intervallo di indirizzi IP è in formato CIDR e potrebbe includere più indirizzi IP nella rete specificata.
 
- **Porte**: sono elencate le porte TCP o UDP combinate con gli indirizzi per formare l'endpoint di rete. Si potrebbero notare dei duplicati negli intervalli di indirizzi IP in cui sono presenti diverse porte.

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
>Per suggerimenti sugli URL e indirizzi IP di Yammer, vedere [Questo post di blog](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592).
>

## <a name="related-topics"></a>Argomenti correlati

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)
  
[Risoluzione dei problemi di connettività di Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d.aspx)

[CA radice e il bundle CA intermedio nel sistema di applicazioni di terze parti](../compliance/encryption-office-365-certificate-chains.md)
  
[Connettività client](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Reti per la distribuzione di contenuti](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Intervalli IP del data center di Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Spazio IP pubblico di Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)
