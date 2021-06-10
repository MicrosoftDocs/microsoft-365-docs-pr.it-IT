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
description: In questo articolo verranno apprese informazioni su Azure ExpressRoute per Office 365 e su come utilizzarlo per la pianificazione della rete.
ms.openlocfilehash: 440d4fafadd7e9b504dc4ffdac1123a2956ed798
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923577"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Pianificazione della rete con ExpressRoute per Office 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

ExpressRoute per Office 365 fornisce connettività di livello 3 tra la rete e i datacenter di Microsoft. I circuiti utilizzano gli annunci di route BGP (Border Gateway Protocol) dei server front-end Office 365 server front-end. Dal punto di vista dei dispositivi locali, quando devono selezionare il percorso TCP/IP corretto per Office 365, Azure ExpressRoute è visto come un'alternativa a Internet.
  
Azure ExpressRoute aggiunge un percorso diretto a un set specifico di funzionalità e servizi supportati offerti Office 365 server all'interno dei data center di Microsoft. Azure ExpressRoute non sostituisce la connettività Internet ai datacenter Microsoft o ai servizi Internet di base, ad esempio la risoluzione dei nomi di dominio. Azure ExpressRoute e i circuiti Internet devono essere protetti e ridondanti.
  
Nella tabella seguente vengono evidenziate alcune differenze tra le connessioni Internet e Azure ExpressRoute nel contesto di Office 365.

|**Differenze nella pianificazione della rete**|**Connessione di rete Internet**|**Connessione di rete ExpressRoute**|
|:-----|:-----|:-----|
| Accesso ai servizi Internet necessari, tra cui;  <br/>  Risoluzione dei nomi DNS  <br/>  Verifica della revoca del certificato  <br/>  Reti per la distribuzione di contenuti (CDN)  <br/> |Sì  <br/> |Le richieste all'infrastruttura DNS e/o rete CDN Microsoft potrebbero usare la rete ExpressRoute.  <br/> |
| Accesso ai Office 365, tra cui;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype for Business Online  <br/>  Office in un browser  <br/>  Office 365 Portale e autenticazione  <br/> |Sì, tutte le applicazioni e le funzionalità  <br/> |Sì, [applicazioni e funzionalità specifiche](./urls-and-ip-address-ranges.md) <br/> |
|Sicurezza locale nel perimetro.  <br/> |Sì  <br/> |Sì  <br/> |
|Pianificazione della disponibilità elevata.  <br/> |Failover a una connessione di rete Internet alternativa  <br/> |Failover a una connessione ExpressRoute alternativa  <br/> |
|Connessione diretta con un profilo di rete prevedibile.  <br/> |No  <br/> |Sì  <br/> |
|Connettività IPv6.  <br/> |Sì  <br/> |Sì  <br/> |

