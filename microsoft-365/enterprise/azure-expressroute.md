---
title: Azure ExpressRoute per Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: Informazioni su come utilizzare Azure ExpressRoute con Office 365 e pianificare il progetto di implementazione della rete se si esegue la distribuzione con esso.
ms.openlocfilehash: 3691161767aba784039cbf317a51429c9ee6444c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690942"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute per Office 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Informazioni su come utilizzare Azure ExpressRoute con Office 365 e su come pianificare il progetto di implementazione della rete che sarà necessario se si esegue la distribuzione di Azure ExpressRoute per l'utilizzo con Office 365. L'infrastruttura e i servizi di piattaforma in esecuzione in Azure spesso usufruiscono dell'architettura di rete e delle considerazioni relative alle prestazioni. In questi casi è consigliabile ExpressRoute per Azure. Il software come offerta di servizi come Office 365 e Dynamics 365 è stato creato per accedere in modo sicuro e affidabile tramite Internet. È possibile leggere le prestazioni e la sicurezza di Internet e quando è possibile considerare Azure ExpressRoute per Office 365 nell'articolo [valutare la connettività di rete di office 365](assessing-network-connectivity.md).

> [!NOTE]
> È necessaria l'autorizzazione Microsoft per l'utilizzo di ExpressRoute per Office 365. Microsoft esamina ogni richiesta del cliente e autorizza ExpressRoute per l'utilizzo di Office 365 quando un requisito normativo del cliente delega la connettività diretta. Se si dispone di tali requisiti, fornire l'Estratto di testo e il collegamento Web al regolamento che si intende interpretare per indicare che la connettività diretta è necessaria nel [modulo di richiesta di ExpressRoute per Office 365](https://aka.ms/O365ERReview) per avviare una revisione Microsoft. Gli abbonamenti non autorizzati che tentano di creare filtri di route per Office 365 riceveranno un [messaggio di errore](https://support.microsoft.com/kb/3181709).

È ora possibile aggiungere una connessione di rete diretta a Office 365 per il traffico di rete di Office 365 selezionato. Azure ExpressRoute offre una connessione diretta, prestazioni prevedibili e viene fornito con un SLA di uptime del 99,95% per i componenti di rete Microsoft. È comunque necessario disporre di una connessione Internet per i servizi che non sono supportati su ExpressRoute di Azure.

## <a name="planning-azure-expressroute-for-office-365"></a>Planning Azure ExpressRoute per Office 365

Oltre alla connettività Internet, è possibile scegliere di instradare un sottoinsieme del traffico di rete di Office 365 tramite una connessione diretta che offre la prevedibilità e il contratto di servizio di uptime del 99,95% per i componenti di rete Microsoft. Azure ExpressRoute offre una connessione di rete dedicata a Office 365 e ad altri servizi cloud Microsoft.

Indipendentemente dal fatto che si disponga di una WAN MPLS esistente, è possibile aggiungere ExpressRoute all'architettura di rete in uno dei tre modi seguenti. tramite un provider di coesistenza di Exchange cloud supportato, un provider di connessione Ethernet Point-to-Point oppure tramite un provider di connessione MPLS. Vedere quali [provider sono disponibili nella propria area geografica](https://azure.microsoft.com/documentation/articles/expressroute-locations/). La connessione ExpressRoute diretta consentirà la connettività alle applicazioni descritte in [quali servizi di Office 365 sono inclusi?](azure-expressroute.md#BKMK_WhatDoIGet) di seguito. Il traffico di rete per tutte le altre applicazioni e servizi continuerà a essere attraversato da Internet.

Si consideri il seguente diagramma di rete ad alto livello, che illustra un tipico client di Office 365 che si connette ai datacenter di Microsoft tramite Internet per accedere a tutte le applicazioni Microsoft come Office 365, Windows Update e TechNet. I clienti utilizzano un percorso di rete simile, indipendentemente dal fatto che si stiano connettendo da una rete locale o da una connessione Internet indipendente.

![Connettività di rete di Office 365](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

A questo punto, vedere il diagramma aggiornato che descrive un cliente di Office 365 che usa sia Internet che ExpressRoute per connettersi a Office 365. Si noti che alcune connessioni, ad esempio i nodi DNS pubblico e di rete per la distribuzione del contenuto, richiedono ancora la connessione Internet pubblica. Si noti inoltre che gli utenti del cliente che non si trovano nell'edificio collegato di ExpressRoute si connettono su Internet.

![Connettività di Office 365 con ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

Vuoi ancora altre informazioni? Informazioni su come [gestire il traffico di rete con Azure ExpressRoute per office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) e informazioni su come [configurare Azure ExpressRoute per Office 365](https://azure.microsoft.com/documentation/articles/expressroute-faqs/). Sono state inoltre registrate una serie di [ExpressRoute di 10 parti di Azure per Office 365 per la formazione](https://channel9.msdn.com/series/aer) su Channel 9 per spiegare i concetti in modo più approfondito.

## <a name="what-office-365-services-are-included"></a>Quali servizi sono inclusi in Office 365?
<a name="BKMK_WhatDoIGet"> </a>

Nella tabella seguente sono elencati i servizi di Office 365 supportati su ExpressRoute. Leggere l' [articolo Office 365 Endpoints](https://aka.ms/o365endpoints) per sapere quali richieste di rete per queste applicazioni richiedono la connettività Internet.

|**Applicazioni incluse**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Approfondire<sup>1</sup> <br/> |
|Skype for business online<sup>1</sup> <br/> Microsoft teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive for business<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|Portale e condiviso<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> ognuna di queste applicazioni ha requisiti di connettività Internet non supportati su ExpressRoute, vedere l' [articolo Office 365 Endpoints](https://aka.ms/o365endpoints) per ulteriori informazioni.

I servizi che non sono inclusi in ExpressRoute per Office 365 sono Microsoft 365 Apps for Enterprise client downloads, on-premises Identity provider sign-in e Office 365 (operated by 21 Viant) Service in Cina.

## <a name="implementing-expressroute-for-office-365"></a>Implementazione di ExpressRoute per Office 365

L'implementazione di ExpressRoute richiede la partecipazione dei proprietari di reti e applicazioni e richiede una pianificazione attenta per determinare la nuova [architettura di routing di rete](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), i requisiti di larghezza di banda, in cui verrà implementata la sicurezza, la disponibilità elevata e così via. Per implementare ExpressRoute, è necessario eseguire le operazioni seguenti:

1. Comprendere appieno la necessità di ExpressRoute soddisfa la pianificazione della connettività di Office 365. Comprendere quali applicazioni utilizzeranno Internet o ExpressRoute e pianificare completamente la capacità di rete, la sicurezza e la disponibilità elevata nel contesto dell'utilizzo di Internet e di ExpressRoute per il traffico di Office 365.

2. Determinare le posizioni di uscita e peering sia per Internet che per il traffico ExpressRoute<sup>1</sup>.

3. Determinare la capacità necessaria su Internet e sulle connessioni di ExpressRoute.

4. Disporre di un piano per l'implementazione della sicurezza e di altri controlli perimetrali standard<sup>1</sup>.

5. Disporre di un account Microsoft Azure valido per la sottoscrizione a ExpressRoute.

6. Selezionare un modello di connettività e un [provider approvato](https://azure.microsoft.com/documentation/articles/expressroute-locations/). Tenere presente che i clienti possono selezionare più modelli di connettività o partner e il partner non deve necessariamente corrispondere al provider di rete esistente.

7. Convalidare la distribuzione prima di indirizzare il traffico a ExpressRoute.

8. Facoltativamente, [implementare QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) e valutare l'espansione regionale.

<sup>1</sup> considerazioni importanti sulle prestazioni. Le decisioni qui possono influire in modo significativo sulla latenza, che è un fattore critico per applicazioni come Skype for business.

Per ulteriori riferimenti, utilizzare la [Guida di routing](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) oltre alla [documentazione di ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/).

Per acquistare ExpressRoute per Office 365, è necessario collaborare con uno o più [provider approvati](https://azure.microsoft.com/documentation/articles/expressroute-locations/) per effettuare il provisioning dei circuiti numerici e di dimensioni desiderate con un abbonamento a ExpressRoute Premium. Non sono disponibili licenze aggiuntive per l'acquisto da Office 365.

Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)

Pronto a iscriversi per [ExpressRoute per Office 365](https://aka.ms/ert)?

## <a name="related-topics"></a>Argomenti correlati

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)

[Gestione di ExpressRoute per la connettività di Office 365](managing-expressroute-for-connectivity.md)

[Routing con ExpressRoute per Office 365](routing-with-expressroute.md)

[Pianificazione della rete con ExpressRoute per Office 365](network-planning-with-expressroute.md)

[Implementazione di ExpressRoute per Office 365](implementing-expressroute.md)

[Utilizzo delle community BGP in ExpressRoute per gli scenari di Office 365](bgp-communities-in-expressroute.md)

[Qualità multimediale e prestazioni della connettività di rete in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)

[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)

[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)

[Ottimizzazione delle prestazioni e della rete di Office 365](network-planning-and-performance.md)

## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
