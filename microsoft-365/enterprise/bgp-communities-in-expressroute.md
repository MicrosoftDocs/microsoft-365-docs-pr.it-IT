---
title: Uso delle community BGP in ExpressRoute per scenari di Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: Informazioni su come usare le community BGP in Azure ExpressRoute per gestire il numero di prefissi IP e la larghezza di banda necessaria per gli scenari di Office 365.
ms.openlocfilehash: 9cb6980c1d8cc120f99cac087602856aeacf1adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905213"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Uso delle community BGP in ExpressRoute per scenari di Office 365

La connessione a Office 365 tramite Azure ExpressRoute si basa su annunci BGP di subnet IP specifiche che rappresentano le reti in cui vengono distribuiti gli endpoint di Office 365. A causa della natura globale di Office 365 e del numero di servizi che costituiscono Office 365, i clienti spesso hanno la necessità di gestire gli annunci che accettano sulla propria rete. Riduzione del numero di subnet IP; Per allinearsi alla terminologia relativa alla gestione della rete BGP, i clienti sono indicati come prefissi IP per tutto il resto di questo articolo:
  
- Gestire il numero di prefissi **IP** annunciati accettati- I clienti che dispongono di un'infrastruttura di rete interna o di un gestore di rete che supporta solo un numero limitato di prefissi IP e clienti che dispongono di un gestore di rete che addebita l'accettazione di prefissi superiori a un numero limitato vorranno valutare il numero totale di prefissi già annunciati alla propria rete e selezionare le applicazioni di Office 365 più adatte per ExpressRoute.

- Gestire la quantità di larghezza di banda necessaria nel **circuito Di Azure ExpressRoute:** i clienti potrebbero voler controllare la busta di larghezza di banda dei servizi di Office 365 sul percorso ExpressRoute rispetto al percorso Internet. In questo modo i clienti possono prenotare la larghezza di banda ExpressRoute per applicazioni specifiche come Skype for Business e instradare le applicazioni di Office 365 rimanenti sul percorso Internet.

Per aiutare i clienti a raggiungere questi obiettivi, i prefissi IP di Office 365 annunciati su ExpressRoute sono contrassegnati con valori della community BGP specifici del servizio, come illustrato nell'esempio seguente.
  
> [!NOTE]
> È consigliabile prevedere che il traffico di rete associato ad altre applicazioni sia incluso nel valore della community. Si tratta di un comportamento previsto per un'offerta globale software as a Service con servizi condivisi e datacenter. Questo è stato ridotto al minimo, se possibile, con i due obiettivi precedenti, gestendo il numero di prefissi e/o la larghezza di banda in mente.