Espandi i titoli seguenti per altre indicazioni sulla pianificazione della rete. Abbiamo anche registrato una serie di [Azure ExpressRoute](https://channel9.msdn.com/series/aer) in 10 parti per Office 365 training che si approfondire.

## <a name="existing-azure-expressroute-customers"></a>Clienti di Azure ExpressRoute esistenti

Se si usa un circuito Azure ExpressRoute esistente e si desidera aggiungere connettività Office 365 in questo circuito, è consigliabile esaminare il numero di circuiti, le posizioni di uscita e le dimensioni dei circuiti per assicurarsi che soddisfino le esigenze dell'utilizzo di Office 365. La maggior parte dei clienti richiede larghezza di banda aggiuntiva e molti circuiti aggiuntivi.
  
Per abilitare l'accesso Office 365 tramite i circuiti Di Azure ExpressRoute esistenti, configurare i filtri di [route](/azure/expressroute/how-to-routefilter-portal) per garantire che i Office 365 siano accessibili.
  
La sottoscrizione di Azure ExpressRoute è incentrata sul cliente, ovvero le sottoscrizioni sono legate ai clienti. Come cliente, puoi avere più circuiti Azure ExpressRoute e accedere a molte risorse cloud Microsoft su tali circuiti. Ad esempio, è possibile scegliere di accedere a una macchina virtuale ospitata in Azure, a un tenant di test di Office 365 e a un tenant di produzione di Office 365 su una coppia di circuiti Di Azure ExpressRoute ridondanti.
  
In questa tabella vengono descritti i due tipi di relazioni di peering che è possibile scegliere di implementare nei circuiti.

|**Relazione di peering**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**Servizi** <br/> |IaaS: macchine virtuali di Azure  <br/> |PaaS: servizi pubblici di Azure  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Avvio della connessione**** <br/> |Da cliente a Microsoft  <br/> Microsoft-to-Customer  <br/> |Da cliente a Microsoft  <br/> Microsoft-to-Customer  <br/> |
|**Supporto QoS** <br/> |Nessun QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1</sup> QoS supporta Skype for Business solo in questo momento.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Pianificazione della larghezza di banda per Azure ExpressRoute

Ogni cliente Office 365 ha esigenze di larghezza di banda univoche a seconda del numero di persone in ogni posizione, della loro attività con ogni applicazione Office 365 e di altri fattori, ad esempio l'uso di attrezzature locali o ibride e configurazioni di sicurezza di rete.
  
La larghezza di banda insufficiente comporta congestione, ritrasmissioni di dati e ritardi imprevedibili. La presenza di una larghezza di banda troppo elevata comporta costi superflui. In una rete esistente, la larghezza di banda viene spesso indicata come percentuale in termini di quantità di spazio disponibile nel circuito. Avere il 10% di headroom può causare congestione e avere l'80% di headroom in genere significa costi superflui. Le allocazioni tipiche degli obiettivi di headroom sono dal 20% al 50%.
  
Per trovare il giusto livello di larghezza di banda, il meccanismo migliore è quello di testare il consumo di rete esistente. Questo è l'unico modo per ottenere una misura reale dell'utilizzo e delle esigenze, poiché ogni configurazione di rete e ogni applicazione sono in qualche modo uniche. Durante la misurazione è necessario prestare particolare attenzione al consumo totale di larghezza di banda, alla latenza e alla congestione TCP per comprendere le esigenze di rete.
  
Dopo aver calcolato una previsione che include tutte le applicazioni di rete, un Office 365 pilota con un piccolo gruppo che comprende i diversi profili delle persone dell'organizzazione per determinare l'utilizzo effettivo e utilizzare le due misurazioni per stimare la larghezza di banda necessaria per ogni sede. In caso di problemi di latenza o congestione TCP rilevati nei test, potrebbe essere necessario avvicinare l'uscita alle persone che usano Office 365 o rimuovere l'analisi di rete intensiva, ad esempio la decrittografia/ispezione SSL.
  
Tutti i nostri consigli sul tipo di elaborazione di rete consigliato si applicano sia ai circuiti ExpressRoute che a Internet. Lo stesso vale per il resto delle indicazioni sul sito di ottimizzazione [delle prestazioni.](./network-planning-and-performance.md)
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Applicazione dei controlli di sicurezza ad Azure ExpressRoute per Office 365 scenari

La protezione della connettività di Azure ExpressRoute inizia con gli stessi principi della protezione della connettività Internet. Molti clienti scelgono di distribuire controlli di rete e perimetrali lungo il percorso ExpressRoute che connette la rete locale a Office 365 e altri cloud Microsoft. Questi controlli possono includere firewall, proxy delle applicazioni, prevenzione della perdita di dati, rilevamento delle intrusioni, sistemi di prevenzione delle intrusioni e così via. In molti casi i clienti applicano diversi livelli di controlli al traffico avviato da locale verso Microsoft, rispetto al traffico avviato da Microsoft verso la rete locale del cliente, rispetto al traffico avviato da locale verso una destinazione Internet generale.
  
Ecco alcuni esempi di integrazione della sicurezza con il modello di connettività [ExpressRoute](/azure/expressroute/expressroute-connectivity-models) scelto per la distribuzione.

|**Opzione di integrazione ExpressRoute**|**Modello perimetrale di sicurezza di rete**|
|:-----|:-----|
|Percorso condiviso in un exchange cloud  <br/> |Installare una nuova infrastruttura di sicurezza/perimetro o sfruttare l'infrastruttura perimetrale esistente nella struttura di co-posizione in cui viene stabilita la connessione ExpressRoute.  <br/> Sfruttare la struttura di co-posizione esclusivamente per scopi di routing/interconnessione e back haul connections from co-location facility into the on-premises security/perimeter infrastructure.  <br/> |
|Point-to-Point Ethernet  <br/> |Terminare la connessione ExpressRoute point-to-point nella posizione dell'infrastruttura perimetrale/di sicurezza locale esistente.  <br/> Installare una nuova infrastruttura di sicurezza/perimetro specifica per il percorso ExpressRoute e terminare la connessione Point-to-Point in questa posizione.  <br/> |
|IPVPN qualsiasi  <br/> |Sfruttare un'infrastruttura di sicurezza/perimetro locale esistente in tutte le posizioni in uscita nell'IPVPN usato per ExpressRoute per la connettività Office 365 locale.  <br/> Hairpin l'IPVPN usato per ExpressRoute per Office 365 in posizioni locali specifiche designate per fungere da sicurezza/perimetro.  <br/> |

Alcuni provider di servizi offrono anche funzionalità di sicurezza/perimetro gestite come parte delle soluzioni di integrazione con Azure ExpressRoute.
  
Quando si prende in considerazione il posizionamento della topologia delle opzioni di rete/perimetro di sicurezza usate per ExpressRoute per le connessioni Office 365, di seguito sono riportate ulteriori considerazioni
  
- I controlli di rete/sicurezza di profondità e tipo possono influire sulle prestazioni e sulla scalabilità dell'Office 365'esperienza utente.

- I flussi in uscita (locale- Microsoft) e \> in ingresso \> (Microsoft- locale) [se abilitati] possono avere requisiti diversi. Queste sono probabilmente diverse da Quelle in uscita verso destinazioni Internet generiche.

- Office 365 requisiti per porte/protocolli e subnet IP necessarie sono gli stessi se il traffico viene instradato tramite ExpressRoute per Office 365 o tramite Internet.

- Il posizionamento topologico dei controlli di rete/sicurezza dei clienti determina la rete end-to-end finale finale tra l'utente e il servizio Office 365 e può avere un impatto sostanziale sulla latenza e sulla congestione della rete.

- I clienti sono invitati a progettare la topologia di sicurezza/perimetro da utilizzare con ExpressRoute per Office 365 in conformità alle procedure consigliate per la ridondanza, la disponibilità elevata e il ripristino di emergenza.

Ecco un esempio di Woodgrove Bank che confronta le diverse opzioni di connettività di Azure ExpressRoute con i modelli di sicurezza perimetrale descritti in precedenza.
  
### <a name="example-1-securing-azure-expressroute"></a>Esempio 1: Protezione di Azure ExpressRoute
  
Woodgrove Bank sta valutando l'implementazione di Azure ExpressRoute e dopo aver pianificare l'architettura ottimale per il routing con [ExpressRoute](routing-with-expressroute.md) per Office 365 e dopo aver utilizzato le indicazioni precedenti per comprendere i requisiti di larghezza di banda, stanno determinando il metodo migliore per proteggere il proprio perimetro.
  
Per Woodgrove, un'organizzazione multi-nazionale con sedi in più continenti, la sicurezza deve estendersi su tutti i perimetri. L'opzione di connettività ottimale per Woodgrove è una connessione a più punti con più posizioni di peering in tutto il mondo per soddisfare le esigenze dei dipendenti in ogni continente. Ogni continente include circuiti Di Azure ExpressRoute ridondanti all'interno del continente e la sicurezza deve estendersi su tutti questi circuiti.
  
L'infrastruttura esistente di Woodgrove è affidabile e può gestire il lavoro aggiuntivo, di conseguenza, la Woodgrove Bank è in grado di usare l'infrastruttura per azure ExpressRoute e la sicurezza perimetrale Internet. In caso contrario, Woodgrove potrebbe scegliere di acquistare attrezzature aggiuntive per integrare l'attrezzatura esistente o per gestire un tipo di connessione diverso.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Disponibilità elevata e failover con Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Ti consigliamo di eseguire il provisioning di almeno due circuiti attivi da ogni uscita con ExpressRoute al provider ExpressRoute. Questo è il luogo più comune in cui si verificano errori per i clienti ed è possibile evitarlo facilmente tramite il provisioning di una coppia di circuiti ExpressRoute attivi/attivi. È inoltre consigliabile utilizzare almeno due circuiti Internet attivi/attivi perché molti Office 365 sono disponibili solo su Internet.
  
All'interno del punto di uscita della rete sono presenti molti altri dispositivi e circuiti che svolgono un ruolo fondamentale nel modo in cui le persone percepiscono la disponibilità. Queste parti degli scenari di connettività non sono coperte dai contratti di servizio ExpressRoute o Office 365, ma svolgono un ruolo fondamentale nella disponibilità del servizio end-to-end, come percepito dagli utenti dell'organizzazione.
  
Concentrarsi sulle persone che usano e operano Office 365, se un errore di un componente influisce sull'esperienza delle persone che usano il servizio, cercare modi per limitare la percentuale totale di persone interessate. Se una modalità di failover è operativamente complessa, considerare l'esperienza degli utenti di un lungo periodo di tempo per il ripristino e cercare modalità di failover operative semplici e automatizzate.
  
All'esterno della rete, Office 365, ExpressRoute e il provider ExpressRoute hanno tutti livelli di disponibilità diversi.
  
### <a name="service-availability"></a>Disponibilità del servizio
  
- Office 365 servizi sono coperti da contratti di servizio ben [definiti,](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)che includono metriche di tempo di attività e disponibilità per i singoli servizi. Uno dei motivi Office 365 mantenere livelli di disponibilità del servizio così elevati è la possibilità per i singoli componenti di eseguire il failover senza problemi tra i numerosi datacenter Microsoft, utilizzando la rete Microsoft globale. Questo failover si estende dal datacenter e dalla rete a più punti di uscita internet e consente il failover senza problemi dal punto di vista degli utenti che usano il servizio.

- ExpressRoute fornisce un contratto di servizio per la disponibilità del [99,9%](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) su singoli circuiti dedicati tra Microsoft Network Edge e l'infrastruttura partner o provider ExpressRoute. Questi livelli di servizio vengono applicati a livello [](/azure/expressroute/expressroute-introduction) di circuito ExpressRoute, costituito da due interconnessioni indipendenti tra l'apparecchiatura Microsoft ridondante e l'attrezzatura del provider di rete in ogni posizione di peering.

### <a name="provider-availability"></a>Disponibilità provider
  
- Le disposizioni del livello di servizio di Microsoft si fermano presso il provider ExpressRoute o il partner. Questa è anche la prima posizione in cui è possibile effettuare scelte che influiranno sul livello di disponibilità. È consigliabile valutare attentamente le caratteristiche di architettura, disponibilità e resilienza offerte dal provider ExpressRoute tra il perimetro di rete e la connessione dei provider in ogni posizione di peering Microsoft. Prestare particolare attenzione agli aspetti logici e fisici della ridondanza, delle apparecchiature di peering, dei circuiti WAN forniti dal gestore telefonico e di qualsiasi altro valore aggiunto, ad esempio servizi NAT o firewall gestiti.

### <a name="designing-your-availability-plan"></a>Progettazione del piano di disponibilità
  
È consigliabile pianificare e progettare disponibilità elevata e resilienza negli scenari di connettività end-to-end per Office 365. Una progettazione deve includere;
  
- nessun singolo punto di errore, inclusi i circuiti Internet ed ExpressRoute.

- riducendo al minimo il numero di persone interessate e la durata dell'impatto per le modalità di errore più previste.

- ottimizzazione per il processo di ripristino semplice, ripetibile e automatico dalle modalità di errore più previste.

- supportando le richieste complete del traffico di rete e delle funzionalità tramite percorsi ridondanti, senza una riduzione sostanziale.

Gli scenari di connettività devono includere una topologia di rete ottimizzata per più percorsi di rete indipendenti e attivi da Office 365. Ciò consente di ottenere una migliore disponibilità end-to-end rispetto a una topologia ottimizzata solo per la ridondanza a livello di singolo dispositivo o attrezzatura.
  
> [!TIP]
> Se gli utenti sono distribuiti in più continenti o aree geografiche e ognuna di queste posizioni si connette tramite circuiti WAN ridondanti a un'unica posizione locale in cui si trova un singolo circuito ExpressRoute, gli utenti sperimenteranno una minore disponibilità del servizio end-to-end rispetto a una progettazione della topologia di rete che include circuiti ExpressRoute indipendenti che connettono le diverse aree alla posizione di peering più vicina.
  
È consigliabile eseguire il provisioning di almeno due circuiti ExpressRoute con ogni circuito a cui ci si connette con una posizione di peering geografica diversa. È consigliabile effettuare il provisioning di questa coppia attiva-attiva di circuiti per ogni area geografica in cui gli utenti useranno la connettività ExpressRoute per Office 365 servizi. Ciò consente a ogni area geografica di rimanere connessa durante un'emergenza che interessa una posizione principale, ad esempio un centro dati o una posizione di peering. Configurandoli come attivi/attivi, il traffico degli utenti finali può essere distribuito su più percorsi di rete. In questo modo si riduce l'ambito delle persone interessate durante le interruzioni del dispositivo o delle apparecchiature di rete.
  
Non è consigliabile usare un singolo circuito ExpressRoute con Internet come backup.
  
### <a name="example-2-failover-and-high-availability"></a>Esempio 2: failover e disponibilità elevata
  
La progettazione multi-geografica della Woodgrove Bank ha subito una revisione del routing, della larghezza di banda, della sicurezza e ora deve essere sottoposta a una revisione a disponibilità elevata. Woodgrove pensa alla disponibilità elevata come a tre categorie; resilienza, affidabilità e ridondanza.
  
La resilienza consente a Woodgrove di eseguire rapidamente il ripristino da errori. L'affidabilità consente a Woodgrove di offrire un risultato coerente all'interno del sistema. La ridondanza consente a Woodgrove di spostarsi tra una o più istanze con mirroring dell'infrastruttura.
  
All'interno di ogni configurazione perimetrale, Woodgrove dispone di firewall, proxy e IDS ridondanti. Per il Nord America, Woodgrove ha una configurazione perimetrale nel datacenter di Dallas e un'altra configurazione perimetrale nel datacenter della Virginia. L'attrezzatura ridondante in ogni posizione offre resilienza a tale posizione.
  
La configurazione di rete della Woodgrove Bank si basa su alcuni principi chiave:
  
- All'interno di ogni area geografica sono presenti più circuiti Azure ExpressRoute.

- Ogni circuito all'interno di un'area può supportare tutto il traffico di rete all'interno di tale area.

- Il routing preferirà chiaramente uno o l'altro percorso a seconda della disponibilità, della posizione e così via.

- Il failover tra circuiti Di Azure ExpressRoute avviene automaticamente senza ulteriori operazioni o configurazioni richieste da Woodgrove.

- Il failover tra circuiti Internet avviene automaticamente senza ulteriori operazioni o configurazioni richieste da Woodgrove.

In questa configurazione, con ridondanza a livello fisico e virtuale, la Woodgrove Bank è in grado di offrire resilienza locale, resilienza regionale e resilienza globale in modo affidabile. Woodgrove ha scelto questa configurazione dopo aver valutato un singolo circuito Azure ExpressRoute per ogni area geografica e la possibilità di eseguire il failover su Internet.
  
Se Woodgrove non è stato in grado di avere più circuiti Azure ExpressRoute per area geografica, il routing del traffico proveniente dal Nord America al circuito Azure ExpressRoute in Asia Pacifico aggiungerebbe un livello inaccettabile di latenza e la configurazione del server d'inoltro DNS necessaria aggiunge complessità.
  
Non è consigliabile utilizzare Internet come configurazione di backup. Ciò interrompe il principio di affidabilità di Woodgrove, determinando un'esperienza incoerente con la connessione. Inoltre, la configurazione manuale sarebbe necessaria per il failover considerando gli annunci BGP configurati, la configurazione NAT, la configurazione DNS e la configurazione proxy. Questa maggiore complessità del failover aumenta il tempo necessario per il ripristino e riduce la capacità di diagnosticare e risolvere i problemi relativi ai passaggi.
  
Hai ancora domande su come pianificare e implementare la gestione del traffico o Azure ExpressRoute? Leggere il resto delle linee guida [per la rete e le prestazioni](./network-planning-and-performance.md) o le domande frequenti su Azure [ExpressRoute.](/azure/expressroute/expressroute-faqs)
  
## <a name="working-with-azure-expressroute-providers"></a>Utilizzo dei provider di Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Scegliere le posizioni dei circuiti in base alla larghezza di banda, alla latenza, alla sicurezza e alla pianificazione della disponibilità elevata. Una volta che conosci le posizioni ottimali in cui desideri posizionare i circuiti, esamina [l'elenco corrente dei provider per area](/azure/expressroute/expressroute-locations)geografica.
  
Collaborare con il provider o i provider per selezionare le opzioni di connettività migliori, point-to-point, multi-point o ospitate. Tenere presente che è possibile combinare e abbinare le opzioni di connettività purché la larghezza di banda e altri componenti ridondanti supportino il routing e la progettazione a disponibilità elevata.
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>Argomenti correlati
<a name="BKMK_high-availability"> </a>

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute per Office 365](azure-expressroute.md)
  
[Gestione di ExpressRoute per la connettività di Office 365](managing-expressroute-for-connectivity.md)
  
[Routing con ExpressRoute per Office 365](routing-with-expressroute.md)
  
[Implementazione di ExpressRoute per Office 365](implementing-expressroute.md)
  
[Uso di community BGP in ExpressRoute per Office 365 scenari](bgp-communities-in-expressroute.md)
  
[Qualità multimediale e prestazioni della connettività di rete in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Ottimizzazione della rete per Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute e QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flusso di chiamata con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)
  
[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)
  
[Intervalli di indirizzi IP e URL di Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Ottimizzazione delle prestazioni e della rete di Office 365](network-planning-and-performance.md)
  
[Domande frequenti sugli endpoint di Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)