---
title: Gestione di ExpressRoute per la connettività di Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: e4468915-15e1-4530-9361-cd18ce82e231
description: Informazioni su come gestire ExpressRoute per Office 365, incluse le aree comuni da configurare come il filtro dei prefissi, la sicurezza e la conformità.
ms.openlocfilehash: 5b55150b91b68954cb7b701afb7cf46ab9b951dd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691555"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Gestione di ExpressRoute per la connettività di Office 365

ExpressRoute per Office 365 offre un percorso di routing alternativo per raggiungere molti servizi di Office 365 senza che sia necessario tutto il traffico per l'uscita verso Internet. Anche se la connessione Internet a Office 365 è ancora necessaria, le route specifiche annunciate da Microsoft tramite BGP alla rete rendono preferito il circuito ExpressRoute diretto, a meno che non siano presenti altre configurazioni nella rete. Le tre aree comuni che è possibile configurare per gestire questo routing includono il filtro dei prefissi, la sicurezza e la conformità.
  
> [!NOTE]
> Microsoft ha modificato la modalità di revisione del dominio di routing del peering Microsoft per Azure ExpressRoute. A partire dal 31 luglio 2017, tutti i clienti di Azure ExpressRoute possono abilitare il peering Microsoft direttamente dalla console di amministrazione di Azure o tramite PowerShell. Dopo aver abilitato il peering Microsoft, qualsiasi cliente può creare filtri di route per ricevere annunci di route BGP per le applicazioni Dynamics 365 Customer Engagement (in precedenza noto come CRM Online). I clienti che necessitano di Azure ExpressRoute per Office 365 devono ottenere la recensione da Microsoft prima di poter creare filtri di route per Office 365. Contattare il team dell'account Microsoft per informazioni su come richiedere una recensione per abilitare Office 365 ExpressRoute. Le sottoscrizioni non autorizzate che tentano di creare filtri di route per Office 365 riceveranno un [messaggio di errore](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>Filtro prefissi

Microsoft consiglia ai clienti di accettare tutte le route BGP come annunciato da Microsoft, le route fornite vengono sottoposte a un rigoroso processo di revisione e convalida, rimuovendo eventuali vantaggi da ulteriori controlli. ExpressRoute offre in modo nativo i controlli consigliati, ad esempio la proprietà, l'integrità e la scala del prefisso IP, senza filtri delle route in ingresso sul lato del cliente.
  
