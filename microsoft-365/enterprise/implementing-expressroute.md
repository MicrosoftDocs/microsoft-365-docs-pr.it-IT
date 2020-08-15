---
title: Implementazione di ExpressRoute per Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/5/2017
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
ms.assetid: 77735c9d-8b80-4d2f-890e-a8598547dea6
description: Informazioni su come implementare ExpressRoute per Office 365, che fornisce un percorso di routing alternativo a molti servizi di Office 365 con Internet.
ms.openlocfilehash: 767a99f3a27f30b7193fd0d0b8376ff4923daffb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691463"
---
# <a name="implementing-expressroute-for-office-365"></a>Implementazione di ExpressRoute per Office 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

ExpressRoute per Office 365 fornisce un percorso di routing alternativo a numerosi servizi Internet di Office 365. L'architettura di ExpressRoute per Office 365 si basa sulla pubblicità di prefissi IP pubblici dei servizi di Office 365 già accessibili tramite Internet nei circuiti ExpressRoute provisionati per la successiva ridistribuzione di tali prefissi IP nella rete. Con ExpressRoute è possibile abilitare efficacemente diversi percorsi di routing, tramite Internet e tramite ExpressRoute, per molti servizi di Office 365. Questo stato del routing sulla rete può rappresentare una modifica significativa del modo in cui è stata progettata la topologia di rete interna.
  
 **Stato:** Guida completa V2
  
È necessario pianificare attentamente l'implementazione di ExpressRoute per Office 365 per soddisfare la complessità della rete di routing disponibile tramite un circuito dedicato con route iniettate nella rete di base e in Internet. Se l'utente e il team non eseguono la pianificazione e il testing dettagliato in questa guida, è possibile che si verifichi un rischio intermittente o una perdita totale di connettività per i servizi di Office 365 quando è abilitato il circuito ExpressRoute.
  
Per eseguire correttamente l'implementazione, è necessario analizzare i requisiti dell'infrastruttura, esaminare dettagliatamente la valutazione e la progettazione della rete, pianificare attentamente la distribuzione in modalità a fasi e controllate e creare un piano dettagliato di verifica e convalida. Per un ambiente esteso e distribuito, non è raro vedere le implementazioni che si estendono per diversi mesi. Questa guida è stata progettata per facilitare la pianificazione in anticipo.
  
Le grandi distribuzioni con esito positivo possono richiedere sei mesi di pianificazione e spesso includono i membri del team di molte aree dell'organizzazione, inclusi gli amministratori di reti, firewall e server proxy, gli amministratori di Office 365, la sicurezza, il supporto per gli utenti finali, la gestione dei progetti e la sponsorizzazione esecutiva Gli investimenti nel processo di pianificazione riducono la probabilità che si verifichino errori di distribuzione che causano tempi di inattività o una risoluzione dei problemi complessa e costosa.
  
Prima di avviare questa guida all'implementazione, è prevedibile che i prerequisiti seguenti siano stati completati.
  
1. È stata completata una valutazione della rete per determinare se ExpressRoute è consigliato e approvato.

