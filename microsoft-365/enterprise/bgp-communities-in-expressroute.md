---
title: Utilizzo delle community BGP in ExpressRoute per gli scenari di Office 365
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
description: Informazioni su come utilizzare le community BGP in Azure ExpressRoute per gestire il numero di prefissi IP e la larghezza di banda necessaria per gli scenari di Office 365.
ms.openlocfilehash: 3a1de8725ae967352723649e602d944ca6948310
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691401"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Utilizzo delle community BGP in ExpressRoute per gli scenari di Office 365

La connessione a Office 365 con Azure ExpressRoute si basa su annunci BGP di subnet IP specifiche che rappresentano le reti in cui vengono distribuiti gli endpoint di Office 365. A causa della natura globale di Office 365 e del numero di servizi che costituiscono Office 365, i clienti spesso hanno la necessità di gestire gli annunci che accettano nella propria rete. Riduzione del numero di subnet IP; denominati prefissi IP per tutto il resto di questo articolo, per allineare con la terminologia di gestione della rete BGP, sono serviti i seguenti obiettivi finali per i clienti:
  
- **Gestire il numero di prefissi IP annunciati accettati** -i clienti che dispongono di un'infrastruttura di rete interna o di una rete che supporta solo un numero limitato di prefissi IP e i clienti che dispongono di un gestore di rete che si addice all'accettazione di prefissi superiori a un numero limitato vorranno valutare il numero totale di prefissi già pubblicizzati nella propria rete e selezionare le applicazioni di 365 Office

- **Gestire la quantità di larghezza di banda necessaria sul circuito di ExpressRoute di Azure** -i clienti possono controllare l'inviluppo di larghezza di banda dei servizi di Office 365 sul percorso ExpressRoute e sul percorso Internet. In questo modo i clienti possono prenotare la larghezza di banda di ExpressRoute per applicazioni specifiche come Skype for business e instradare le restanti applicazioni di Office 365 sul percorso Internet.

Per assistere i clienti con questi obiettivi, i prefissi IP di Office 365 che vengono pubblicizzati su ExpressRoute sono contrassegnati con i valori specifici del servizio della community BGP, come illustrato nell'esempio seguente.
  
> [!NOTE]
> È prevedibile che il traffico di rete associato ad altre applicazioni sia incluso nel valore community. Si tratta di un comportamento previsto per un software globale come offerta del servizio con i servizi condivisi e i datacenter. Questa operazione è stata ridotta a icona quando possibile con i due obiettivi sopra riportati, gestendo il numero di prefisso e/o la larghezza di banda in mente.