|**Servizio**|**Valore della community BGP**|**Note**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Include i servizi Exchange ed EOP\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype for Business\*  <br/> |12076:5030  <br/> |Skype for Business online & servizi di Microsoft Teams  <br/> |
|Altri servizi di Office 365\*  <br/> |12076:5100  <br/> |Include Azure Active Directory (scenari di autenticazione e sincronizzazione della directory) e servizi portale di Office 365  <br/> |
|\*L'ambito degli scenari di servizio inclusi in ExpressRoute è documentato [nell'articolo Endpoint di Office 365.](./urls-and-ip-address-ranges.md)  <br/> \*\*In futuro potrebbero essere aggiunti altri servizi e valori della community BGP. [Vedi l'elenco corrente delle community BGP.](/azure/expressroute/expressroute-routing)  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>Quali sono gli scenari più comuni per l'utilizzo delle community BGP?

I clienti possono usare le community BGP per regolare gruppi di prefissi IP accettati dalla rete tramite Azure ExpressRoute, influenzando così il numero totale di prefissi IP e la busta di larghezza di banda prevista di determinati servizi di Office 365. È importante comprendere che tutto Office 365 richiederà traffico associato a Internet indipendentemente dall'uso di Azure ExpressRoute o community BGP. I tre scenari seguenti sono gli utilizzi più comuni di questa funzionalità.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Scenario 1: ridurre al minimo il numero di prefissi IP di Office 365

Contoso Corporation è una società di 50.000 persone che attualmente utilizza Office 365 per Exchange Online e SharePoint Online. Nell'esame dei requisiti expressRoute Contoso determina che i dispositivi di rete in molte località regionali non sono in grado di gestire le dimensioni delle tabelle di routing superiori a 100 voci di route aggiuntive. Contoso ha esaminato il numero totale di prefissi IP annunciati da ExpressRoute per il set completo di servizi di Office 365 e ha concluso che supera i 100. Per rimanere al di sotto delle 100 voci di route aggiuntive, Contoso ha come ambito l'uso di ExpressRoute per Office 365 solo per il valore della community BGP di SharePoint Online, 12076:5020, ricevuto tramite peering Microsoft ExpressRoute.

|**Tag community BGP usato**|**Funzionalità instradabile su Azure ExpressRoute**|**Route Internet necessarie**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint Online &amp; OneDrive for Business  <br/> | Richieste DNS, CRL, &amp; CDN  <br/>  Tutti gli altri servizi di Office 365 non sono supportati in modo specifico su Azure ExpressRoute  <br/>  Tutti gli altri servizi cloud Microsoft  <br/>  Portale di Office 365, autenticazione di Office 365, &amp; Office in un browser  <br/>  Exchange Online, Exchange Online Protection e Skype for Business online  <br/> |

> [!NOTE]
> Per ottenere un numero di prefissi inferiore per ogni servizio, verrà mantenuta una quantità minima di sovrapposizione tra i servizi. Si tratta di un comportamento previsto.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Scenario 2: ambito di ExpressRoute e utilizzo della larghezza di banda interna per alcuni servizi di Office 365

Fabrikam Inc, un'azienda multi-nazionale di grandi dimensioni con una rete eterogenea distribuita, è un sottoscrittore di molti servizi di Office 365 tra cui; Exchange Online, SharePoint Online e Skype for Business online. L'infrastruttura di routing interna di Fabrikam è in grado di gestire migliaia di prefissi IP nelle tabelle di routing. Tuttavia, Fabrikam desidera solo effettuare il provisioning di ExpressRoute e della larghezza di banda interna per le applicazioni di Office 365 più sensibili alle prestazioni di rete e utilizzare la larghezza di banda Internet esistente per tutte le altre applicazioni di Office 365.
  
Per questo motivo, Fabrikam ha come ambito la larghezza di banda di Azure ExpressRoute solo al valore della community BGP di Skype for Business online, 12076:5030, ricevuto tramite peering Microsoft ExpressRoute. Il traffico di rete rimanente associato a Office 365 continua a usare i punti di uscita internet.

|**Tag community BGP usato**|**Funzionalità instradabile su Azure ExpressRoute**|**Route Internet necessarie**|
|:-----|:-----|:-----|
|Skype for Business  <br/> (12076:5030)  <br/> |Segnalazione SIP Skype, download, voce, video e condivisione desktop  <br/> | Richieste DNS, CRL, &amp; CDN  <br/>  Tutti gli altri servizi di Office 365 non sono supportati in modo specifico su Azure ExpressRoute  <br/>  Tutti gli altri servizi cloud Microsoft  <br/>  Portale di Office 365, autenticazione di Office 365, &amp; Office in un browser  <br/>  Telemetria di Skype for Business, suggerimenti rapidi sul client Skype, connettività di messaggistica istantanea pubblica  <br/>  Exchange Online, Exchange Online Protection e SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Scenario 3: ambito di Azure ExpressRoute solo per i servizi di Office 365

Woodgrove Bank è un cliente di diversi servizi cloud Microsoft, tra cui Office 365. Dopo aver valutato la capacità di rete e il consumo, Woodgrove Bank decide di distribuire Azure ExpressRoute come percorso preferito per i servizi di Office 365 supportati. Le tabelle di routing possono supportare il set completo di prefissi IP di Office 365 e i circuiti Di Azure ExpressRoute di cui è stato eseguito il provisioning supportano tutte le esigenze di larghezza di banda e latenza proiettate.
  
Per garantire il traffico di rete associato a servizi cloud Microsoft diversi da Office 365, Woodgrove Bank ha come ambito l'uso di ExpressRoute per Office 365 in tutti i prefissi IP contrassegnati con valori specifici della community BGP di Office 365, 12076:5010, 12076:5020, 12076:5030, 12076:5100.

|**Tag community BGP usato**|**Funzionalità instradabile su Azure ExpressRoute**|**Route Internet necessarie**|
|:-----|:-----|:-----|
|Exchange, Skype for Business & Microsoft Teams, SharePoint, &amp; altri servizi  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |Exchange Online &amp; Exchange Online Protection  <br/> SharePoint Online &amp; OneDrive for Business  <br/> Segnalazione SIP Skype, download, voce, video e condivisione desktop  <br/> Portale di Office 365, autenticazione di Office 365, &amp; Office in un browser  <br/> | Richieste DNS, CRL, &amp; CDN  <br/>  Tutti gli altri servizi di Office 365 non sono supportati in modo specifico su Azure ExpressRoute  <br/>  Tutti gli altri servizi cloud Microsoft  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Considerazioni chiave sulla pianificazione per l'utilizzo delle community BGP

I clienti che scelgono di sfruttare le community BGP per influenzare il modo in cui ExpressRoute viene annunciato e propagato attraverso la rete dei clienti devono tenere conto delle considerazioni seguenti:
  
- Quando si usano community BGP nella progettazione della rete, è importante garantire che la simmetria delle route sia ancora mantenuta. In alcuni casi, l'aggiunta o la rimozione delle community BGP può creare una situazione in cui il routing simmetrico viene interrotto e la configurazione del routing deve essere aggiornata per ristabilire il routing simmetrico.

- L'ambito di Azure ExpressRoute con i valori della community BGP è un'azione del cliente. Microsoft annuncierà tutti i prefissi IP associati alla relazione di peering indipendentemente dall'ambito configurato dal cliente.

- Azure ExpressRoute non supporta azioni sulla rete di Microsoft in base alle community BGP assegnate al cliente.

- I prefissi IP utilizzati da Office 365 sono contrassegnati solo con valori specifici della community BGP del servizio, le community BGP specifiche della posizione non sono supportate. I servizi di Office 365 sono di natura globale, i prefissi di filtro in base alla posizione del tenant o ai dati all'interno del cloud di Office 365 non sono supportati. L'approccio consigliato consiste nel configurare la rete in modo da coordinare il percorso di rete più breve o preferito dal percorso di rete dell'utente alla rete globale Microsoft, indipendentemente dalla posizione fisica dell'indirizzo IP del servizio Office 365 richiesto.

- I prefissi IP inclusi in ogni valore della community BGP rappresentano una subnet contenente gli indirizzi IP per l'applicazione di Office 365 associata al valore. In alcuni casi, più applicazioni di Office 365 hanno indirizzi IP all'interno di una subnet, con conseguente prefissi IP esistenti in più di un valore di community. Questo comportamento è previsto, anche se raramente, a causa della frammentazione dell'allocazione e non influisce sul numero di prefissi o sugli obiettivi di gestione della larghezza di banda. I clienti sono invitati a usare l'approccio "consenti ciò che serve" invece di "negare ciò che non è necessario" quando sfruttano le community BGP per Office 365 per ridurre al minimo l'effetto.

- L'uso delle community BGP non modifica i requisiti di connettività di rete sottostanti o la configurazione necessaria per usare Office 365. I clienti che desiderano accedere a Office 365 devono comunque essere in grado di accedere a Internet.

- L'ambito di Azure ExpressRoute con le community BGP influisce solo sulle route che la rete interna può visualizzare sulla relazione di peering Microsoft. Potrebbe essere necessario eseguire configurazioni aggiuntive a livello di applicazione, ad esempio l'uso di una configurazione PAC o WPAD insieme al routing con ambito.

- Oltre a usare le community BGP assegnate da Microsoft, i clienti possono scegliere di assegnare le proprie community BGP ai prefissi IP di Office 365 appresi tramite Azure ExpressRoute per influenzare il routing interno. Un caso d'uso comune è l'assegnazione di una community BGP basata sulla posizione a tutte le route apprese attraverso ogni determinata posizione di peering ExpressRoute e quindi l'uso di queste informazioni a valle nella rete del cliente per coordinare il percorso di rete più breve o preferito nella rete di Microsoft. L'uso delle community BGP assegnate al cliente con ExpressRoute per gli scenari di Office 365 non rientra nell'ambito del controllo o della visibilità Microsoft.

Ecco un breve collegamento che puoi usare per tornare: [https://aka.ms/bgpexpressroute365]() .
  
## <a name="related-topics"></a>Argomenti correlati

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute per Office 365](azure-expressroute.md)
  
[Gestione di ExpressRoute per la connettività di Office 365](managing-expressroute-for-connectivity.md)
  
[Routing con ExpressRoute per Office 365](routing-with-expressroute.md)
  
[Pianificazione della rete con ExpressRoute per Office 365](network-planning-with-expressroute.md)
  
[Qualità multimediale e prestazioni della connettività di rete in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[ExpressRoute e QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flusso di chiamata con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Implementazione di ExpressRoute per Office 365](implementing-expressroute.md)
  
[Supporto per le community BGP](/azure/expressroute/expressroute-routing)
  
[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)
  
[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)
  
[Formazione su Azure ExpressRoute per Office 365](https://channel9.msdn.com/series/aer)