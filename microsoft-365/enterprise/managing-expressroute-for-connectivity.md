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
description: Informazioni su come gestire ExpressRoute per Office 365, incluse le aree comuni da configurare come il filtro del prefisso, la sicurezza e la conformità.
ms.openlocfilehash: 5b55150b91b68954cb7b701afb7cf46ab9b951dd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691555"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Gestione di ExpressRoute per la connettività di Office 365

ExpressRoute per Office 365 offre un percorso di routing alternativo per raggiungere numerosi servizi di Office 365 senza che sia necessario che tutto il traffico venga in uscita su Internet. Anche se la connessione Internet a Office 365 è ancora necessaria, le route specifiche che Microsoft annuncia tramite BGP alla rete rendono il circuito ExpressRoute diretto preferito, a meno che non siano presenti altre configurazioni della rete. Le tre aree comuni che possono essere configurate per gestire questo percorso includono il filtro, la sicurezza e la conformità del prefisso.
  
> [!NOTE]
> Microsoft ha modificato il modo in cui viene esaminato il dominio di routing peering di Microsoft per Azure ExpressRoute. A partire dal 31 luglio 2017, tutti i clienti di ExpressRoute di Azure possono abilitare Microsoft peering direttamente dalla console di amministrazione di Azure o tramite PowerShell. Dopo aver abilitato il peering Microsoft, tutti i clienti possono creare filtri di route per ricevere gli annunci route BGP per le applicazioni di impegno dei clienti Dynamics 365 (in precedenza noto come CRM online). I clienti che hanno bisogno di Azure ExpressRoute per Office 365 devono ottenere la revisione da Microsoft prima che possano creare filtri di route per Office 365. Contattare il team dell'account Microsoft per informazioni su come richiedere una revisione per l'abilitazione di Office 365 ExpressRoute. Gli abbonamenti non autorizzati che tentano di creare filtri di route per Office 365 riceveranno un [messaggio di errore](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>Filtro prefisso

Microsoft consiglia ai clienti di accettare tutte le rotte BGP come pubblicizzate da Microsoft, le rotte fornite subiscono una rigorosa revisione e processo di convalida, eliminando eventuali vantaggi per il controllo aggiunto. ExpressRoute offre in modo nativo i controlli consigliati, come la proprietà del prefisso IP, l'integrità e la scalabilità, senza filtraggio delle route in ingresso sul fianco del cliente.
  
Se si richiede ulteriore convalida della proprietà di route tra peering pubblico di ExpressRoute, è possibile controllare le route pubblicizzate con l'elenco di tutti i prefissi IP IPv4 e IPv6 che rappresentano [gli intervalli di indirizzi IP pubblici di Microsoft](https://www.microsoft.com/download/details.aspx?id=53602). Questi intervalli coprono lo spazio di indirizzi Microsoft completo e cambiano di frequente, fornendo un set affidabile di intervalli di cui filtrare i contenuti che fornisce anche ulteriore protezione ai clienti preoccupati per le rotte di proprietà non Microsoft che fuoriescono nel loro ambiente. Nel caso in cui si verifichi una modifica, verrà eseguito il 1 ° mese e il numero di versione nella sezione **Dettagli** della pagina cambia ogni volta che il file verrà aggiornato.
  
Esistono diversi motivi per evitare l'utilizzo degli [URL di Office 365 e degli intervalli di indirizzi IP](https://aka.ms/o365endpoints) per la generazione di elenchi di filtri di prefisso. Sono inclusi gli elementi seguenti:
  
- I prefissi IP di Office 365 subiscono molte modifiche su base frequente.

- Gli intervalli di indirizzi IP e URL di Office 365 sono stati creati per la gestione del firewall Consenti elenchi e infrastruttura proxy, non per il routing.

- Gli intervalli di indirizzi IP e URL di Office 365 non riguardano altri servizi Microsoft che possono essere nell'ambito delle connessioni di ExpressRoute.

|**Opzione**|**Complessità**|**Controllo delle modifiche**|
|:-----|:-----|:-----|
|Accettare tutte le route Microsoft  <br/> |**Bassa:** Il cliente si affida ai controlli Microsoft per garantire che tutte le rotte siano possedute correttamente.  <br/> |Nessuno  <br/> |
|Filtrare le reti supernets di Microsoft  <br/> |**Medium:** Il cliente implementa gli elenchi di filtri dei prefissi riepilogati per consentire solo le route di proprietà di Microsoft.  <br/> |I clienti devono garantire che gli aggiornamenti non frequenti vengano riflessi nei filtri route.  <br/> |
|Filtrare gli intervalli di indirizzi IP di Office 365  <br/> [!CAUTION] Non consigliato |**Alta:** Le route dei filtri dei clienti si basano sui prefissi IP di Office 365 definiti.  <br/> |I clienti devono implementare un processo di gestione delle modifiche affidabile per gli aggiornamenti mensili.  <br/> [!CAUTION] Questa soluzione richiede importanti modifiche in continuo. Le modifiche non implementate nel tempo probabilmente provocheranno un'interruzione del servizio.   |

La connessione a Office 365 con Azure ExpressRoute si basa su annunci BGP di subnet IP specifiche che rappresentano le reti in cui vengono distribuiti gli endpoint di Office 365. A causa della natura globale di Office 365 e del numero di servizi che compongono Office 365, i clienti spesso hanno la necessità di gestire gli annunci che accettano nella propria rete. Se si è interessati al numero di prefissi pubblicizzati nell'ambiente, la funzionalità [community BGP](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) consente di filtrare gli annunci pubblicitari in un set specifico di servizi di Office 365. Questa funzionalità è ora in anteprima.
  
Indipendentemente da come gestire la route BGP annunci provenienti da Microsoft, non si otterrà alcuna esposizione speciale ai servizi di Office 365 rispetto alla connessione a Office 365 su un circuito Internet solo. Microsoft mantiene gli stessi livelli di sicurezza, conformità e prestazioni indipendentemente dal tipo di circuito utilizzato da un cliente per la connessione a Office 365.
  
### <a name="security"></a>Sicurezza

Microsoft consiglia di mantenere i propri controlli perimetrali di rete e sicurezza per le connessioni da e verso ExpressRoute Public e Microsoft peering, che include connessioni da e verso i servizi di Office 365. I controlli di sicurezza devono essere disponibili per le richieste di rete che viaggiano in uscita dalla rete alla rete Microsoft e in ingresso dalla rete di Microsoft alla rete.
  
#### <a name="outbound-from-customer-to-microsoft"></a>In uscita dal cliente a Microsoft
  
Quando i computer si connettono a Office 365, si connettono allo stesso set di endpoint, indipendentemente dal fatto che la connessione venga effettuata tramite un circuito Internet o ExpressRoute. Indipendentemente dal circuito utilizzato, Microsoft consiglia di trattare i servizi di Office 365 come attendibili rispetto alle destinazioni Internet generiche. I controlli di sicurezza in uscita devono concentrarsi sulle porte e sui protocolli per ridurre l'esposizione e ridurre al minimo la manutenzione in uscita. Le informazioni sulla porta necessarie sono disponibili nell'articolo di riferimento per gli [endpoint di Office 365](https://aka.ms/o365endpoints) .
  
Per i controlli aggiunti, è possibile utilizzare il filtro di livello FQDN all'interno dell'infrastruttura proxy per limitare o ispezionare alcune o tutte le richieste di rete destinate a Internet o a Office 365. La gestione dell'elenco di nomi FQDN come funzionalità vengono rilasciate e le offerte di Office 365 evolvono richiedono una maggiore robustezza delle modifiche e la verifica dei cambiamenti apportati agli [endpoint di Office 365](https://aka.ms/o365endpoints)pubblicati.
  
> [!CAUTION]
> Microsoft consiglia di non fare affidamento solo sui prefissi IP per gestire la sicurezza in uscita in Office 365.

|**Opzione**|**Complessità**|**Controllo delle modifiche**|
|:-----|:-----|:-----|
|Nessuna restrizione  <br/> |**Bassa:** Il cliente consente l'accesso in uscita illimitato a Microsoft.  <br/> |Nessuno  <br/> |
|Restrizioni delle porte  <br/> |**Bassa:** Il cliente limita l'accesso in uscita a Microsoft dalle porte previste.  <br/> |Rara.  <br/> |
|Restrizioni FQDN  <br/> |**Alta:** Il cliente limita l'accesso in uscita a Office 365 in base ai nomi FQDN pubblicati.  <br/> |Modifiche mensili.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>In ingresso da Microsoft al cliente
  
Sono disponibili diversi scenari facoltativi che richiedono che Microsoft avvii le connessioni alla rete.
  
- ADFS durante la convalida delle password per l'accesso.

- [Distribuzioni ibride di Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).

- Posta da un tenant di Exchange Online a un host locale.

- Posta elettronica di SharePoint Online inviata da SharePoint Online a un host locale.

- [Ricerca ibrida federata di SharePoint](https://technet.microsoft.com/library/dn197174.aspx).

- [BCS ibrido di SharePoint](https://technet.microsoft.com/library/dn197239.aspx ).

- Federazione di [Skype for business ibrida](https://technet.microsoft.com/library/jj205403.aspx) e/o [Skype for business](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).

- [Connettore Cloud Skype for business](https://technet.microsoft.com/library/mt605227.aspx ).

Microsoft consiglia di accettare queste connessioni sul circuito Internet invece che sul circuito di ExpressRoute per ridurre la complessità. Se le esigenze di conformità o di prestazioni prevedono che queste connessioni in ingresso devono essere accettate su un circuito ExpressRoute, utilizzando un firewall o un proxy inverso per l'ambito, è consigliabile utilizzare le connessioni accettate. È possibile utilizzare gli [endpoint di Office 365](https://aka.ms/o365endpoints) per individuare gli FQDN e i prefissi IP giusti.
  
### <a name="compliance"></a>Conformità

Non si basa sul percorso di routing utilizzato per i controlli di conformità. Indipendentemente dal fatto che ci si connette a servizi di Office 365 su un circuito ExpressRoute o Internet, i controlli di conformità non cambiano. È consigliabile esaminare i diversi livelli di certificazione di conformità e sicurezza di Office 365 per individuare la scelta migliore per soddisfare le esigenze dell'organizzazione.
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/manageexpressroute365](https://aka.ms/manageexpressroute365)
  
## <a name="related-topics"></a>Argomenti correlati

[Reti per la distribuzione di contenuti](content-delivery-networks.md)
  
[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Formazione di Azure ExpressRoute per Office 365](https://channel9.msdn.com/series/aer)