|**Servizio**|**Valore comunitario BGP**|**Note**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Include i servizi di Exchange e EOP\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype for Business\*  <br/> |12076:5030  <br/> |Skype for business online & servizi Microsoft Teams  <br/> |
|Altri servizi di Office 365\*  <br/> |12076:5100  <br/> |Include Azure Active Directory (scenari di sincronizzazione della directory e di autenticazione) così come i servizi portale di Office 365  <br/> |
|\* L'ambito degli scenari di servizio inclusi in ExpressRoute è documentato nell'articolo degli [endpoint di Office 365](https://aka.ms/o365endpoints) .  <br/> \*\*In futuro, è possibile aggiungere ulteriori servizi e i valori della community BGP. [Vedere l'elenco corrente delle community BGP](https://azure.microsoft.com/documentation/articles/expressroute-routing/).  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>Quali sono gli scenari più comuni per l'utilizzo di community BGP?

I clienti possono utilizzare le community BGP per regolare i gruppi di prefissi IP accettati dalla propria rete tramite Azure ExpressRoute, influenzando così il numero totale di prefisso IP e l'inviluppo di larghezza di banda previsto di alcuni servizi di Office 365. È importante comprendere che tutti gli Office 365 richiedono traffico associato Internet indipendentemente dall'utilizzo delle community di Azure ExpressRoute o BGP. I tre scenari seguenti sono gli usi più comuni di questa funzionalità.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Scenario 1: riduzione del numero di prefissi IP di Office 365

Contoso Corporation è una società di 50.000 persone che attualmente utilizza Office 365 per Exchange Online e SharePoint Online. Nella revisione dei requisiti di ExpressRoute contoso determina che i dispositivi di rete in molti percorsi regionali non sono in grado di gestire le dimensioni della tabella di routing superiori a 100 voci di route aggiuntive. Contoso ha esaminato il numero totale di prefissi IP che ExpressRoute avrebbe pubblicizzato per l'intero set di servizi di Office 365 e ha concluso che è superiore a 100. Per rimanere all'interno delle voci di route aggiuntive di 100, contoso ambisce l'utilizzo di ExpressRoute per Office 365 solo al valore della community di SharePoint Online BGP, 12076:5020, ricevuto tramite ExpressRoute Microsoft peering.

|**Tag community BGP utilizzato**|**Funzionalità instradabili su ExpressRoute di Azure**|**Route Internet obbligatorie**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint Online &amp; OneDrive for business  <br/> | Richieste DNS, CRL, &amp; CDN  <br/>  Tutti gli altri servizi di Office 365 non supportati in modo specifico su Azure ExpressRoute  <br/>  Tutti gli altri servizi cloud Microsoft  <br/>  Office 365 portal, Office 365 Authentication, &amp; Office in a browser  <br/>  Exchange Online, Exchange Online Protection e Skype for business online  <br/> |

> [!NOTE]
> Per ottenere un numero di prefisso inferiore per ogni servizio, viene mantenuta una quantità minima di sovrapposizione tra i servizi. Si tratta di un comportamento previsto.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Scenario 2: ambito ExpressRoute e utilizzo della larghezza di banda interna per alcuni servizi di Office 365

Fabrikam Inc, un'azienda multinazionale di grandi dimensioni con una rete eterogenea distribuita, è un Sottoscrittore di numerosi servizi di Office 365, tra cui: Exchange Online, SharePoint Online e Skype for business online. L'infrastruttura di routing interna di Fabrikam è in grado di gestire migliaia di prefissi IP nelle tabelle di routing. Tuttavia, Fabrikam desidera solo eseguire il provisioning di ExpressRoute e la larghezza di banda interna per le applicazioni di Office 365 che sono più sensibili alle prestazioni della rete e utilizzano la larghezza di banda Internet esistente per tutte le altre applicazioni di Office 365.
  
Per questo motivo, Fabrikam ambisce la larghezza di banda di ExpressRoute di Azure a solo Skype for business online BGP community value, 12076:5030, ricevuto tramite ExpressRoute Microsoft peering. Il traffico di rete rimanente associato a Office 365 continua a utilizzare i punti di uscita Internet.

|**Tag community BGP utilizzato**|**Funzionalità instradabili su ExpressRoute di Azure**|**Route Internet obbligatorie**|
|:-----|:-----|:-----|
|Skype for Business  <br/> (12076:5030)  <br/> |Segnalazioni di Skype SIP, download, Voice, video e condivisione del desktop  <br/> | Richieste DNS, CRL, &amp; CDN  <br/>  Tutti gli altri servizi di Office 365 non supportati in modo specifico su Azure ExpressRoute  <br/>  Tutti gli altri servizi cloud Microsoft  <br/>  Office 365 portal, Office 365 Authentication, &amp; Office in a browser  <br/>  Telemetria Skype for business, suggerimenti rapidi del client Skype, connettività per messaggistica istantanea pubblica  <br/>  Exchange Online, Exchange Online Protection e SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Scenario 3: solo per l'ambito di Azure ExpressRoute per i servizi di Office 365

La Woodgrove Bank è un cliente di numerosi servizi cloud Microsoft, tra cui Office 365. Dopo aver valutato la capacità della rete e il consumo della Woodgrove Bank decide di distribuire Azure ExpressRoute come percorso preferito per i servizi di Office 365 supportati. Le tabelle di routing sono in grado di supportare il set completo di prefissi IP di Office 365 e i circuiti di Azure ExpressRoute che hanno eseguito il provisioning supportano tutte le esigenze di larghezza di banda e latenza proiettate.
  
Per garantire il traffico di rete associato ai servizi cloud Microsoft diversi da Office 365, la Woodgrove Bank ambites l'utilizzo di ExpressRoute per Office 365 su tutti i prefissi IP contrassegnati con i valori di Office 365 specific BGP community, 12076:5010, 12076:5020, 12076:5030, 12076:5100.

|**Tag community BGP utilizzato**|**Funzionalità instradabili su ExpressRoute di Azure**|**Route Internet obbligatorie**|
|:-----|:-----|:-----|
|Exchange, Skype for business & Microsoft teams, SharePoint, &amp; altri servizi  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |Exchange Online &amp; Exchange Online Protection  <br/> SharePoint Online &amp; OneDrive for business  <br/> Segnalazioni di Skype SIP, download, Voice, video e condivisione del desktop  <br/> Office 365 portal, Office 365 Authentication, &amp; Office in a browser  <br/> | Richieste DNS, CRL, &amp; CDN  <br/>  Tutti gli altri servizi di Office 365 non supportati in modo specifico su Azure ExpressRoute  <br/>  Tutti gli altri servizi cloud Microsoft  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Considerazioni di pianificazione chiave per l'utilizzo di community BGP

I clienti che scelgono di avvalersi delle community BGP per influenzare il modo in cui ExpressRoute viene pubblicizzato e propagato tramite la rete del cliente devono tenere conto delle considerazioni seguenti:
  
- Quando si utilizzano le community BGP nella progettazione della rete, è importante garantire che la simmetria del percorso sia ancora mantenuta. In alcuni casi, l'aggiunta o la rimozione delle Comunità BGP potrebbe creare una situazione in cui il routing simmetrico viene interrotto e la configurazione del routing deve essere aggiornata per ristabilire il routing simmetrico.

- L'ambito di Azure ExpressRoute con i valori della community BGP è un'azione del cliente. Microsoft annuncierà tutti i prefissi IP associati alla relazione peering indipendentemente dall'ambito configurato dal cliente.

- Azure ExpressRoute non supporta alcuna azione sulla rete Microsoft in base alle comunità BGP assegnate ai clienti.

- I prefissi IP utilizzati da Office 365 sono contrassegnati solo con valori specifici per la community di servizi BGP, le community BGP specifiche per la posizione non sono supportate. I servizi di Office 365 sono di natura globale, i prefissi del filtro in base alla posizione del tenant o ai dati all'interno del cloud di Office 365 non sono supportati. L'approccio consigliato consiste nel configurare la rete in modo da coordinare il percorso di rete più breve o più preferito dal percorso di rete dell'utente nella rete globale di Microsoft, indipendentemente dalla posizione fisica dell'indirizzo IP del servizio Office 365 che stanno richiedendo.

- I prefissi IP inclusi in ogni valore della community BGP rappresentano una subnet che contiene gli indirizzi IP per l'applicazione Office 365 associata al valore. In alcuni casi, più di un'applicazione di Office 365 dispone di indirizzi IP all'interno di una subnet con un prefisso IP che esiste in più di un valore comunitario. Questo comportamento è previsto, anche se raramente, a causa della frammentazione dell'allocazione e non influisce sugli obiettivi di gestione della larghezza di banda o del conteggio dei prefissi. I clienti sono invitati a utilizzare l'approccio "Consenti ciò che è necessario" anziché "negare ciò che non è necessario" quando si approfitta delle community BGP per Office 365 per minimizzare l'effetto.

- L'utilizzo di community BGP non modifica i requisiti di connettività di rete o la configurazione necessari per l'utilizzo di Office 365. È comunque necessario che i clienti che desiderano accedere a Office 365 siano in grado di accedere a Internet.

- L'ambito di Azure ExpressRoute con le community BGP influisce solo sulle route che la rete interna può visualizzare sulla relazione Microsoft peering. Potrebbe essere necessario apportare ulteriori configurazioni a livello di applicazione, ad esempio l'utilizzo di una configurazione PAC o WPAD, in combinazione con il routing con ambito.

- Oltre a utilizzare le community di Microsoft BGP assegnate, i clienti possono scegliere di assegnare le proprie comunità BGP ai prefissi IP di Office 365 imparati tramite Azure ExpressRoute per influire sul routing interno. Un caso di utilizzo popolare è l'assegnazione di una comunità BGP basata sulla posizione a tutte le rotte acquisite tramite ogni percorso di peering di ExpressRoute e quindi l'utilizzo di tali informazioni nella rete del cliente per coordinare il percorso di rete più breve o più preferito nella rete di Microsoft. L'utilizzo delle community di BGP assegnate ai clienti con ExpressRoute per gli scenari di Office 365 non è compreso nell'ambito del controllo Microsoft o della visibilità.

Ecco un breve collegamento che è possibile utilizzare per tornare: [https://aka.ms/bgpexpressroute365](https://aka.ms/bgpexpressroute365) .
  
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
  
[Supporto per le community BGP](https://azure.microsoft.com/documentation/articles/expressroute-routing/)
  
[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)
  
[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)
  
[Formazione di Azure ExpressRoute per Office 365](https://channel9.msdn.com/series/aer)
