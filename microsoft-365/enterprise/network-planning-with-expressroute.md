---
title: Pianificazione della rete con ExpressRoute per Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/14/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 103208f1-e788-4601-aa45-504f896511cd
description: In questo articolo vengono fornite informazioni su Azure ExpressRoute per Office 365 e su come utilizzarlo per la pianificazione della rete.
ms.openlocfilehash: 7159640adeae1b4a4ff364683f939a97b6e06a92
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691268"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Pianificazione della rete con ExpressRoute per Office 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

ExpressRoute per Office 365 fornisce la connettività Layer 3 tra la rete e i datacenter di Microsoft. I circuiti utilizzano la route BGP (Border Gateway Protocol) per la pubblicità dei server front-end di Office 365. Dal punto di vista dei dispositivi locali, quando è necessario selezionare il percorso TCP/IP corretto per Office 365, Azure ExpressRoute viene visualizzato come alternativa a Internet.
  
Azure ExpressRoute aggiunge un percorso diretto a un set specifico di funzionalità e servizi supportati offerti dai server di Office 365 all'interno dei datacenter di Microsoft. Azure ExpressRoute non sostituisce la connettività Internet ai Data Center Microsoft o ai servizi Internet di base come la risoluzione del nome di dominio. Azure ExpressRoute e i circuiti Internet devono essere protetti e ridondanti.
  
Nella tabella seguente sono riportate alcune differenze tra le connessioni Internet e Azure ExpressRoute nel contesto di Office 365.

