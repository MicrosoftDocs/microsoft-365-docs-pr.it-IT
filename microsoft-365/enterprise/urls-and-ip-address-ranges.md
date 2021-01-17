---
title: URL e intervalli di indirizzi IP di Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/04/2021
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
ms.openlocfilehash: 386c92d0856b3faa88fb8a05f8ddff58a81e3c4f
ms.sourcegitcommit: a92b150da1e11d4a204c556ab98a4776727dbc22
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "49883337"
---
# <a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="87fe5-104">Intervalli di indirizzi IP e URL di Office 365</span><span class="sxs-lookup"><span data-stu-id="87fe5-104">Office 365 URLs and IP address ranges</span></span>

<span data-ttu-id="87fe5-p102">Office 365 richiede la connessione a Internet. Gli endpoint riportati di seguito dovrebbero essere raggiungibili per i clienti che usano i piani di Office 365, compreso Government Community Cloud (GCC).</span><span class="sxs-lookup"><span data-stu-id="87fe5-p102">Office 365 requires connectivity to the Internet. The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).</span></span>
  
<span data-ttu-id="87fe5-107">*Office 365 internazionale (+GCC)* | [Office 365 gestito da 21Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span><span class="sxs-lookup"><span data-stu-id="87fe5-107">*Office 365 Worldwide (+GCC)* | [Office 365 operated by 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Germany](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="87fe5-108">**Ultimo aggiornamento:** 01/04/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abbonamento al Log delle modifiche](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="87fe5-108">**Last updated:** 01/04/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span> <br/> |<span data-ttu-id="87fe5-109">**Download:** tutte le destinazioni obbligatorie e facoltative in un unico elenco in [formato JSON](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="87fe5-109">**Download:** all required and optional destinations in one [JSON formatted](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) list.</span></span>  <br/> | <span data-ttu-id="87fe5-110">**Uso:** i nostri [file PAC](managing-office-365-endpoints.md#pacfiles) proxy</span><span class="sxs-lookup"><span data-stu-id="87fe5-110">**Use:** our proxy [PAC files](managing-office-365-endpoints.md#pacfiles)</span></span> <br/> |

 <span data-ttu-id="87fe5-p103">Iniziare con [Gestione degli endpoint di Office 365](managing-office-365-endpoints.md) per conoscere i nostri consigli sulla gestione della connessione di rete con questi dati. I dati degli endpoint vengono aggiornati all'inizio di ogni mese con i nuovi URL e indirizzi IP pubblicati 30 giorni prima di essere attivi. In questo modo, i clienti che non hanno ancora automatizzato gli aggiornamenti possono completare le loro procedure prima che sia necessaria una nuova connessione. Inoltre, gli endpoint potrebbero essere aggiornati anche durante il mese qualora fosse necessario gestire problemi di supporto, problemi di sicurezza o altri requisiti operativi immediati. I dati mostrati più avanti in questa pagina sono tutti generati dai servizi Web basati su REST. Se si utilizza uno script o un dispositivo di rete per accedere a questi dati, passare direttamente al [servizio Web](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="87fe5-p103">Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data. Endpoints data is updated at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active. This allows for customers who do not yet have automated updates to complete their processes before new connectivity is required. Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements. The data shown on this page below is all generated from the REST-based web services. If you are using a script or a network device to access this data, you should go to the [Web service](microsoft-365-ip-web-service.md) directly.</span></span>

<span data-ttu-id="87fe5-p104">I dati endpoint riportati di seguito elencano i requisiti di connettività dal computer dell'utente a Office 365. Ma non includono le connessioni di rete da Microsoft a una rete del cliente, dette ibridi o connessioni di rete in ingresso. Vedere [Altri endpoint](additional-office365-ip-addresses-and-urls.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="87fe5-p104">Endpoint data below lists requirements for connectivity from a user's machine to Office 365. It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections. See [Additional endpoints](additional-office365-ip-addresses-and-urls.md) for more information.</span></span>

<span data-ttu-id="87fe5-p105">Gli endpoint sono raggruppati in quattro aree del servizio. Le prime tre aree del servizio possono essere selezionate in modo indipendente per la connessione. La quarta area del servizio è una dipendenza comune (denominata Microsoft 365 Common e Office) e deve avere sempre la connessione di rete.</span><span class="sxs-lookup"><span data-stu-id="87fe5-p105">The endpoints are grouped into four service areas. The first three service areas can be independently selected for connectivity. The fourth service area is a common dependency (called Microsoft 365 Common and Office) and must always have network connectivity.</span></span>

<span data-ttu-id="87fe5-123">Le colonne di dati visualizzate sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="87fe5-123">Data columns shown are:</span></span>

- <span data-ttu-id="87fe5-p106">**ID**: il numero ID della riga, noto anche come set di endpoint. Questo ID è uguale a quello restituito dal servizio Web per il set di endpoint.</span><span class="sxs-lookup"><span data-stu-id="87fe5-p106">**ID**: The ID number of the row, also known as an endpoint set. This ID is the same as is returned by the web service for the endpoint set.</span></span>

- <span data-ttu-id="87fe5-p107">**Categoria**: indica se il set di endpoint è categorizzato come "Optimize", "Allow" o "Default". Sono disponibili informazioni su queste categorie e linee guida per la loro gestione nell'articolo [Nuove categorie di endpoint di Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). Inoltre, in questa colonna sono elencati i set di endpoint necessari per la connessione di rete. Per i set di endpoint non necessari per la connessione di rete, in questo campo sono fornite delle note che indicano quale funzionalità non sarebbe disponibile se il set di endpoint fosse bloccato. Se si esclude un'intera area del servizio, i set di endpoint elencati come necessari non richiedono la connessione.</span><span class="sxs-lookup"><span data-stu-id="87fe5-p107">**Category**: Shows whether the endpoint set is categorized as "Optimize", "Allow", or "Default". You can read about these categories and guidance for management of them at [New Office 365 endpoint categories](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). This column also lists which endpoint sets are required to have network connectivity. For endpoint sets which are not required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked. If you are excluding an entire service area, the endpoint sets listed as required do not require connectivity.</span></span>

- <span data-ttu-id="87fe5-p108">**ER**: presenta **Sì** se il set di endpoint è supportato su Azure ExpressRoute con i prefissi di route Office 365. La community BGP che include i prefissi di route mostrati si allinea con l'area del servizio elencata. Se ER presenta **No**, significa che ExpressRoute non è supportata per il set di endpoint. Tuttavia, non è detto che non vengano annunciate route per un set di endpoint in cui ER presenta **No**.</span><span class="sxs-lookup"><span data-stu-id="87fe5-p108">**ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes. The BGP community that includes the route prefixes shown aligns with the service area listed. When ER is **No**, this means that ExpressRoute is not supported for this endpoint set. However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**.</span></span>

- <span data-ttu-id="87fe5-p109">**Indirizzi**: sono elencati i nomi di dominio completo (FQDN) o con caratteri jolly e gli intervalli di indirizzi IP per il set di endpoint. Tenere presente che un intervallo di indirizzi IP è in formato CIDR e potrebbe includere più indirizzi IP nella rete specificata.</span><span class="sxs-lookup"><span data-stu-id="87fe5-p109">**Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set. Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.</span></span>
 
- <span data-ttu-id="87fe5-p110">**Porte**: sono elencate le porte TCP o UDP combinate con gli indirizzi per formare l'endpoint di rete. Si potrebbero notare dei duplicati negli intervalli di indirizzi IP in cui sono presenti diverse porte.</span><span class="sxs-lookup"><span data-stu-id="87fe5-p110">**Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint. You may notice some duplication in IP Address ranges where there are different ports listed.</span></span>

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
><span data-ttu-id="87fe5-139">Per consigli sugli indirizzi IP e URL di Yammer, vedere il post del blog di Yammer [L'uso di indirizzi IP statici per Yammer non è consigliato](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592).</span><span class="sxs-lookup"><span data-stu-id="87fe5-139">For recommendations on Yammer IP addresses and URLs, see [Using hard-coded IP addresses for Yammer is not recommended](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) on the Yammer blog.</span></span>
>

## <a name="related-topics"></a><span data-ttu-id="87fe5-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="87fe5-140">Related Topics</span></span>

[<span data-ttu-id="87fe5-141">Gestione degli endpoint di Office 365</span><span class="sxs-lookup"><span data-stu-id="87fe5-141">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="87fe5-142">Endpoint generali di Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="87fe5-142">General Microsoft Stream endpoints</span></span>](https://docs.microsoft.com/stream/network-overview#general-microsoft-stream-endpoints)
  
[<span data-ttu-id="87fe5-143">Monitorare la connettività di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="87fe5-143">Monitor Microsoft 365 connectivity</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/monitor-connectivity)

[<span data-ttu-id="87fe5-144">CA radice e il bundle CA intermedio nel sistema di applicazioni di terze parti</span><span class="sxs-lookup"><span data-stu-id="87fe5-144">Root CA and the Intermediate CA bundle on the third-party application system</span></span>](../compliance/encryption-office-365-certificate-chains.md)
  
[<span data-ttu-id="87fe5-145">Connettività client</span><span class="sxs-lookup"><span data-stu-id="87fe5-145">Client connectivity</span></span>](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[<span data-ttu-id="87fe5-146">Reti per la distribuzione di contenuti</span><span class="sxs-lookup"><span data-stu-id="87fe5-146">Content delivery networks</span></span>](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[<span data-ttu-id="87fe5-147">Intervalli IP di Microsoft Azure e tag di servizio - Cloud pubblico</span><span class="sxs-lookup"><span data-stu-id="87fe5-147">Microsoft Azure IP Ranges and Service Tags – Public Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=56519)

[<span data-ttu-id="87fe5-148">Intervalli IP di Microsoft Azure e tag di servizio - Cloud US Government</span><span class="sxs-lookup"><span data-stu-id="87fe5-148">Microsoft Azure IP Ranges and Service Tags – US Government Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57063)

[<span data-ttu-id="87fe5-149">Intervalli IP di Microsoft Azure e tag di servizio - Cloud Germania</span><span class="sxs-lookup"><span data-stu-id="87fe5-149">Microsoft Azure IP Ranges and Service Tags – Germany Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57064)

[<span data-ttu-id="87fe5-150">Intervalli IP di Microsoft Azure e tag di servizio - Cloud Cina</span><span class="sxs-lookup"><span data-stu-id="87fe5-150">Microsoft Azure IP Ranges and Service Tags – China Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57062)
  
[<span data-ttu-id="87fe5-151">Spazio IP pubblico di Microsoft</span><span class="sxs-lookup"><span data-stu-id="87fe5-151">Microsoft Public IP Space</span></span>](https://www.microsoft.com/download/details.aspx?id=53602)

[<span data-ttu-id="87fe5-152">Registro del nome del servizio e numero di porta del protocollo di trasporto</span><span class="sxs-lookup"><span data-stu-id="87fe5-152">Service Name and Transport Protocol Port Number Registry</span></span>](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