Se è necessaria una convalida aggiuntiva della proprietà della route attraverso il peering pubblico ExpressRoute, è possibile controllare le route annunciate rispetto [all'elenco](https://www.microsoft.com/download/details.aspx?id=53602)di tutti i prefissi IP IPv4 e IPv6 che rappresentano gli intervalli IP pubblici di Microsoft. Questi intervalli coprono l'intero spazio di indirizzi Microsoft e cambiano raramente, fornendo un set affidabile di intervalli in base a cui filtrare, fornendo anche una protezione aggiuntiva ai clienti che sono preoccupati per la perdita di route non di proprietà di Microsoft nel proprio ambiente. Nel caso in cui vi sia una modifica, verrà apportata il 1° del mese e il numero di versione nella sezione dei dettagli della pagina cambierà ogni volta che il file viene aggiornato. 
  
Esistono diversi motivi per evitare l'uso degli URL e degli intervalli di indirizzi IP di [Office 365](https://aka.ms/o365endpoints) per la generazione di elenchi di filtri di prefissi. Tra cui:
  
- I prefissi IP di Office 365 subiscono numerose modifiche su base frequente.

- Gli URL e gli intervalli di indirizzi IP di Office 365 sono progettati per la gestione degli elenchi di indirizzi consentiti dal firewall e dell'infrastruttura proxy, non per il routing.

- Gli URL e gli intervalli di indirizzi IP di Office 365 non coprono altri servizi Microsoft che potrebbero essere nell'ambito delle connessioni ExpressRoute.

|**Opzione**|**Complessità**|**Change Control**|
|:-----|:-----|:-----|
|Accetta tutte le route Microsoft  <br/> |**Basso:** Il cliente si basa sui controlli Microsoft per garantire che tutte le route siano di proprietà corretta.  <br/> |Nessuno  <br/> |
|Filtrare le supernet di proprietà di Microsoft  <br/> |**Medio:** Il cliente implementa elenchi di filtri dei prefissi riepilogati per consentire solo le route di proprietà di Microsoft.  <br/> |I clienti devono assicurarsi che gli aggiornamenti poco frequenti si riflettano nei filtri di route.  <br/> |
|Filtrare gli intervalli IP di Office 365  <br/> [!CAUTION] Not-Recommended |**Alto:** I clienti filtrano le route in base ai prefissi IP di Office 365 definiti.  <br/> |I clienti devono implementare un solido processo di gestione delle modifiche per gli aggiornamenti mensili.  <br/> [!CAUTION] Questa soluzione richiede modifiche significative in corso. Le modifiche non implementate nel tempo potrebbero causare un'interruzione del servizio.   |

La connessione a Office 365 tramite Azure ExpressRoute si basa sugli annunci BGP di subnet IP specifiche che rappresentano le reti in cui vengono distribuiti gli endpoint di Office 365. A causa della natura globale di Office 365 e del numero di servizi che costituiscono Office 365, i clienti spesso hanno la necessità di gestire gli annunci che accettano sulla propria rete. Se si è interessati al numero di prefissi annunciati nell'ambiente, la funzionalità [della community BGP](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) consente di filtrare gli annunci in base a un set specifico di servizi di Office 365. Questa funzionalità è ora disponibile in anteprima.
  
Indipendentemente da come si gestiscono gli annunci di route BGP provenienti da Microsoft, non si ocurrà alcuna esposizione speciale ai servizi di Office 365 rispetto alla connessione a Office 365 solo tramite un circuito Internet. Microsoft mantiene gli stessi livelli di sicurezza, conformità e prestazioni indipendentemente dal tipo di circuito utilizzato da un cliente per connettersi a Office 365.
  
### <a name="security"></a>Sicurezza

Microsoft consiglia di mantenere i controlli della rete e del perimetro di sicurezza personalizzati per le connessioni da e verso ExpressRoute pubblico e il peering Microsoft, che include le connessioni da e verso i servizi di Office 365. I controlli di sicurezza devono essere in atto per le richieste di rete che viaggiano in uscita dalla rete alla rete di Microsoft e in ingresso dalla rete di Microsoft alla rete.
  
#### <a name="outbound-from-customer-to-microsoft"></a>In uscita dal cliente a Microsoft
  
Quando i computer si connettono a Office 365, si connettono allo stesso set di endpoint indipendentemente dal fatto che la connessione sia effettuata tramite un circuito Internet o ExpressRoute. Indipendentemente dal circuito utilizzato, Microsoft consiglia di considerare i servizi di Office 365 più attendibili delle destinazioni Internet generiche. I controlli di sicurezza in uscita devono concentrarsi sulle porte e sui protocolli per ridurre l'esposizione e ridurre al minimo le attività di manutenzione. Le informazioni sulla porta necessarie sono disponibili nell'articolo di riferimento sugli endpoint di [Office 365.](https://aka.ms/o365endpoints)
  
Per i controlli aggiunti, è possibile utilizzare il filtro a livello di FQDN all'interno dell'infrastruttura proxy per limitare o esaminare alcune o tutte le richieste di rete destinate a Internet o Office 365. La gestione dell'elenco di FQDN non appena vengono rilasciate le funzionalità e l'evoluzione delle offerte di Office 365 richiede una gestione delle modifiche e un monitoraggio più affidabili delle modifiche apportate agli [endpoint di Office 365](https://aka.ms/o365endpoints)pubblicati.
  
> [!CAUTION]
> Microsoft consiglia di non fare affidamento esclusivamente sui prefissi IP per gestire la sicurezza in uscita in Office 365.

|**Opzione**|**Complessità**|**Change Control**|
|:-----|:-----|:-----|
|Nessuna restrizione  <br/> |**Basso:** Il cliente consente l'accesso in uscita illimitato a Microsoft.  <br/> |Nessuno  <br/> |
|Restrizioni delle porte  <br/> |**Basso:** Il cliente limita l'accesso in uscita a Microsoft dalle porte previste.  <br/> |Poco frequenti.  <br/> |
|Restrizioni FQDN  <br/> |**Alto:** Il cliente limita l'accesso in uscita a Office 365 in base agli FQDN pubblicati.  <br/> |Modifiche mensili.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>In ingresso da Microsoft al cliente
  
Esistono diversi scenari facoltativi che richiedono a Microsoft di avviare connessioni alla rete.
  
- ADFS durante la convalida della password per l'accesso.

- [Exchange Server distribuzioni ibride.](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)

- Posta da un tenant di Exchange Online a un host locale.

- Invio della posta di SharePoint Online da SharePoint Online a un host locale.

- [Ricerca ibrida federata di SharePoint.](https://technet.microsoft.com/library/dn197174.aspx)

- [SharePoint ibrido BCS](https://technet.microsoft.com/library/dn197239.aspx ).

- [Federazione ibrida di Skype for Business](https://technet.microsoft.com/library/jj205403.aspx) e/o Skype for [Business.](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx)

- [Skype for Business Cloud Connector.](https://technet.microsoft.com/library/mt605227.aspx )

Microsoft consiglia di accettare queste connessioni tramite il circuito Internet anziché il circuito ExpressRoute per ridurre la complessità. Se le esigenze di conformità o prestazioni determinano che queste connessioni in ingresso devono essere accettate su un circuito ExpressRoute, è consigliabile utilizzare un firewall o un proxy inverso per l'ambito delle connessioni accettate. È possibile usare gli [endpoint di Office 365](https://aka.ms/o365endpoints) per capire gli FQDN e i prefissi IP.
  
### <a name="compliance"></a>Conformità

Microsoft non si basa sul percorso di instradamento utilizzato per nessuno dei controlli di conformità. Indipendentemente dal fatto che ci si connetta ai servizi di Office 365 tramite un circuito ExpressRoute o Internet, i controlli di conformità non cambieranno. È consigliabile esaminare i diversi livelli di certificazione di conformità e sicurezza per Office 365 per trovare la scelta migliore per soddisfare le esigenze dell'organizzazione.
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/manageexpressroute365](https://aka.ms/manageexpressroute365)
  
## <a name="related-topics"></a>Argomenti correlati

[Reti per la distribuzione di contenuti](content-delivery-networks.md)
  
[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Formazione su Azure ExpressRoute per Office 365](https://channel9.msdn.com/series/aer)