|**Differenze nella pianificazione della rete**|**Connessione di rete Internet**|**Connessione di rete ExpressRoute**|
|:-----|:-----|:-----|
| Accesso ai servizi Internet richiesti, tra cui;  <br/>  Risoluzione del nome DNS  <br/>  Verifica della revoca del certificato  <br/>  Reti per la distribuzione di contenuti (CDN)  <br/> |Sì  <br/> |Le richieste all'infrastruttura DNS e/o CDN di proprietà di Microsoft possono utilizzare la rete ExpressRoute.  <br/> |
| Accesso ai servizi di Office 365, tra cui;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype for Business Online  <br/>  Office in un browser  <br/>  Portale e autenticazione di Office 365  <br/> |Sì, tutte le applicazioni e le funzionalità  <br/> |Sì, [applicazioni e funzionalità specifiche](https://aka.ms/o365endpoints) <br/> |
|Sicurezza locale al perimetro.  <br/> |Sì  <br/> |Sì  <br/> |
|Pianificazione della disponibilità elevata.  <br/> |Failover a una connessione di rete Internet alternativa  <br/> |Failover a una connessione ExpressRoute alternativa  <br/> |
|Connessione diretta con un profilo di rete prevedibile.  <br/> |No  <br/> |Sì  <br/> |
|Connettività IPv6.  <br/> |Sì  <br/> |Sì  <br/> |

Espandere i titoli riportati di seguito per ulteriori informazioni sulla pianificazione della rete. Inoltre, è stata registrata una serie [di corsi di formazione di ExpressRoute per Office 365 di](https://channel9.msdn.com/series/aer) 10 parti che si tuffa più in profondità.

## <a name="existing-azure-expressroute-customers"></a>Clienti di Azure ExpressRoute esistenti

Se si utilizza un circuito di Azure ExpressRoute esistente e si desidera aggiungere la connettività di Office 365 su questo circuito, è necessario esaminare il numero di circuiti, le posizioni di uscita e le dimensioni dei circuiti per assicurarsi che soddisfino le esigenze dell'utilizzo di Office 365. La maggior parte dei clienti richiede ulteriore larghezza di banda e molti richiedono ulteriori circuiti.
  
Per abilitare l'accesso a Office 365 sui circuiti di ExpressRoute di Azure esistenti, [configurare i filtri route](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) per garantire che i servizi di Office 365 siano accessibili.
  
La sottoscrizione di Azure ExpressRoute è incentrata sui clienti, ovvero gli abbonamenti sono legati ai clienti. Come cliente, è possibile disporre di più circuiti di ExpressRoute di Azure e accedere a molte risorse cloud Microsoft su tali circuiti. Ad esempio, è possibile scegliere di accedere a una macchina virtuale ospitata in Azure, a un tenant di testing di Office 365 e a un tenant di produzione di Office 365 su una coppia di circuiti di ExpressRoute di Azure ridondanti.
  
In questa tabella vengono illustrati i due tipi di relazioni di peering che è possibile scegliere di implementare nei circuiti.

|**Relazione peering**|**Azure privato**|**Microsoft**|
|:-----|:-----|:-----|
|**Servizi** <br/> |IaaS: macchine virtuali di Azure  <br/> |PaaS: Servizi pubblici di Azure  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Avvio della connessione * * * * <br/> |Customer-to-Microsoft  <br/> Microsoft-to-Customer  <br/> |Customer-to-Microsoft  <br/> Microsoft-to-Customer  <br/> |
|**Supporto QoS** <br/> |Nessuna QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> QoS supporta Skype for business solo in questo momento.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Pianificazione della larghezza di banda per ExpressRoute di Azure

Tutti i clienti di Office 365 dispongono di una larghezza di banda univoca, a seconda del numero di persone in ogni posizione, di come sono attivi con ogni applicazione di Office 365 e di altri fattori, come l'utilizzo di apparecchiature locali o ibride e configurazioni di sicurezza di rete.
  
La presenza di una larghezza di banda troppo limitata comporta congestioni, ritrasmissioni di dati e ritardi imprevedibili. La presenza di una quantità eccessiva di larghezza di banda provocherà costi inutili. In una rete esistente, la larghezza di banda viene spesso definita in termini di quantità di spazio disponibile sul circuito come percentuale. La disponibilità del 10% può comportare una congestione e l'altezza del 80% generalmente comporta costi non necessari. Gli stanziamenti di destinazione tipici del margine sono del 20%-50%.
  
Per individuare il livello di larghezza di banda appropriato, è consigliabile testare il consumo di rete esistente. Questo è l'unico modo per ottenere una vera misura di utilizzo e di necessità, poiché ogni configurazione di rete e le applicazioni sono in qualche modo univoci. Quando si misura, è necessario prestare particolare attenzione al consumo totale di larghezza di banda, alla latenza e alla congestione TCP per comprendere le esigenze della rete.
  
Dopo aver valutato la linea di base che include tutte le applicazioni di rete, Office Pilot 365 con un piccolo gruppo che comprende i diversi profili di persone nell'organizzazione per determinare l'utilizzo effettivo e utilizzare le due misure per stimare la larghezza di banda necessaria per ogni posizione di Office. In caso di problemi di latenza o TCP congestione riscontrati nei test, potrebbe essere necessario spostare l'uscita più vicino alle persone che usano Office 365 o rimuovere un'analisi intensiva della rete, ad esempio la decrittografia o l'ispezione SSL.
  
Tutti i suggerimenti su quale tipo di elaborazione della rete è consigliato si applicano sia ai circuiti di ExpressRoute che a Internet. Lo stesso vale per le altre linee guida del [sito di ottimizzazione delle prestazioni](https://aka.ms/tune).
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Applicazione dei controlli di sicurezza a Azure ExpressRoute per gli scenari di Office 365

La protezione della connettività di ExpressRoute di Azure inizia con gli stessi principi di protezione della connettività Internet. Molti clienti scelgono di distribuire controlli di rete e perimetrali lungo il percorso ExpressRoute che collega la rete locale a Office 365 e ad altri cloud Microsoft. Questi controlli possono includere firewall, proxy di applicazioni, prevenzione della perdita di dati, rilevamento delle intrusioni, sistemi di prevenzione delle intrusioni e così via. In molti casi, i clienti applicano diversi livelli di controlli al traffico avviato da Microsoft in locale, rispetto al traffico avviato da Microsoft che si rivolge alla rete locale del cliente, rispetto al traffico avviato da una destinazione Internet generale.
  
Di seguito sono riportati alcuni esempi di integrazione della sicurezza con il [modello di connettività di ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-connectivity-models) che si sceglie di distribuire.

|**Opzione di integrazione di ExpressRoute**|**Modello perimetrale di sicurezza di rete**|
|:-----|:-----|
|Percorso condiviso in un exchange cloud  <br/> |Installare nuovo o sfruttare l'infrastruttura di sicurezza/perimetro esistente nella struttura di co-location in cui è stabilita la connessione ExpressRoute.  <br/> Sfruttare la funzionalità di co-location solo per gli scopi di routing/interconnessione e le connessioni di back haul dalla funzionalità di co-location all'infrastruttura di sicurezza/perimetro locale.  <br/> |
|Ethernet Point-to-Point  <br/> |Terminare la connessione a ExpressRoute Point-to-Point nel percorso dell'infrastruttura di sicurezza/perimetrale esistente.  <br/> Installare nuova infrastruttura di sicurezza/perimetrale specifica del percorso di ExpressRoute e terminare la connessione punto-punto.  <br/> |
|IPVPN any-to-any  <br/> |Sfruttare un'infrastruttura di sicurezza/perimetrale locale esistente in tutte le posizioni che vengono esportate nel IPVPN utilizzato per ExpressRoute per la connettività di Office 365.  <br/> Tornanti il IPVPN utilizzato per ExpressRoute per Office 365 a specifiche posizioni locali designate per fungere da protezione/perimetro.  <br/> |

Alcuni provider di servizi offrono anche funzionalità di sicurezza/perimetro gestite come parte delle loro soluzioni di integrazione con Azure ExpressRoute.
  
Quando si considera la disposizione della topologia delle opzioni di rete/perimetro di sicurezza utilizzate per le connessioni di ExpressRoute per Office 365, vengono riportate considerazioni aggiuntive
  
- La profondità e i controlli di sicurezza e di rete dei tipi potrebbero avere un impatto sulle prestazioni e sulla scalabilità dell'esperienza utente di Office 365.

- I flussi in uscita (locali- \> Microsoft) e in ingresso (Microsoft-locale \> ) [se abilitato] possono avere requisiti diversi. Queste sono probabilmente diverse da quelle in uscita per le destinazioni Internet generali.

- I requisiti di Office 365 per le porte e i protocolli e le subnet IP necessarie sono gli stessi se il traffico viene instradato tramite ExpressRoute per Office 365 o tramite Internet.

- La disposizione topologica dei controlli di sicurezza e di rete del cliente determina la rete finale End to end tra l'utente e il servizio di Office 365 e può avere un impatto sostanziale sulla latenza e sulla congestione della rete.

- I clienti sono invitati a progettare la topologia di sicurezza/perimetro per l'utilizzo con ExpressRoute per Office 365 in conformità con le procedure consigliate per la ridondanza, la disponibilità elevata e il ripristino di emergenza.

Di seguito è riportato un esempio di Woodgrove Bank che confronta le diverse opzioni di connettività di ExpressRoute di Azure con i modelli di sicurezza perimetrale descritti in questo articolo.
  
### <a name="example-1-securing-azure-expressroute"></a>Esempio 1: protezione di ExpressRoute di Azure
  
La Woodgrove Bank sta prendendo in considerazione l'implementazione di Azure ExpressRoute e dopo aver pianificato l'architettura ottimale per il [routing con ExpressRoute per Office 365](routing-with-expressroute.md) e dopo aver utilizzato le linee guida sopra riportate per comprendere i requisiti di larghezza di banda, determinano il metodo migliore per la protezione del perimetro.
  
Per la Woodgrove, un'organizzazione multi-nazionale con posizioni in più continenti, la sicurezza deve coprire tutti i perimetri. L'opzione di connettività ottimale per la Woodgrove è una connessione a più punti con più posizioni di peering in tutto il mondo per soddisfare le esigenze dei propri dipendenti in ogni continente. Ogni continente include circuiti di ExpressRoute di Azure ridondanti all'interno del continente e la sicurezza deve essere esteso a tutti questi.
  
L'infrastruttura esistente di Woodgrove è affidabile e in grado di gestire il lavoro aggiuntivo, di conseguenza, la Woodgrove Bank è in grado di utilizzare l'infrastruttura per i propri ExpressRoute di Azure e la sicurezza perimetrale Internet. In caso contrario, la Woodgrove potrebbe scegliere di acquistare ulteriori apparecchiature per completare le apparecchiature esistenti o per gestire un diverso tipo di connessione.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Disponibilità elevata e failover con ExpressRoute di Azure
<a name="BKMK_high-availability"> </a>

È consigliabile eseguire il provisioning di almeno due circuiti attivi da ogni uscita con ExpressRoute al provider di ExpressRoute. Questo è il luogo più comune in cui viene visualizzato un errore per i clienti e si può facilmente evitarlo provisioning di una coppia di circuiti ExpressRoute attivi/attivi. È inoltre consigliabile disporre di almeno due circuiti Internet attivi/attivi perché molti servizi di Office 365 sono disponibili solo su Internet.
  
All'interno del punto di uscita della rete sono presenti molti altri dispositivi e circuiti che svolgono un ruolo critico nel modo in cui le persone percepiscono la disponibilità. Queste parti degli scenari di connettività non sono incluse in ExpressRoute o Office 365 SLA, ma svolgono un ruolo critico alla fine della disponibilità del servizio finale percepita dagli utenti dell'organizzazione.
  
Concentrarsi sulle persone che usano e gestiscono Office 365, se un errore di un componente potrebbe influire sull'esperienza dei popoli tramite il servizio, cercare modi per limitare la percentuale totale di persone coinvolte. Se una modalità di failover è complessa dal punto di vista operativo, prendere in considerazione la possibilità di eseguire il ripristino di un periodo di tempo prolungato e cercare modalità di failover operative in modo semplice e automatizzato.
  
All'esterno della rete, Office 365, ExpressRoute e il provider di ExpressRoute dispongono di diversi livelli di disponibilità.
  
### <a name="service-availability"></a>Disponibilità del servizio
  
- I servizi di Office 365 sono coperti da [contratti di servizio](https://technet.microsoft.com/library/office-365-service-level-agreement.aspx)ben definiti, tra cui il tempo di attività e la metrica di disponibilità per i singoli servizi. Uno dei motivi per cui Office 365 è in grado di mantenere livelli elevati di disponibilità del servizio è la possibilità per i singoli componenti di eseguire il failover senza problemi tra i numerosi datacenter Microsoft, utilizzando la rete globale di Microsoft. Questo failover si estende dal datacenter e dalla rete ai punti di uscita Internet multipli e consente il failover senza problemi dal punto di vista delle persone che usano il servizio.

- ExpressRoute [fornisce un contratto](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) di servizio di disponibilità del 99,9% su singoli circuiti dedicati tra Microsoft Network Edge e il provider di ExpressRoute o l'infrastruttura del partner. Tali livelli di servizio vengono applicati a livello di circuito di ExpressRoute, che è costituito da [due interconnessioni indipendenti](https://azure.microsoft.com/documentation/articles/expressroute-introduction/) tra le apparecchiature Microsoft ridondanti e le apparecchiature dei provider di rete in ogni posizione di peering.

### <a name="provider-availability"></a>Disponibilità del provider
  
- Le modalità di servizio di Microsoft si arrestano presso il provider o partner di ExpressRoute. Questo è anche il primo luogo in cui è possibile effettuare scelte che influiscono sul livello di disponibilità. È consigliabile valutare attentamente le caratteristiche di architettura, disponibilità e resilienza offerte dal provider di ExpressRoute tra il perimetro della rete e la connessione dei provider in ogni posizione di peering Microsoft. Prestare particolare attenzione agli aspetti logici e fisici della ridondanza, dell'equipaggiamento di peering, dei circuiti WAN forniti dal vettore e di qualsiasi altro valore aggiuntivo, ad esempio i servizi NAT o i firewall gestiti.

### <a name="designing-your-availability-plan"></a>Progettare il piano di disponibilità
  
Si consiglia vivamente di pianificare e progettare la disponibilità elevata e la resilienza negli scenari di connettività end-to-end per Office 365. Una progettazione deve includere;
  
- nessun singolo punto di errore, compresi i circuiti Internet e ExpressRoute.

- ridurre al minimo il numero di persone interessate e la durata di tale impatto per la maggior parte delle modalità di errore previste.

- ottimizzazione per il processo di ripristino semplice, ripetibile e automatico dalla maggior parte delle modalità di errore previste.

- supporto delle richieste complete del traffico di rete e della funzionalità tramite percorsi ridondanti, senza degrado sostanziale.

Gli scenari di connettività devono includere una topologia di rete ottimizzata per più percorsi di rete indipendenti e attivi in Office 365. In questo modo si otterrà una maggiore disponibilità end-to-end rispetto a una topologia ottimizzata solo per la ridondanza a livello di singolo dispositivo o equipaggiamento.
  
> [!TIP]
> Se gli utenti sono distribuiti in più continenti o aree geografiche e ognuno di questi percorsi si connette a circuiti WAN ridondanti in un singolo percorso locale in cui si trova un singolo circuito ExpressRoute, gli utenti sperimenteranno meno disponibilità del servizio end-to-end rispetto a una progettazione della topologia di rete che include circuiti ExpressRoute indipendenti che collegano le diverse aree alla posizione di peering più vicina.
  
È consigliabile eseguire il provisioning di almeno due circuiti di ExpressRoute con ogni circuito connesso a una posizione peer geografica diversa. È necessario eseguire il provisioning di questa coppia attiva di circuiti per ogni area geografica in cui gli utenti utilizzeranno la connettività di ExpressRoute per i servizi di Office 365. In questo modo ogni area rimarrà connessa durante una situazione di emergenza che influisce su una posizione principale, ad esempio un centro dati o un percorso di peering. La configurazione in attivo/attivo consente la distribuzione del traffico degli utenti finali su più percorsi di rete. Questo riduce l'ambito delle persone coinvolte durante interruzioni del dispositivo o delle apparecchiature di rete.
  
Non è consigliabile utilizzare un singolo circuito di ExpressRoute con Internet come backup.
  
### <a name="example-2-failover-and-high-availability"></a>Esempio 2: failover e disponibilità elevata
  
La progettazione geografica di Woodgrove Bank è stata sottoposta a una revisione del routing, della larghezza di banda, della sicurezza e ora deve passare a una revisione a disponibilità elevata. La Woodgrove pensa alla disponibilità elevata, in quanto copre tre categorie; resilienza, affidabilità e ridondanza.
  
La resilienza consente alla Woodgrove di recuperare rapidamente gli errori. L'affidabilità consente a Woodgrove di offrire un risultato coerente all'interno del sistema. La ridondanza consente alla Woodgrove di spostarsi tra una o più istanze di infrastruttura con mirroring.
  
All'interno di ogni configurazione perimetrale, la Woodgrove dispone di firewall, proxy e ID ridondanti. Per il Nord America, la Woodgrove ha una configurazione perimetrale nel datacenter di Dallas e un'altra configurazione perimetrale nel Data Center di Virginia. Le apparecchiature ridondanti in ogni posizione offrono resilienza a tale percorso.
  
La configurazione di rete di Woodgrove Bank è basata su alcuni principi fondamentali:
  
- All'interno di ogni area geografica sono presenti più circuiti di ExpressRoute di Azure.

- Ogni circuito all'interno di un'area è in grado di supportare tutto il traffico di rete all'interno di tale area.

- Il routing preferirà chiaramente uno o l'altro percorso a seconda della disponibilità, della posizione e così via.

- Il failover tra i circuiti di ExpressRoute di Azure avviene automaticamente senza ulteriori configurazioni o azioni richieste dalla Woodgrove.

- Il failover tra circuiti Internet avviene automaticamente senza ulteriori configurazioni o azioni richieste dalla Woodgrove.

In questa configurazione, con la ridondanza a livello fisico e virtuale, la Woodgrove Bank è in grado di offrire resilienza locale, resilienza regionale e resilienza globale in modo affidabile. La Woodgrove ha eletto questa configurazione dopo aver valutato un singolo circuito di ExpressRoute di Azure per ogni area e la possibilità di eseguire il failover su Internet.
  
Se la Woodgrove non è in grado di disporre di più circuiti di ExpressRoute di Azure per ogni area geografica, il traffico proveniente dal Nord America al circuito ExpressRoute di Azure in Asia Pacifico aggiunge un livello di latenza inaccettabile e la configurazione del forwarder DNS necessario aggiunge la complessità.
  
L'utilizzo di Internet come configurazione di backup non è consigliato. In questo modo si interrompe il principio di affidabilità di Woodgrove, con una conseguente esperienza di connessione. Inoltre, la configurazione manuale sarebbe necessaria per il failover considerando gli annunci BGP che sono stati configurati, la configurazione NAT, la configurazione DNS e la configurazione del proxy. L'aggiunta di questa complessità di failover aumenta il tempo necessario per il ripristino e la riduzione della capacità di diagnosticare e risolvere i problemi relativi ai passaggi.
  
Sono ancora richieste informazioni su come pianificare e implementare la gestione del traffico o ExpressRoute di Azure? Leggere le altre [linee guida per la rete e le prestazioni](https://aka.ms/tune) o le [domande frequenti su ExpressRoute di Azure](https://azure.microsoft.com/documentation/articles/expressroute-faqs/).
  
## <a name="working-with-azure-expressroute-providers"></a>Utilizzo dei provider di ExpressRoute di Azure
<a name="BKMK_high-availability"> </a>

Scegliere le posizioni dei circuiti in base alla larghezza di banda, alla latenza, alla sicurezza e alla pianificazione della disponibilità elevata. Dopo aver conosciuto le posizioni ottimali che si desidera inserire nei circuiti, [esaminare l'elenco corrente dei provider in base all'area geografica](https://azure.microsoft.com/documentation/articles/expressroute-locations/).
  
Collaborare con il provider o i provider per selezionare le opzioni di connettività migliori, punto-punto, multi-punto o ospitate. Tenere presente che è possibile combinare le opzioni di connettività fino a quando la larghezza di banda e gli altri componenti ridondanti supportano il routing e la struttura a disponibilità elevata.
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/planningexpressroute365](https://aka.ms/planningexpressroute365)
  
## <a name="related-topics"></a>Argomenti correlati
<a name="BKMK_high-availability"> </a>

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute per Office 365](azure-expressroute.md)
  
[Gestione di ExpressRoute per la connettività di Office 365](managing-expressroute-for-connectivity.md)
  
[Routing con ExpressRoute per Office 365](routing-with-expressroute.md)
  
[Implementazione di ExpressRoute per Office 365](implementing-expressroute.md)
  
[Utilizzo delle community BGP in ExpressRoute per gli scenari di Office 365](bgp-communities-in-expressroute.md)
  
[Qualità multimediale e prestazioni della connettività di rete in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Ottimizzazione della rete per Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute e QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flusso di chiamata con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)
  
[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)
  
[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Ottimizzazione delle prestazioni e della rete di Office 365](network-planning-and-performance.md)
  
[Domande frequenti sugli endpoint di Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