2. È stato selezionato un provider di servizi di rete di ExpressRoute. Sono disponibili informazioni dettagliate sui [partner di ExpressRoute e sulle posizioni di peering](https://azure.microsoft.com/documentation/articles/expressroute-locations/).

3. Sono già state lette e interpretate la [documentazione di ExpressRoute](https://azure.microsoft.com/documentation/services/expressroute/) e la rete interna è in grado di rispettare i prerequisiti ExpressRoute end to end.

4. Il team ha letto tutte le linee guida e la documentazione pubblica di [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365) , [https://aka.ms/ert](https://aka.ms/ert) e ha guardato la serie di [formazione di Azure ExpressRoute per Office 365](https://channel9.msdn.com/series/aer) sul canale 9 per acquisire una conoscenza dei dettagli tecnici critici, tra cui:

      - Dipendenze Internet dei servizi SaaS.

      - Come evitare rotte asimmetriche e gestire il routing complesso.

      - Informazioni su come incorporare i controlli a livello di sicurezza, disponibilità e applicazione del perimetro.

## <a name="begin-by-gathering-requirements"></a>Iniziare con la raccolta dei requisiti
<a name="requirements"> </a>

Iniziare determinando le funzionalità e i servizi che si intende adottare all'interno dell'organizzazione. È necessario determinare quali funzionalità dei diversi servizi di Office 365 verranno utilizzate e quali posizioni della rete ospiteranno gli utenti che utilizzano tali funzionalità. Con il catalogo degli scenari, è necessario aggiungere gli attributi di rete necessari per ognuno di questi scenari. ad esempio flussi di traffico di rete in ingresso e in uscita e se gli endpoint di Office 365 sono disponibili su ExpressRoute oppure no.
  
Per raccogliere i requisiti dell'organizzazione:
  
- Catalogare il traffico di rete in ingresso e in uscita per i servizi di Office 365 che l'organizzazione sta utilizzando. Consultare la pagina degli URL e degli intervalli di indirizzi IP di Office 365 per la descrizione dei flussi necessari per diversi scenari di Office 365.

- Raccogliere la documentazione relativa alla topologia di rete esistente che mostra i dettagli relativi alla backbone e alla topologia WAN interna, alla connettività dei siti satellite, alla connettività degli utenti di Mile, al routing ai punti di uscita perimetrali di rete e ai servizi proxy.

  - Identificare gli endpoint dei servizi in ingresso nei diagrammi di rete a cui si connetterà Office 365 e altri servizi Microsoft, mostrando sia Internet che i percorsi di connessione di ExpressRoute proposti.

  - Identificare tutte le posizioni degli utenti geografici e la connettività WAN tra i percorsi insieme a quali posizioni sono attualmente in uscita su Internet e quali posizioni vengono proposte per avere un'uscita per una posizione di peering di ExpressRoute.

  - Identificare tutti i dispositivi perimetrali, ad esempio proxy, firewall e così via, e catalogare la relazione con i flussi in corso su Internet e ExpressRoute.

  - Documentare se gli utenti finali avranno accesso ai servizi di Office 365 tramite routing diretto o proxy di applicazione indiretta per flussi Internet e ExpressRoute.

- Aggiungere il percorso del tenant e dei percorsi Meet-me al diagramma di rete.

- Stimare le caratteristiche di latenza e prestazioni di rete attese e osservate dalle principali posizioni degli utenti a Office 365. Tenere presente che Office 365 è un insieme di servizi globale e distribuito e che gli utenti si connettono a percorsi che possono essere diversi dalla posizione del tenant. Per questo motivo, è consigliabile misurare e ottimizzare la latenza tra l'utente e il perimetro più vicino della rete globale Microsoft su ExpressRoute e sulle connessioni Internet. È possibile utilizzare i risultati della valutazione della rete per agevolare questa attività.

- Elencare i requisiti di sicurezza della rete aziendale e di disponibilità elevata che devono essere soddisfatti con la nuova connessione di ExpressRoute. Ad esempio, in che modo gli utenti continuano ad accedere a Office 365 nel caso di un errore del circuito ExpressRoute o di uscita Internet.

- Documentare quali flussi di rete di Office 365 in ingresso e in uscita utilizzerà il percorso Internet e che utilizzerà ExpressRoute. Le specifiche delle posizioni geografiche degli utenti e i dettagli della topologia di rete locale possono richiedere che il piano sia diverso da un percorso utente a un altro.

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a>Catalogare il traffico di rete in uscita e in ingresso
<a name="trafficCatalog"> </a>

Per ridurre al minimo il routing e altre complessità di rete, si consiglia di utilizzare solo ExpressRoute per Office 365 per i flussi di traffico di rete necessari per eseguire una connessione dedicata a causa di requisiti normativi o come risultato della valutazione della rete. Inoltre, si consiglia di eseguire il routing di ExpressRoute e l'approccio in uscita e il traffico di rete in ingresso scorre come fasi diverse e distinte del progetto di implementazione. Distribuire ExpressRoute per Office 365 solo per i flussi di traffico di rete in uscita avviati dall'utente e lasciare flussi di traffico di rete in ingresso su Internet può contribuire a controllare l'aumento della complessità topologica e i rischi di introdurre ulteriori possibilità di routing asimmetrico.
  
Il catalogo del traffico di rete deve contenere liste di tutte le connessioni di rete in ingresso e in uscita che sono disponibili tra la rete locale e Microsoft.
  
- I flussi del traffico di rete in uscita sono scenari in cui viene avviata una connessione dall'ambiente locale, ad esempio da client o server interni, con una destinazione dei servizi Microsoft. Queste connessioni possono essere dirette a Office 365 o indirettamente, ad esempio quando la connessione passa attraverso i server proxy, i firewall o altri dispositivi di rete nel percorso di Office 365.

- I flussi del traffico di rete in ingresso sono scenari in cui una connessione viene avviata dal cloud Microsoft a un host locale. In genere, queste connessioni devono passare attraverso il firewall e altre infrastrutture di sicurezza richieste dai criteri di sicurezza dei clienti per i flussi originati esternamente.

Leggere la **sezione garantire la simmetria del percorso** dell'articolo [routing con ExpressRoute per Office 365](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) per determinare quali servizi invieranno il traffico in ingresso e cercare la colonna contrassegnata **come ExpressRoute per Office 365** nell'articolo di riferimento per gli [endpoint di Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) per determinare le altre informazioni di connettività.
  
Per ogni servizio che richiede una connessione in uscita, è consigliabile descrivere la connettività pianificata per il servizio, tra cui il routing di rete, la configurazione del proxy, l'ispezione dei pacchetti e le esigenze di larghezza di banda.
  
Per ogni servizio che richiede una connessione in ingresso, sono necessarie ulteriori informazioni. I server nel cloud Microsoft consentiranno di stabilire le connessioni alla rete locale. per garantire il corretto funzionamento delle connessioni, è necessario descrivere tutti gli aspetti di questa connettività, tra cui: le voci DNS pubbliche per i servizi che accetteranno queste connessioni in ingresso, gli indirizzi IP IPv4 in formato CIDR, quali apparecchiature ISP sono coinvolte e la modalità di gestione di NAT in ingresso o NAT di origine per queste connessioni.
  
Le connessioni in ingresso devono essere esaminate indipendentemente dal fatto che si stiano connettendo su Internet o ExpressRoute per garantire che il routing asimmetrico non sia stato introdotto. In alcuni casi, gli endpoint locali che i servizi di Office 365 avviano le connessioni in ingresso potrebbero dover essere accessibili anche da altri servizi Microsoft e non Microsoft. È fondamentale che l'abilitazione del routing di ExpressRoute a questi servizi per gli scopi di Office 365 non interrompa altri scenari. In molti casi, i clienti potrebbero dover implementare specifiche modifiche alla propria rete interna, ad esempio NAT basata sull'origine, per garantire che i flussi in ingresso da Microsoft rimangano simmetrici dopo che è stato abilitato ExpressRoute.
  
Di seguito è indicato un esempio del livello di dettaglio necessario. In questo caso, l'ibrido di Exchange si instraderà al sistema locale su ExpressRoute.

|**Connection, proprietà**|**Valore**|
|:-----|:-----|
|**Direzione del traffico di rete** <br/> |Inbound  <br/> |
|**Servizio** <br/> |Ambiente Exchange ibrido  <br/> |
|**Office pubblico 365 endpoint (origine)** <br/> |Exchange Online (indirizzi IP)  <br/> |
|**Endpoint pubblico locale (destinazione)** <br/> |5.5.5.5  <br/> |
|**Voce DNS pubblica (Internet)** <br/> |Autodiscover.contoso.com  <br/> |
|**Questo endpoint locale verrà utilizzato per altri servizi Microsoft (non Office 365)** <br/> |No  <br/> |
|**Questo endpoint locale verrà utilizzato dagli utenti/sistemi su Internet** <br/> |Sì  <br/> |
|**Sistemi interni pubblicati tramite endpoint pubblici** <br/> |Ruolo di accesso client di Exchange Server (locale) 192.168.101, 192.168.102, 192.168.103  <br/> |
|**Annuncio IP dell'endpoint pubblico** <br/> |**A Internet**: 5.5.0.0/16  <br/> **A ExpressRoute**: 5.5.5.0/24  <br/> |
|**Controlli di sicurezza/perimetrale** <br/> |**Percorso Internet**: DeviceID_002  <br/> **Percorso ExpressRoute**: DeviceID_003  <br/> |
|**Disponibilità elevata** <br/> |Attivo/attivo in due spaziatura geografica ridondante  <br/> Circuiti di ExpressRoute-Chicago e Dallas  <br/> |
|**Controllo della simmetria del percorso** <br/> |**Metodo**: NAT di origine  <br/> **Percorso Internet**: connessioni NAT di origine in ingresso a 192.168.5.5  <br/> |**Percorso ExpressRoute**: connessioni NAT di origine a 192.168.1.0 (Chicago) e 192.168.2.0 (Dallas)  <br/> |

Ecco un esempio di un servizio in uscita solo:

|**Connection, proprietà**|**Valore**|
|:-----|:-----|
|**Direzione del traffico di rete** <br/> |In uscita  <br/> |
|**Servizio** <br/> |SharePoint Online  <br/> |
|**Endpoint locale (origine)** <br/> |Workstation utente  <br/> |
|**Office pubblico 365 endpoint (destinazione)** <br/> |SharePoint Online (indirizzi IP)  <br/> |
|**Voce DNS pubblica (Internet)** <br/> |\*. sharepoint.com (e FQDN aggiuntivi)  <br/> |
|**Riferimenti alla rete CDN** <br/> |cdn.sharepointonline.com (e altri FQDN)-indirizzi IP gestiti da provider della rete CDN)  <br/> |
|**Annuncio pubblicitario IP e NAT in uso** <br/> |**Percorso Internet/NAT di origine**: 1.1.1.0/24  <br/> **ExpressRoute Path/Source NAT**: 1.1.2.0/24 (Chicago) e 1.1.3.0/24 (Dallas)  <br/> |
|**Connectivity, metodo** <br/> |**Internet**: tramite proxy Layer 7 (file. PAC)  <br/> **ExpressRoute**: Direct routing (nessun proxy)  <br/> |
|**Controlli di sicurezza/perimetrale** <br/> |**Percorso Internet**: DeviceID_002  <br/> **Percorso ExpressRoute**: DeviceID_003  <br/> |
|**Disponibilità elevata** <br/> |**Percorso Internet**: uscita Internet ridondante  <br/> **Percorso ExpressRoute**: instradamento attivo/attivo ' Hot Potato ' in 2 circuiti ExpressRoute Geo-ridondanti-Chicago e Dallas  <br/> |
|**Controllo della simmetria del percorso** <br/> |**Metodo**: NAT di origine per tutte le connessioni  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a>Progettazione della topologia di rete con connettività regionale
<a name="topology"> </a>

Dopo aver compreso i servizi e i flussi di traffico di rete associati, è possibile creare un diagramma reticolare che incorpora questi nuovi requisiti di connettività e illustra le modifiche apportate per l'utilizzo di ExpressRoute per Office 365. Il diagramma deve includere:
  
1. Tutte le posizioni degli utenti a cui si accede a Office 365 e ad altri servizi.

2. Tutti i punti di uscita Internet e ExpressRoute.

3. Tutti i dispositivi in uscita e in ingresso che gestiscono la connettività all'interno e all'esterno della rete, inclusi router, firewall, server proxy di applicazione e rilevamento intrusione/prevenzione.

4. Destinazioni interne per tutto il traffico in ingresso, ad esempio i server ADFS interni che accettano connessioni dai server proxy dell'applicazione Web ADFS.

5. Catalogo di tutte le subnet IP che verranno pubblicizzate

6. Identificare ogni percorso in cui gli utenti accedono a Office 365 e elencano i percorsi Meet-me che verranno utilizzati per ExpressRoute.

7. Percorsi e parti della topologia di rete interna, in cui i prefissi di Microsoft IP appresi da ExpressRoute verranno accettati, filtrati e propagati.

8. La topologia di rete dovrebbe illustrare la posizione geografica di ogni segmento di rete e il modo in cui si connette alla rete Microsoft tramite ExpressRoute e/o Internet.

Nel diagramma seguente vengono illustrate tutte le posizioni in cui gli utenti utilizzeranno Office 365 insieme agli annunci di routing in ingresso e in uscita a Office 365.
  
![Meet-me geografica regionale di ExpressRoute](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
Per il traffico in uscita, gli utenti accedono a Office 365 in uno dei tre modi seguenti:
  
1. Tramite una posizione di Meet-me in Nord America per gli utenti in California.

2. Tramite una location Meet-me a Hong Kong per gli utenti di Hong Kong.

3. Tramite Internet in Bangladesh dove sono presenti meno persone e non viene effettuato il provisioning di un circuito di ExpressRoute.

![Connessioni in uscita per il diagramma regionale](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
Analogamente, il traffico di rete in ingresso proveniente da Office 365 restituisce uno dei tre modi seguenti:
  
1. Tramite una posizione di Meet-me in Nord America per gli utenti in California.

2. Tramite una location Meet-me a Hong Kong per gli utenti di Hong Kong.

3. Tramite Internet in Bangladesh dove sono presenti meno persone e non viene effettuato il provisioning di un circuito di ExpressRoute.

![Connessioni in ingresso per il diagramma regionale](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a>Determinare il percorso di riunione appropriato

La selezione delle posizioni Meet-me, ovvero la posizione fisica in cui il circuito di ExpressRoute connette la rete alla rete Microsoft, è influenzata dai percorsi in cui gli utenti accedono a Office 365. Come offerta SaaS, Office 365 non funziona con il modello regionale IaaS o PaaS nello stesso modo in cui è Azure. Invece, Office 365 è un insieme distribuito di servizi di collaborazione, in cui gli utenti possono dover connettersi a endpoint su più datacenter e aree geografiche, che potrebbero non essere necessariamente nello stesso percorso o nell'area in cui è ospitato il tenant dell'utente.
  
Questo significa che la considerazione più importante da fare quando si selezionano le posizioni Meet-me per ExpressRoute per Office 365 è quella in cui le persone all'interno dell'organizzazione si connetteranno. La raccomandazione generale per la connettività ottimale di Office 365 è l'implementazione del routing, in modo che le richieste degli utenti ai servizi di Office 365 vengano distribuite nella rete Microsoft tramite il percorso di rete più breve, anche questo viene spesso definito "Hot Potato". Ad esempio, se la maggior parte degli utenti di Office 365 si trova in una o due posizioni, la selezione dei percorsi Meet-me che si trovano nelle immediate vicinanze del percorso di tali utenti creerà la struttura ottimale. Se l'azienda dispone di popolazioni di utenti di grandi dimensioni in molte aree geografiche diverse, è possibile prendere in considerazione la possibilità di disporre di più circuiti ExpressRoute e posizioni Meet-me. Per alcune delle posizioni degli utenti, il percorso più breve/ottimale in Microsoft Network e Office 365, potrebbe non essere tramite la rete WAN interna e i punti di ExpressRoute Meet-me, ma tramite Internet.
  
Spesso, sono disponibili più posizioni Meet-me che possono essere selezionate all'interno di un'area con relativa vicinanza agli utenti. Compilare la tabella seguente per guidare le proprie decisioni.

|**Planned ExpressRoute Meet-me Locations in California e New York**||
|:-----|:-----|
|Posizione  <br/> |Numero di persone  <br/> |Latenza prevista per la rete Microsoft tramite l'uscita Internet  <br/> |Latenza prevista per Microsoft Network over ExpressRoute  <br/> |
|Roma  <br/> |10.000  <br/> |~ 15ms  <br/> |~ 10ms (tramite Silicon Valley)  <br/> |
|Washington D.C.  <br/> |15.000  <br/> |~ 20ms  <br/> |~ 10ms (via New York)  <br/> |
|Dallas  <br/> |5.000  <br/> |~ 15ms  <br/> |~ 40ms (via New York)  <br/> |

Una volta che l'architettura di rete globale che mostra l'area di Office 365, i percorsi Meet-me del provider di servizi di rete di ExpressRoute e la quantità di persone per località è stata sviluppata, può essere utilizzata per identificare se è possibile effettuare eventuali ottimizzazioni. Può anche mostrare connessioni di rete tornanti globali in cui le rotte del traffico in una posizione distante per ottenere la posizione Meet-me. Se viene individuato un tornante sulla rete globale, è necessario aggiornarlo prima di continuare. Trova un'altra posizione Meet-me oppure usa i punti di uscita di breakout Internet selettivi per evitare la tornante.
  
Nel primo diagramma viene illustrato un esempio di un cliente con due posizioni fisiche in Nord America. È possibile visualizzare le informazioni sui percorsi di Office, le posizioni tenant di Office 365 e diverse opzioni per le posizioni di ExpressRoute Meet-me. In questo esempio, il cliente ha selezionato la posizione Meet-me in base a due principi, nell'ordine indicato:
  
1. Prossimità più vicina alle persone nell'organizzazione.

2. Più vicino a un datacenter Microsoft in cui è ospitato Office 365.

![ExpressRoute US Geographic Meet-me](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
Espandendo questo concetto leggermente oltre, nel secondo diagramma viene mostrato un esempio di cliente multi-nazionale di fronte a informazioni e processi decisionali simili. Questo cliente ha un piccolo ufficio in Bangladesh con solo un piccolo team di dieci persone incentrato sulla crescita del proprio ingombro nella regione. Vi è una posizione Meet-me a Chennai e un datacenter Microsoft con Office 365 ospitato in Chennai quindi una posizione di Meet-me avrebbe senso; Tuttavia, per dieci persone, la spesa del circuito aggiuntivo è gravosa. Quando si guarda la rete, è necessario determinare se la latenza coinvolta nell'invio del traffico di rete in tutta la rete è più efficace rispetto alla spesa del capitale per acquisire un altro circuito di ExpressRoute.
  
In alternativa, le dieci persone in Bangladesh potrebbero ottenere prestazioni migliori con il traffico di rete inviato tramite Internet alla rete Microsoft piuttosto che instradarlo sulla rete interna, come mostrato nei diagrammi introduttivi e riprodotti di seguito.
  
![Connessioni in uscita per il diagramma regionale](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a>Creare il piano di implementazione di ExpressRoute per Office 365
<a name="implementation"> </a>

Il piano di implementazione deve comprendere sia i dettagli tecnici della configurazione di ExpressRoute, sia i dettagli della configurazione di tutte le altre infrastrutture della rete, ad esempio le seguenti.
  
- Pianificare i servizi suddivisi tra ExpressRoute e Internet.

- Pianificare la larghezza di banda, la sicurezza, la disponibilità elevata e il failover.

- Progettare il routing in ingresso e in uscita, incluse le ottimizzazioni del percorso di routing appropriate per le diverse posizioni

- Decidere in che modo i percorsi di ExpressRoute verranno pubblicizzati nella propria rete e qual è il meccanismo che consente ai client di selezionare il percorso Internet o ExpressRoute; ad esempio, Direct routing o proxy di applicazione.

- Pianificare le modifiche ai record DNS, incluse le voci del [Framework del criterio mittente](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx) .

- Pianificare la strategia NAT, inclusi i NAT in uscita e in ingresso.

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a>Pianificare il routing con percorsi di rete sia Internet che ExpressRoute
<a name="paths"> </a>

- Per la distribuzione iniziale, tutti i servizi in ingresso, come la posta elettronica in ingresso o la connettività ibrida, sono consigliati per l'utilizzo di Internet.

- Pianificare la distribuzione della rete LAN dei client degli utenti finali, ad esempio [la configurazione di un file PAC/WPAD, la](https://aka.ms/manageo365endpoints)route predefinita, i server proxy e gli annunci route BGP.

- Pianificare il routing perimetrale, inclusi i server proxy, i firewall e i proxy cloud.

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a>Pianificare la larghezza di banda, la sicurezza, la disponibilità elevata e il failover
<a name="availability"> </a>

Creare un piano per la larghezza di banda necessaria per ogni carico di lavoro principale di Office 365. Stimare separatamente i requisiti di larghezza di banda di Exchange Online, SharePoint Online e Skype for business online. È possibile utilizzare i calcolatori di stima che sono stati forniti per Exchange Online e Skype for business come punto di partenza. Tuttavia, è necessario un test pilota con un campione rappresentativo dei profili utente e delle posizioni per comprendere appieno le esigenze di larghezza di banda della propria organizzazione.
  
Aggiungere la modalità di gestione della sicurezza in ogni Internet e la posizione di uscita di ExpressRoute al piano, tenere presente che tutte le connessioni di ExpressRoute a Office 365 utilizzano il peering pubblico e devono essere ancora protette in conformità con i criteri di sicurezza aziendali connessi alla rete esterna.
  
Aggiungere dettagli al piano di cui le persone saranno intaccate dal tipo di interruzione e in che modo queste persone potranno svolgere il proprio lavoro a piena capacità nel modo più semplice.
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a>Pianificare i requisiti di larghezza di banda inclusi i requisiti di Skype for business su jitter, latenza, congestione e spazio di espansione
  
Skype for business online dispone anche di requisiti di rete aggiuntivi specifici descritti nell'articolo [qualità multimediale e prestazioni della connettività di rete in Skype for business online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).
  
Leggere la sezione **pianificazione della larghezza di banda per Azure ExpressRoute** nella [pianificazione della rete con ExpressRoute per Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
Quando si esegue una valutazione della larghezza di banda con gli utenti pilota, è possibile utilizzare la guida. [Ottimizzazione delle prestazioni di Office 365 utilizzando le linee di base e la cronologia delle prestazioni](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).
  
#### <a name="plan-for-high-availability-requirements"></a>Pianificare i requisiti di disponibilità elevata
  
Creare un piano per la disponibilità elevata per soddisfare le proprie esigenze e incorporarlo nel diagramma della topologia di rete aggiornato. Leggere la sezione **High Availability and failover with Azure ExpressRoute** in [Network Planning with ExpressRoute for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
#### <a name="plan-for-network-security-requirements"></a>Pianificare i requisiti di sicurezza di rete
  
Creare un piano per soddisfare i requisiti di sicurezza della rete e inserirlo nel diagramma della topologia di rete aggiornato. Leggere la sezione **Applying Security Controls to Azure ExpressRoute for office 365 Scenarios** in [Network Planning with ExpressRoute for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
### <a name="design-outbound-service-connectivity"></a>Progettare la connettività dei servizi in uscita
<a name="outbound"> </a>

ExpressRoute per Office 365 ha requisiti di rete in  *uscita*  che potrebbero non essere familiari. In particolare, gli indirizzi IP che rappresentano gli utenti e le reti a Office 365 e agiscono come endpoint di origine per le connessioni di rete in uscita a Microsoft devono seguire i requisiti specifici descritti di seguito.
  
1. Gli endpoint devono essere indirizzi IP pubblici, registrati alla propria azienda o al vettore che fornisce la connettività di ExpressRoute all'utente.

2. Gli endpoint devono essere annunciati a Microsoft e convalidati/accettati da ExpressRoute.

3. Gli endpoint non devono essere pubblicizzati su Internet con la stessa metrica di routing preferita.

4. Gli endpoint non devono essere utilizzati per la connettività ai servizi Microsoft che non sono configurati su ExpressRoute.

Se la struttura di rete non soddisfa questi requisiti, è possibile che gli utenti verifichino problemi di connettività a Office 365 e ad altri servizi Microsoft per instradare la foratura nera o il routing asimmetrico. Questo problema si verifica quando le richieste ai servizi Microsoft vengono instradate su ExpressRoute, ma le risposte vengono instradate di nuovo su Internet o viceversa e le risposte vengono rimosse dai dispositivi di rete con stato, ad esempio i firewall.
  
Il metodo più comune che è possibile utilizzare per soddisfare i requisiti di cui sopra è l'utilizzo di NAT di origine, implementato come parte della rete o fornito dal gestore di ExpressRoute. NAT di origine consente di astrarre i dettagli e l'indirizzamento IP privato della rete Internet da ExpressRoute e; insieme agli annunci di route IP corretti, fornire un meccanismo semplice per garantire la simmetria del percorso. Se si utilizzano dispositivi di rete con stato che sono specifici per le posizioni di peering di ExpressRoute, è necessario implementare pool NAT distinti per ogni peering di ExpressRoute per garantire la simmetria del percorso.
  
Per ulteriori informazioni, vedere i [requisiti NAT di ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-nat/).
  
Aggiungere le modifiche per la connettività in uscita al diagramma di topologia di rete.
  
### <a name="design-inbound-service-connectivity"></a>Progettare la connettività dei servizi in ingresso
<a name="inbound"> </a>

La maggior parte delle distribuzioni di Office 365 presuppone una qualche forma di connettività in ingresso da Office 365 ai servizi locali, ad esempio per gli scenari ibridi di Exchange, SharePoint e Skype for business, le migrazioni delle cassette postali e l'autenticazione tramite l'infrastruttura ADFS. Quando ExpressRoute si Abilita un ulteriore percorso di routing tra la rete locale e Microsoft per la connettività in uscita, queste connessioni in ingresso possono inavvertitamente influire sul routing asimmetrico, anche se si prevede di continuare a utilizzare Internet. Alcuni accorgimenti descritti di seguito sono consigliati per garantire che non vi siano effetti sui flussi in ingresso basati su Internet da Office 365 a sistemi locali.
  
Per ridurre al minimo i rischi del routing asimmetrico per i flussi del traffico di rete in ingresso, tutte le connessioni in ingresso devono utilizzare NAT di origine prima di essere instradate in segmenti della rete che dispongono di visibilità del routing in ExpressRoute. Se le connessioni in ingresso sono consentite su un segmento di rete con visibilità del routing in ExpressRoute senza NAT di origine, le richieste provenienti da Office 365 entreranno da Internet, ma la risposta che torna a Office 365 preferirà il percorso di rete di ExpressRoute alla rete Microsoft, causando il routing asimmetrico.
  
È possibile prendere in considerazione uno dei modelli di implementazione seguenti per soddisfare questo requisito:
  
1. Eseguire NAT di origine prima che le richieste vengano instradate nella rete interna utilizzando apparecchiature di rete, ad esempio firewall o di bilanciamento del carico, sul percorso da Internet ai sistemi locali.

2. Assicurarsi che le route di ExpressRoute non vengano propagate ai segmenti di rete in cui si trovano i servizi in ingresso, ad esempio i Front End Server o i sistemi proxy inversi, per la gestione delle connessioni Internet.

L'accounting esplicito di questi scenari nella rete e la conservazione di tutti i flussi del traffico di rete in ingresso su Internet consentono di ridurre al minimo la distribuzione e il rischio operativo del routing asimmetrico.
  
In alcuni casi, è possibile scegliere di indirizzare alcuni flussi in ingresso su connessioni ExpressRoute. Per questi scenari, tenere conto delle considerazioni aggiuntive seguenti.
  
1. Office 365 può solo individuare endpoint locali che utilizzano indirizzi IP pubblici. Ciò significa che, anche se l'endpoint in ingresso locale è esposto solo a Office 365 su ExpressRoute, è comunque necessario che sia associato a un IP pubblico.

2. La risoluzione dei nomi DNS che i servizi di Office 365 eseguono per risolvere gli endpoint locali avviene tramite DNS pubblico. Questo significa che è necessario registrare i mapping FQDN degli endpoint dei servizi in ingresso in Internet.

3. Per ricevere connessioni di rete in ingresso su ExpressRoute, le subnet IP pubbliche per tali endpoint devono essere pubblicizzate su Microsoft su ExpressRoute.

4. Valutare attentamente i flussi del traffico di rete in ingresso per garantire che vengano applicati ai controlli di rete e di sicurezza appropriati in base ai criteri di sicurezza e di rete dell'azienda.

5. Dopo che gli endpoint in ingresso locali sono stati annunciati a Microsoft su ExpressRoute, ExpressRoute diventerà effettivamente il percorso di routing preferito per tali endpoint per tutti i servizi Microsoft, tra cui Office 365. Questo significa che le subnet degli endpoint devono essere utilizzate solo per le comunicazioni con i servizi di Office 365 e nessun altro servizio sulla rete Microsoft. In caso contrario, la progettazione provocherà il routing asimmetrico, in cui le connessioni in ingresso da altri servizi Microsoft preferiscono instradare l'ingresso su ExpressRoute, mentre il percorso di ritorno utilizzerà Internet.

6. Nel caso in cui un circuito ExpressRoute o un percorso Meet-me sia inverso, è necessario assicurarsi che gli endpoint in ingresso locali siano ancora disponibili per accettare le richieste su un percorso di rete distinto. Ciò può significare subnet pubblicitarie per tali endpoint tramite più circuiti ExpressRoute.

7. È consigliabile applicare NAT di origine per tutti i flussi del traffico di rete in ingresso che entrano nella rete tramite ExpressRoute, soprattutto quando questi flussi interessano i dispositivi di rete, ad esempio i firewall.

8. Alcuni servizi locali, ad esempio il proxy ADFS o l'individuazione automatica di Exchange, possono ricevere richieste in ingresso da entrambi i servizi e gli utenti di Office 365 da Internet. Per queste richieste, Office 365 avrà lo stesso nome di dominio completo delle richieste degli utenti su Internet. La possibilità di utilizzare ExpressRoute per le connessioni degli utenti in ingresso da Internet a quegli endpoint locali, mentre la forzatura delle connessioni di Office 365, rappresenta una significativa complessità del routing. Per la vasta maggioranza dei clienti che implementano scenari complessi su ExpressRoute non è consigliabile a causa di considerazioni operative. Questo sovraccarico aggiuntivo include, gestendo i rischi del routing asimmetrico e richiede la gestione accurata degli annunci e dei criteri di routing su più dimensioni.

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a>Aggiornare il piano di topologia di rete per mostrare come evitare le rotte asimmetriche
<a name="asymmetric"> </a>

Si desidera evitare il routing asimmetrico per garantire che gli utenti dell'organizzazione possano utilizzare senza problemi Office 365 e altri servizi importanti su Internet. Sono disponibili due comuni configurazioni che causano il routing asimmetrico. Ora è un buon momento per esaminare la configurazione di rete che si sta pianificando di utilizzare e verificare se uno di questi scenari di routing asimmetrico potrebbe esistere.
  
Per iniziare, verranno esaminate alcune situazioni diverse associate al diagramma di rete seguente. In questo diagramma, tutti i server che ricevono richieste in ingresso, ad esempio ADFS o server ibridi locali, si trovano nel data center del New Jersey e sono pubblicizzati su Internet.
  
1. Anche se la rete perimetrale è sicura, non esiste alcuna NAT di origine disponibile per le richieste in arrivo.

2. I server del Data Center di New Jersey sono in grado di visualizzare sia le route Internet che quelle di ExpressRoute.

![Panoramica della connettività di ExpressRoute](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
Sono inoltre presenti suggerimenti su come correggerli.
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a>Problema 1: cloud alla connessione locale tramite Internet
  
Nel diagramma seguente viene illustrato il percorso di rete asimmetrico eseguito quando la configurazione di rete non fornisce NAT per le richieste in ingresso da Microsoft Cloud su Internet.
  
1. La richiesta in ingresso proveniente da Office 365 recupera l'indirizzo IP dell'endpoint locale da DNS pubblico e Invia la richiesta alla rete perimetrale.

2. In questa configurazione difettosa non è presente alcun NAT di origine configurato o disponibile nella rete perimetrale in cui il traffico viene inviato con l'indirizzo IP di origine effettivo utilizzato come destinazione di ritorno.

  - Il server della rete instrada il traffico di ritorno a Office 365 tramite una connessione di rete di ExpressRoute disponibile.

  - Il risultato è un percorso asimmetrico per il flusso a Office 365, causando una connessione interrotta.

![ExpressRoute asimmetrica del routing problema 1](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a>Soluzione 1a: NAT di origine
  
La semplice aggiunta di un NAT di origine alla richiesta in ingresso risolve questa rete non configurata in modo non configurato. In questo diagramma:
  
1. La richiesta in arrivo continua a essere introdotta attraverso la rete perimetrale del data center del New Jersey. Questa volta è disponibile NAT.

2. La risposta del server instrada verso l'IP associato al NAT di origine anziché all'indirizzo IP originale, causando la risposta che ritorna lungo lo stesso percorso di rete.

![Soluzione di routing asimmetrica ExpressRoute 1](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a>Soluzione 1B: instradare l'ambito
  
In alternativa, è possibile scegliere di non consentire l'annuncio dei prefissi di ExpressRoute BGP, rimuovendo il percorso di rete alternativo per tali computer. In questo diagramma:
  
1. La richiesta in arrivo continua a essere introdotta attraverso la rete perimetrale del data center del New Jersey. Questa volta i prefissi annunciati da Microsoft sul circuito di ExpressRoute non sono disponibili per il Data Center del New Jersey.

2. La risposta del server reindirizza verso l'IP associato all'indirizzo IP originale sull'unica route disponibile, causando la risposta che ritorna lungo lo stesso percorso di rete.

![Soluzione di routing di ExpressRoute asimmetrica 2](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a>Problema 2: Cloud to on-premises connection over ExpressRoute
  
Nel diagramma seguente viene illustrato il percorso di rete asimmetrico eseguito quando la configurazione di rete non fornisce NAT per le richieste in ingresso da Microsoft Cloud su ExpressRoute.
  
1. La richiesta in ingresso proveniente da Office 365 recupera l'indirizzo IP da DNS e Invia la richiesta alla rete perimetrale.

2. In questa configurazione difettosa non è presente alcun NAT di origine configurato o disponibile nella rete perimetrale in cui il traffico viene inviato con l'indirizzo IP di origine effettivo utilizzato come destinazione di ritorno.

  - Il computer della rete instrada il traffico di ritorno a Office 365 tramite una connessione di rete di ExpressRoute disponibile.

  - Il risultato è una connessione asimmetrica a Office 365.

![ExpressRoute asimmetrica routing problem 2](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a>Soluzione 2: NAT di origine
  
La semplice aggiunta di un NAT di origine alla richiesta in ingresso risolve questa rete non configurata in modo non configurato. In questo diagramma:
  
1. La richiesta in arrivo continua a essere introdotta attraverso la rete perimetrale di New York Data Center. Questa volta è disponibile NAT.

2. La risposta del server instrada verso l'IP associato al NAT di origine anziché all'indirizzo IP originale, causando la risposta che ritorna lungo lo stesso percorso di rete.

![Soluzione di routing ExpressRoute asimmetrica 3](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a>Documento verificare che la struttura di rete abbia una simmetria del percorso

A questo punto, è necessario verificare su carta che il piano di implementazione offra la simmetria del percorso per i diversi scenari in cui si utilizzerà Office 365. È possibile identificare la route di rete specifica che dovrebbe essere eseguita quando una persona utilizza diverse funzionalità del servizio. Dalla rete locale e il routing WAN, ai dispositivi perimetrali, al percorso di connettività; ExpressRoute o Internet e alla connessione all'endpoint online.
  
Sarà necessario eseguire questa operazione per tutti i servizi di rete di Office 365 precedentemente identificati come servizi adottati dall'organizzazione.
  
Questo foglio di lavoro consente di eseguire questa operazione tramite percorsi con una seconda persona. Spiegare loro dove ogni hop di rete dovrebbe ottenere la successiva route e assicurarsi di avere familiarità con i percorsi di routing. Tenere presente che ExpressRoute fornirà sempre una route con più ambiti agli indirizzi IP dei server Microsoft assegnando un costo del percorso più basso rispetto a una route predefinita Internet.
  
### <a name="design-client-connectivity-configuration"></a>Progettare la configurazione della connettività client
<a name="asymmetric"> </a>

![Utilizzo dei file PAC con ExpressRoute](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
Se si utilizza un server proxy per il traffico associato a Internet, è necessario modificare i file di configurazione del client o PAC per garantire che i computer client della rete siano configurati correttamente per inviare il traffico ExpressRoute desiderato a Office 365 senza transitare nel server proxy e che il traffico rimanente, incluso il traffico di Office 365, venga inviato al proxy pertinente. Leggere la guida sulla [gestione degli endpoint di Office 365](https://aka.ms/manageo365endpoints) , ad esempio i file PAC.
  
> [!NOTE]
> Gli endpoint cambiano spesso, tutte le volte che sono settimanalmente. È consigliabile apportare modifiche solo in base ai servizi e alle caratteristiche che l'organizzazione ha adottato per ridurre il numero di modifiche che è necessario apportare per rimanere aggiornate. Prestare particolare attenzione alla **Data di validità** del feed RSS in cui vengono annunciate le modifiche e viene mantenuto un record di tutte le modifiche passate, gli indirizzi IP annunciati non possono essere pubblicizzati o rimossi dall'annuncio, finché non viene raggiunta la data effettiva.
  
## <a name="build-your-deployment-and-testing-procedures"></a>Creare le procedure di distribuzione e testing
<a name="testing"> </a>

Il piano di implementazione deve includere sia la pianificazione del testing sia quella di rollback. Se l'implementazione non funziona come previsto, il piano dovrebbe essere progettato in modo da influenzare il minor numero di persone prima che vengano scoperti i problemi. Di seguito sono riportati alcuni principi di alto livello che il piano dovrebbe prendere in considerazione.
  
1. Eseguire la fase di onboarding del segmento di rete e del servizio utente per ridurre al minimo le interruzioni.

2. Pianificare il testing delle route con traceroute e TCP Connect da un host connesso a Internet separato.

3. Preferibilmente, il testing dei servizi in ingresso e in uscita dovrebbe essere effettuato su una rete di test isolata con un tenant di test Office 365.

      - In alternativa, il test può essere eseguito su una rete di produzione se il cliente non utilizza ancora Office 365 o è in fase di esecuzione.

      - In alternativa, il test può essere eseguito durante un'interruzione di produzione accantonata solo per il testing e il monitoraggio.

      - In alternativa, il test può essere effettuato controllando le route per ogni servizio su ogni nodo del router Layer 3. Questo rientro dovrebbe essere utilizzato solo se non è possibile eseguire altri test poiché la mancanza di test fisici introduce un rischio.

### <a name="build-your-deployment-procedures"></a>Creare le procedure di distribuzione

Le procedure di distribuzione devono essere distribuite a piccoli gruppi di persone in fasi che consentono di eseguire il test prima di eseguire la distribuzione in gruppi di persone di dimensioni maggiori. Di seguito sono riportati alcuni modi per eseguire la distribuzione di ExpressRoute.
  
1. Configurare ExpressRoute con Microsoft peering e fare in modo che gli annunci di route vengano inoltrati a un singolo host solo per scopi di test a fasi.

2. Pubblicizzare gli itinerari verso la rete ExpressRoute in un singolo segmento di rete e quindi espandere gli annunci instradati dal segmento di rete o dall'area geografica.

3. Se si distribuisce Office 365 per la prima volta, utilizzare la distribuzione di rete di ExpressRoute come pilota per un numero limitato di utenti.

4. Se si utilizzano i server proxy, è possibile configurare in alternativa un file PAC di test per indirizzare un numero limitato di utenti a ExpressRoute con test e commenti e suggerimenti prima di aggiungerne altri.

Il piano di implementazione deve elencare tutte le procedure di distribuzione che devono essere eseguite o i comandi che devono essere utilizzati per distribuire la configurazione di rete. Quando il tempo di interruzione della rete arriva tutte le modifiche apportate deve provenire dal piano di distribuzione scritto che è stato scritto in anticipo e peer reviewed. Consultare le indicazioni sulla configurazione tecnica di ExpressRoute.
  
- Aggiornamento dei record TXT SPF se sono stati modificati gli indirizzi IP di tutti i server locali che continueranno a inviare messaggi di posta elettronica.

- Aggiornamento di tutte le voci DNS per i server locali se sono stati modificati gli indirizzi IP per ospitare una nuova configurazione NAT.

- Assicurarsi di aver sottoscritto il feed RSS per le notifiche degli endpoint di Office 365 per gestire le configurazioni di routing o proxy.

Dopo aver completato la distribuzione di ExpressRoute, è necessario eseguire le procedure del piano di test. I risultati di ogni procedura devono essere registrati. È necessario includere le procedure per eseguire il rollback all'ambiente di produzione originale nel caso in cui i risultati del piano di test indichino che l'implementazione non ha avuto esito positivo.
  
### <a name="build-your-test-procedures"></a>Creare le procedure di test

Le procedure di testing devono includere i test per ogni servizio di rete in uscita e in ingresso per Office 365 entrambi che utilizzeranno ExpressRoute e quelli che non lo saranno. Le procedure devono includere il testing da ogni percorso di rete univoco, compresi gli utenti non locali nella LAN aziendale.
  
Di seguito sono riportati alcuni esempi di attività di test.
  
1. Eseguire il ping dal router locale al router dell'operatore di rete.

2. Convalidare gli annunci di indirizzi IP di 500 + Office 365 e CRM Online vengono ricevuti dal router locale.

3. Convalidare il NAT in ingresso e in uscita è in funzione tra ExpressRoute e la rete interna.

4. Verificare che le route verso il NAT vengano pubblicizzate dal router.

5. Verificare che ExpressRoute abbia accettato i prefissi annunciati.

      - Utilizzare il seguente cmdlet per verificare la presenza di annunci peering:

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. Convalidare l'intervallo IP pubblico NAT non è pubblicizzato a Microsoft tramite altri ExpressRoute o circuiti di rete Internet pubblici, a meno che non si tratta di un sottoinsieme specifico di un intervallo più esteso come nell'esempio precedente.

7. I circuiti di ExpressRoute sono associati, convalidare che entrambe le sessioni BGP sono in esecuzione.

8. Configurare un singolo host all'interno del NAT e utilizzare ping, tracert e tcpping per testare la connettività tra il nuovo circuito e l'host outlook.office365.com. In alternativa, è possibile utilizzare uno strumento come Wireshark o Microsoft Network Monitor 3,4 su una porta con mirroring per MSEE per convalidare la possibilità di connettersi all'indirizzo IP associato a outlook.office365.com.

9. Testare le funzionalità a livello di applicazione per Exchange Online.

  - Test Outlook è in grado di connettersi a Exchange Online e inviare/ricevere messaggi di posta elettronica.

  - Test Outlook è in grado di utilizzare la modalità online.

  - Testare la connettività di smartphone e la funzionalità di invio/ricezione.

10. Testare le funzionalità a livello di applicazione per SharePoint Online

  - Testare il client di sincronizzazione di OneDrive for business.

  - Test di SharePoint Online Web Access.

11. Testare le funzionalità a livello di applicazione per gli scenari di chiamata di Skype for business:

  - Join to Conference Call As Authenticated user [invite iniziato dall'utente finale].

  - Invitare un utente a una chiamata in conferenza [invito inviato da MCU].

  - Partecipare a una conferenza come utente anonimo utilizzando l'applicazione web Skype for business.

  - Chiamata di join dalla connessione del PC cablata, dal telefono IP e dal dispositivo mobile.

  - Chiamata a un utente federato o a una chiamata alla convalida PSTN: la chiamata è stata completata, la qualità delle chiamate è accettabile, il tempo di connessione è accettabile.

  - Verificare che lo stato di presenza dei contatti venga aggiornato per entrambi i membri del tenant e degli utenti federati.

### <a name="common-problems"></a>Problemi comuni

Il routing asimmetrico è il problema di implementazione più comune. Di seguito sono riportate alcune fonti comuni da cercare:
  
- Utilizzo di una topologia di routing di rete aperta o piana senza NAT di origine sul posto.

- L'utilizzo di SNAT non viene utilizzato per instradare i servizi in ingresso tramite le connessioni Internet e ExpressRoute.

- Non è possibile testare i servizi in ingresso su ExpressRoute in una rete di test prima di distribuirli in generale.

## <a name="deploying-expressroute-connectivity-through-your-network"></a>Distribuzione della connettività di ExpressRoute tramite la rete
<a name="testing"> </a>

Eseguire il passaggio della distribuzione a un segmento della rete alla volta, distribuendo progressivamente la connettività a diverse parti della rete con un piano per eseguire il rollback per ogni nuovo segmento di rete. Se la distribuzione è allineata a una distribuzione di Office 365, distribuire prima gli utenti pilota di Office 365 ed estenderli da qui.
  
In primo luogo per il test e quindi per la produzione:
  
- Eseguire la procedura di distribuzione per abilitare ExpressRoute.

- Verificare la visualizzazione delle route di rete come previsto.

- Eseguire il testing su ogni servizio in ingresso e in uscita.

- Rollback se si riscontrano problemi.

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a>Configurare una connessione di test a ExpressRoute con un segmento di rete di test

Dopo aver completato il piano su carta, è necessario eseguire il test su scala ridotta. In questo test si stabilirà una singola connessione di ExpressRoute con Microsoft peering a una subnet di prova sulla rete locale. È possibile configurare una [versione di valutazione di Office 365 tenant](https://go.microsoft.com/fwlink/p/?LinkID=403802) con connettività da e verso la subnet dei test e includere tutti i servizi in uscita e in ingresso che verranno utilizzati per la produzione nella subnet di test. Configurare il DNS per il segmento di rete di test e stabilire tutti i servizi in ingresso e in uscita. Eseguire il piano di test e assicurarsi di avere familiarità con il routing per ogni servizio e la propagazione della route.
  
### <a name="execute-the-deployment-and-test-plans"></a>Eseguire i piani di distribuzione e di testing

Dopo aver completato gli elementi descritti in precedenza, è necessario controllare le aree che sono state completate e verificare che l'utente e il team siano stati esaminati prima di eseguire i piani di distribuzione e testing.
  
- Elenco dei servizi in uscita e in ingresso coinvolti nella modifica della rete.

- Diagramma dell'architettura di rete globale che mostra sia l'uscita Internet sia le posizioni ExpressRoute Meet-me.

- Diagramma di distribuzione di rete in cui vengono illustrati i diversi percorsi di rete utilizzati per ogni servizio distribuito.

- Piano di distribuzione con passaggi per implementare le modifiche e il rollback, se necessario.

- Piano di testing per testare ogni Office 365 e il servizio di rete.

- Convalida cartacea completata delle route di produzione per i servizi in ingresso e in uscita.

- Un test completato su un segmento di rete di test, inclusi i test di disponibilità.

Scegliere una finestra di interruzione che sia sufficiente per l'esecuzione dell'intero piano di distribuzione e del piano di testing, che sia disponibile un certo tempo per la risoluzione dei problemi e per il rollback, se necessario.
  
> [!CAUTION]
> A causa della natura complessa del routing su Internet e ExpressRoute, è consigliabile aggiungere ulteriore tempo di buffer alla finestra per gestire la risoluzione dei problemi relativi al routing complesso.
  
### <a name="configure-qos-for-skype-for-business-online"></a>Configurare QoS per Skype for business online

La funzionalità QoS è necessaria per ottenere vantaggi per la riunione e la voce per Skype for business online. È possibile configurare QoS dopo aver garantito che la connessione di rete di ExpressRoute non blocchi gli altri accessi al servizio di Office 365. La configurazione per QoS è descritta nell'articolo [ExpressRoute e QoS in Skype for business online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) .
  
## <a name="troubleshooting-your-implementation"></a>Risoluzione dei problemi relativi all'implementazione
<a name="troubleshooting"> </a>

La prima cosa da vedere è la procedura descritta in questa guida all'implementazione, sono state perse nel piano di implementazione? Se possibile, è necessario eseguire ulteriori test di rete di piccole dimensioni per replicare l'errore e eseguirne il debug.
  
Identificare i servizi in ingresso o in uscita non riusciti durante il testing. Ottenere in modo specifico gli indirizzi IP e le subnet per ognuno dei servizi che hanno avuto esito negativo. Andare avanti e percorrere il diagramma della topologia di rete su carta e convalidare il routing. Convalidare in modo specifico il percorso in cui viene pubblicizzato il routing di ExpressRoute, verificare che il routing durante l'interruzione, se possibile con le tracce.
  
Eseguire PSPing con una traccia di rete per ogni endpoint del cliente e valutare gli indirizzi IP di origine e di destinazione per convalidare i risultati previsti. Eseguire Telnet a qualsiasi host di posta elettronica esposto sulla porta 25 e verificare che SNAT nasconda l'indirizzo IP di origine originale, se previsto.
  
Tenere presente che, durante la distribuzione di Office 365 con una connessione ExpressRoute, è necessario assicurarsi che sia la configurazione di rete per ExpressRoute sia stata progettata in modo ottimale e che siano stati ottimizzati anche gli altri componenti della rete, ad esempio i computer client. Oltre a utilizzare questa guida alla pianificazione per la risoluzione dei problemi che potrebbero essere stati persi, è stato anche scritto un [piano per la risoluzione dei problemi relativi alle prestazioni per Office 365](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c) .
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/implementexpressroute365](https://aka.ms/implementexpressroute365)
  
## <a name="related-topics"></a>Argomenti correlati

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute per Office 365](azure-expressroute.md)
  
[Gestione di ExpressRoute per la connettività di Office 365](managing-expressroute-for-connectivity.md)
  
[Routing con ExpressRoute per Office 365](routing-with-expressroute.md)
  
[Pianificazione della rete con ExpressRoute per Office 365](network-planning-with-expressroute.md)
  
[Utilizzo delle community BGP in ExpressRoute per gli scenari di Office 365](bgp-communities-in-expressroute.md)
  
[Qualità multimediale e prestazioni della connettività di rete in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Ottimizzazione della rete per Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute e QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flusso di chiamata con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)
  
[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)
  
[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Ottimizzazione delle prestazioni e della rete di Office 365](network-planning-and-performance.md)
