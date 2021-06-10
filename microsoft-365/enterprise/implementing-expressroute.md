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
description: Informazioni su come implementare ExpressRoute per Office 365, che fornisce un percorso di routing alternativo a molti servizi di Office 365 Internet.
ms.openlocfilehash: d75fe3a6dab4926babeef61fc14894566ff819b0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051367"
---
# <a name="implementing-expressroute-for-office-365"></a>Implementazione di ExpressRoute per Office 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

ExpressRoute per Office 365 fornisce un percorso di routing alternativo a molti servizi Office 365 Internet. L'architettura di ExpressRoute per Office 365 si basa sulla pubblicità di prefissi IP pubblici di servizi Office 365 già accessibili tramite Internet nei circuiti ExpressRoute di cui è stato effettuato il provisioning per la successiva ridistribuzione di tali prefissi IP nella rete. Con ExpressRoute è possibile abilitare in modo efficace diversi percorsi di routing, tramite Internet e tramite ExpressRoute, per molti Office 365 servizi. Questo stato di routing nella rete può rappresentare una modifica significativa alla modalità di progettazione della topologia di rete interna.
  
 **Stato:** Guida completa v2
  
È necessario pianificare con attenzione ExpressRoute per l'implementazione di Office 365 per soddisfare le complessità di rete di disponibilità del routing tramite un circuito dedicato con route iniettate nella rete principale e in Internet. Se l'utente e il team non eseguono la pianificazione e i test dettagliati in questa guida, esiste un rischio elevato che si verifichi intermittente o una perdita totale di connettività ai servizi Office 365 quando il circuito ExpressRoute è abilitato.
  
Per ottenere un'implementazione corretta, è necessario analizzare i requisiti dell'infrastruttura, esaminare la valutazione e la progettazione dettagliate della rete, pianificare attentamente l'implementazione in modo a fasi e controllato e creare un piano di convalida e test dettagliato. Per un ambiente distribuito di grandi dimensioni non è raro vedere le implementazioni che si estendono per diversi mesi. Questa guida è progettata per aiutarti a pianificare in anticipo.
  
Le distribuzioni con successo di grandi dimensioni possono richiedere sei mesi di pianificazione e spesso includono membri del team provenienti da molte aree dell'organizzazione, tra cui amministratori di rete, firewall e server proxy, amministratori di Office 365, sicurezza, supporto degli utenti finali, gestione dei progetti e sponsorizzazione esecutiva. L'investimento nel processo di pianificazione ridurrà la probabilità che si verifichino errori di distribuzione con conseguenti tempi di inattività o una risoluzione dei problemi complessa e costosa.
  
Prima di iniziare questa guida all'implementazione, è previsto che siano completati i prerequisiti seguenti.
  
1. È stata completata una valutazione della rete per determinare se ExpressRoute è consigliato e approvato.

2. È stato selezionato un provider di servizi di rete ExpressRoute. Informazioni dettagliate sui [partner ExpressRoute e sulle posizioni di peering.](/azure/expressroute/expressroute-locations)

3. Hai già letto e compreso la documentazione [di ExpressRoute](https://azure.microsoft.com/documentation/services/expressroute/) e la rete interna è in grado di soddisfare i prerequisiti di ExpressRoute end-to-end.

4. Il team ha letto tutte le indicazioni e la documentazione pubblica all'indirizzo , e ha seguito la serie Di formazione di [https://aka.ms/expressrouteoffice365](./azure-expressroute.md) [https://aka.ms/ert](https://aka.ms/ert) Azure [ExpressRoute per Office 365 su](https://channel9.msdn.com/series/aer) Channel 9 per acquisire una conoscenza dei dettagli tecnici critici, tra cui:

      - Dipendenze Internet dei servizi SaaS.

      - Come evitare le route asimmetriche e gestire il routing complesso.

      - Come incorporare i controlli di sicurezza, disponibilità e a livello di applicazione perimetrali.

## <a name="begin-by-gathering-requirements"></a>Iniziare raccogliendo i requisiti
<a name="requirements"> </a>

Iniziare determinando quali funzionalità e servizi si prevede di adottare all'interno dell'organizzazione. È necessario determinare quali funzionalità dei diversi servizi Office 365 verranno utilizzati e quali posizioni della rete ospiteranno gli utenti che utilizzano tali funzionalità. Con il catalogo di scenari, è necessario aggiungere gli attributi di rete richiesti da ognuno di questi scenari. ad esempio i flussi di traffico di rete in ingresso e in uscita e se gli endpoint Office 365 sono disponibili tramite ExpressRoute o meno.
  
Per raccogliere i requisiti dell'organizzazione:
  
- Catalogare il traffico di rete in ingresso e in uscita per Office 365 servizi di rete che l'organizzazione sta utilizzando. Consultare Office 365 url e intervalli di indirizzi IP per la descrizione dei flussi richiesti Office 365 diversi scenari.

- Raccogliere la documentazione della topologia di rete esistente che mostra i dettagli della backbone e della topologia WAN interna, la connettività dei siti satellite, la connettività utente dell'ultimo chilometro, il routing ai punti di uscita del perimetro della rete e i servizi proxy.

  - Identificare gli endpoint del servizio in ingresso nei diagrammi di rete a cui Office 365 e altri servizi Microsoft si connetteranno, mostrando sia i percorsi di connessione a Internet che i percorsi di connessione ExpressRoute proposti.

  - Identificare tutte le posizioni geografiche degli utenti e la connettività WAN tra le posizioni insieme a quali posizioni attualmente hanno un'uscita verso Internet e quali posizioni sono proposte per l'uscita a una posizione di peering ExpressRoute.

  - Identificare tutti i dispositivi perimetrali, ad esempio proxy, firewall e così via, e catalogare la relazione con i flussi che passano su Internet ed ExpressRoute.

  - Documentare se gli utenti finali accederanno Office 365 servizi tramite routing diretto o proxy di applicazione indiretto per i flussi Internet ed ExpressRoute.

- Aggiungere il percorso del tenant e dei percorsi meet-me al diagramma di rete.

- Stimare le prestazioni di rete previste e osservate e le caratteristiche di latenza dalle posizioni principali degli utenti a Office 365. Tieni presente che Office 365 è un set globale e distribuito di servizi e gli utenti si connetteranno a posizioni che potrebbero essere diverse dalla posizione del tenant. Per questo motivo, è consigliabile misurare e ottimizzare la latenza tra l'utente e il margine più vicino della rete globale Microsoft su ExpressRoute e connessioni Internet. Puoi usare i risultati della valutazione della rete per facilitare questa attività.

- Elencare i requisiti di sicurezza della rete aziendale e disponibilità elevata che devono essere soddisfatti con la nuova connessione ExpressRoute. Ad esempio, in che modo gli utenti continuano ad accedere a Office 365 in caso di uscita da Internet o errore del circuito ExpressRoute.

- Documentare quali flussi di rete Office 365 in ingresso e in uscita utilizzeranno il percorso Internet e che utilizzeranno ExpressRoute. Le specifiche delle posizioni geografiche degli utenti e i dettagli della topologia di rete locale potrebbero richiedere che il piano sia diverso da una posizione utente a un'altra.

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a>Catalogare il traffico di rete in ingresso e in uscita
<a name="trafficCatalog"> </a>

Per ridurre al minimo il routing e altre complessità di rete, è consigliabile usare ExpressRoute solo per Office 365 per i flussi di traffico di rete necessari per passare attraverso una connessione dedicata a causa di requisiti normativi o come risultato della valutazione della rete. Inoltre, è consigliabile impostare in fasi l'ambito del routing ExpressRoute e l'approccio ai flussi di traffico di rete in ingresso e in uscita come fasi diverse e distinte del progetto di implementazione. Distribuire ExpressRoute per Office 365 solo per i flussi di traffico di rete in uscita avviati dall'utente e lasciare i flussi di traffico di rete in ingresso su Internet può aiutare a controllare l'aumento della complessità topologica e dei rischi derivanti dall'introduzione di ulteriori possibilità di routing asimmetrico.
  
Il catalogo del traffico di rete deve contenere elenchi di tutte le connessioni di rete in ingresso e in uscita tra la rete locale e Microsoft.
  
- I flussi di traffico di rete in uscita sono scenari in cui viene avviata una connessione dall'ambiente locale, ad esempio da client o server interni, con una destinazione del servizi Microsoft. Queste connessioni possono essere dirette Office 365 o indirette, ad esempio quando la connessione passa attraverso server proxy, firewall o altri dispositivi di rete nel percorso di Office 365.

- I flussi di traffico di rete in ingresso sono tutti gli scenari in cui viene avviata una connessione dal cloud Microsoft a un host locale. Queste connessioni in genere devono passare attraverso il firewall e altre infrastrutture di sicurezza richieste dal criterio di sicurezza dei clienti per i flussi originati esternamente.

Leggere  la sezione Verifica della simmetria della route dell'articolo [Routing con ExpressRoute](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) per Office 365 per determinare quali servizi invieranno il traffico in ingresso e cercare la colonna **contrassegnata come ExpressRoute per Office 365** nell'articolo di riferimento sugli endpoint [di Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) per determinare il resto delle informazioni sulla connettività.
  
Per ogni servizio che richiede una connessione in uscita, è necessario descrivere la connettività pianificata per il servizio, inclusi il routing di rete, la configurazione proxy, l'ispezione dei pacchetti e le esigenze di larghezza di banda.
  
Per ogni servizio che richiede una connessione in ingresso, sono necessarie alcune informazioni aggiuntive. I server nel cloud Microsoft stabiliranno connessioni alla rete locale. per assicurarsi che le connessioni vengano effettuate correttamente, è necessario descrivere tutti gli aspetti di questa connettività, tra cui; le voci DNS pubbliche per i servizi che accetteranno queste connessioni in ingresso, gli indirizzi IP IPv4 formattati ciDR, le apparecchiature ISP coinvolte e la modalità di gestione del NAT in ingresso o nat di origine per queste connessioni.
  
Le connessioni in ingresso devono essere esaminate indipendentemente dal fatto che si connettono tramite Internet o ExpressRoute per garantire che il routing asimmetrico non sia stato introdotto. In alcuni casi, gli endpoint locali a cui i servizi Office 365 avviano connessioni in ingresso potrebbero dover essere accessibili anche da altri utenti Microsoft e non servizi Microsoft. È fondamentale che l'abilitazione del routing ExpressRoute a questi servizi Office 365 non interrompa altri scenari. In molti casi, i clienti potrebbero dover implementare modifiche specifiche alla propria rete interna, ad esempio NAT basato sull'origine, per garantire che i flussi in ingresso da Microsoft rimangano simmetrici dopo l'attivazione di ExpressRoute.
  
Ecco un esempio del livello di dettaglio necessario. In questo caso Exchange ibrido instraderebbe al sistema locale tramite ExpressRoute.

|**Connection, proprietà**|**Valore**|
|:-----|:-----|
|**Direzione del traffico di rete** <br/> |In ingresso  <br/> |
|**Servizio** <br/> |Ambiente Exchange ibrido  <br/> |
|**Endpoint Office 365 pubblico (origine)** <br/> |Exchange Online (indirizzi IP)  <br/> |
|**Endpoint locale pubblico (destinazione)** <br/> |5.5.5.5  <br/> |
|**Voce DNS pubblica (Internet)** <br/> |Autodiscover.contoso.com  <br/> |
|**Questo endpoint locale verrà usato da altri utenti (non Office 365) servizi Microsoft** <br/> |No  <br/> |
|**Questo endpoint locale verrà utilizzato da utenti/sistemi su Internet** <br/> |Sì  <br/> |
|**Sistemi interni pubblicati tramite endpoint pubblici** <br/> |Exchange Server ruolo accesso client (locale) 192.168.101, 192.168.102, 192.168.103  <br/> |
|**Annuncio IP dell'endpoint pubblico** <br/> |**A Internet**: 5.5.0.0/16  <br/> **To ExpressRoute**: 5.5.5.0/24  <br/> |
|**Controlli di sicurezza/perimetro** <br/> |**Percorso Internet**: DeviceID_002  <br/> **Percorso ExpressRoute**: DeviceID_003  <br/> |
|**Disponibilità elevata** <br/> |Attivo/Attivo su 2 con ridondanza geografica  <br/> Circuiti ExpressRoute - Chicago e Dallas  <br/> |
|**Controllo della simmetria del percorso** <br/> |**Metodo**: NAT di origine  <br/> **Internet path**: Source NAT inbound connections to 192.168.5.5  <br/> |**Percorso ExpressRoute**: connessioni NAT di origine a 192.168.1.0 (Chicago) e 192.168.2.0 (Dallas)  <br/> |

Ecco un esempio di servizio solo in uscita:

|**Connection, proprietà**|**Valore**|
|:-----|:-----|
|**Direzione del traffico di rete** <br/> |In uscita  <br/> |
|**Servizio** <br/> |SharePoint Online  <br/> |
|**Endpoint locale (origine)** <br/> |Workstation utente  <br/> |
|**Endpoint Office 365 pubblico (destinazione)** <br/> |SharePoint Online (indirizzi IP)  <br/> |
|**Voce DNS pubblica (Internet)** <br/> |\*.sharepoint.com (e FQDN aggiuntivi)  <br/> |
|**rete CDN Riferimenti** <br/> |cdn.sharepointonline.com (e FQDN aggiuntivi) - Indirizzi IP gestiti da rete CDN provider)  <br/> |
|**Annuncio IP e NAT in uso** <br/> |**Percorso Internet/NAT di origine**: 1.1.1.0/24  <br/> **Percorso ExpressRoute/NAT** di origine : 1.1.2.0/24 (Chicago) e 1.1.3.0/24 (Dallas)  <br/> |
|**Connectivity, metodo** <br/> |**Internet**: tramite proxy di livello 7 (file PAC)  <br/> **ExpressRoute**: instradamento diretto (senza proxy)  <br/> |
|**Controlli di sicurezza/perimetro** <br/> |**Percorso Internet**: DeviceID_002  <br/> **Percorso ExpressRoute**: DeviceID_003  <br/> |
|**Disponibilità elevata** <br/> |**Percorso Internet**: uscita Internet ridondante  <br/> **Percorso ExpressRoute**: routing attivo/attivo di "patata calda" tra 2 circuiti ExpressRoute con ridondanza geografica - Chicago e Dallas  <br/> |
|**Controllo della simmetria del percorso** <br/> |**Metodo**: NAT di origine per tutte le connessioni  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a>Progettazione della topologia di rete con connettività regionale
<a name="topology"> </a>

Dopo aver compreso i servizi e i flussi di traffico di rete associati, è possibile creare un diagramma di rete che incorpora questi nuovi requisiti di connettività e illustra le modifiche che verranno apportate per usare ExpressRoute per Office 365. Il diagramma deve includere:
  
1. Tutte le posizioni utente da Office 365 e altri servizi da cui sarà possibile accedere.

2. Tutti i punti di uscita di Internet ed ExpressRoute.

3. Tutti i dispositivi in uscita e in ingresso che gestiscono la connettività all'interno e all'esterno della rete, inclusi router, firewall, server proxy dell'applicazione e rilevamento/prevenzione delle intrusioni.

4. Destinazioni interne per tutto il traffico in ingresso, ad esempio i server ADFS interni che accettano connessioni dai server proxy dell'applicazione Web ADFS.

5. Catalogo di tutte le subnet IP che verranno annunciate

6. Identificare ogni posizione da cui gli utenti Office 365 da ed elencare le posizioni meet-me che verranno usate per ExpressRoute.

7. I percorsi e le parti della topologia di rete interna, in cui i prefissi IP Microsoft appresi da ExpressRoute verranno accettati, filtrati e propagati.

8. La topologia di rete deve illustrare la posizione geografica di ogni segmento di rete e il modo in cui si connette alla rete Microsoft tramite ExpressRoute e/o Internet.

Il diagramma seguente mostra ogni posizione in cui gli utenti Office 365 gli annunci di routing in ingresso e in uscita Office 365.
  
![ExpressRoute regional geographic meet-me](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
Per il traffico in uscita, gli utenti accedono Office 365 in uno dei tre modi seguenti:
  
1. Attraverso una sede di meet-me in Nord America per le persone in California.

2. Attraverso un luogo di incontro a Hong Kong per le persone a Hong Kong.

3. Attraverso Internet in Bangladesh, dove ci sono meno persone e nessun circuito ExpressRoute di cui è stato eseguito il provisioning.

![Connessioni in uscita per il diagramma regionale](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
Analogamente, il traffico di rete in ingresso Office 365 in uno dei tre modi seguenti:
  
1. Attraverso una sede di meet-me in Nord America per le persone in California.

2. Attraverso un luogo di incontro a Hong Kong per le persone a Hong Kong.

3. Attraverso Internet in Bangladesh, dove ci sono meno persone e nessun circuito ExpressRoute di cui è stato eseguito il provisioning.

![Connessioni in ingresso per il diagramma regionale](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a>Determinare la posizione di meet-me appropriata

La selezione delle posizioni meet-me, ovvero la posizione fisica da cui il circuito ExpressRoute connette la rete alla rete Microsoft, è influenzata dalle posizioni da cui gli utenti accederanno Office 365. Come offerta SaaS, Office 365 non opera nel modello regionale IaaS o PaaS nello stesso modo di Azure. Invece, Office 365 è un set distribuito di servizi di collaborazione, in cui gli utenti potrebbero dover connettersi agli endpoint tra più data center e aree geografiche, che potrebbero non essere necessariamente nella stessa posizione o area geografica in cui è ospitato il tenant dell'utente.
  
Ciò significa che la considerazione più importante da prendere quando si selezionano le posizioni meet-me per ExpressRoute per Office 365 è da dove si connetteranno gli utenti dell'organizzazione. La raccomandazione generale per una connettività Office 365 ottimale è implementare il routing, in modo che le richieste degli utenti ai servizi Office 365 vengano inviate nella rete Microsoft attraverso il percorso di rete più breve, anche questo viene spesso definito routing "hot-patata". Ad esempio, se la maggior parte degli utenti di Office 365 si trovano in una o due posizioni, la selezione delle posizioni meet-me che si trovano nella vicinanza più vicina alla posizione di tali utenti creerà la progettazione ottimale. Se la tua azienda ha una popolazione di utenti di grandi dimensioni in molte aree geografiche diverse, puoi prendere in considerazione la possibilità di avere più circuiti ExpressRoute e posizioni meet-me. Per alcune delle posizioni degli utenti, il percorso più breve/ottimale nella rete Microsoft e in Office 365 potrebbe non essere attraverso la rete WAN interna e i punti di incontro ExpressRoute, ma tramite Internet.
  
Spesso, ci sono più località di meet-me che possono essere selezionate all'interno di un'area con relativa prossimità agli utenti. Compila la tabella seguente per guidare le tue decisioni.

|**Sedi expressroute meet-me pianificate in California e New York**||
|:-----|:-----|
|Posizione  <br/> |Numero di persone  <br/> |Latenza prevista per la rete Microsoft in uscita da Internet  <br/> |Latenza prevista per la rete Microsoft su ExpressRoute  <br/> |
|Roma  <br/> |10.000  <br/> |~15 ms  <br/> |~10ms (tramite Silicon Valley)  <br/> |
|Washington DC  <br/> |15.000  <br/> |~20ms  <br/> |~10ms (tramite New York)  <br/> |
|Dallas  <br/> |5.000  <br/> |~15 ms  <br/> |~40ms (tramite New York)  <br/> |

Dopo aver sviluppato l'architettura di rete globale che mostra l'area di Office 365, le posizioni del provider di servizi di rete ExpressRoute e la quantità di persone in base alla posizione, possono essere usate per identificare se è possibile eseguire ottimizzazioni. Può anche mostrare connessioni di rete di hairpin globali in cui il traffico viene instradato a una posizione distante per ottenere la posizione di meet-me. Se viene individuato un hairpin nella rete globale, è necessario correggere il sistema prima di continuare. Trovare un'altra posizione di meet-me o usare punti di uscita di breakout Internet selettivi per evitare l'hairpin.
  
Il primo diagramma mostra un esempio di cliente con due posizioni fisiche in Nord America. È possibile visualizzare le informazioni sulle posizioni degli uffici, Office 365 tenant e diverse scelte per le posizioni meet-me di ExpressRoute. In questo esempio, il cliente ha selezionato la posizione meet-me in base a due principi, nell'ordine seguente:
  
1. Prossimità più vicina alle persone dell'organizzazione.

2. Più vicino a un datacenter Microsoft in cui Office 365 è ospitato.

![ExpressRoute US geographic meet-me](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
Espandendo leggermente ulteriormente questo concetto, il secondo diagramma mostra un esempio di cliente multi-nazionale di fronte a informazioni e decisioni simili. Questo cliente ha un piccolo ufficio in Bangladesh con solo un piccolo team di dieci persone che si è concentrato sulla crescita della propria impronta nella regione. C'è una posizione meet-me a Chennai e un datacenter Microsoft con Office 365 ospitato a Chennai in modo che una posizione di meet-me avrebbe senso; tuttavia, per dieci persone, il costo del circuito aggiuntivo è gravoso. Quando si osserva la rete, è necessario determinare se la latenza implicata nell'invio del traffico di rete attraverso la rete è più efficace che spendere il capitale per acquisire un altro circuito ExpressRoute.
  
In alternativa, le dieci persone in Bangladesh possono ottenere prestazioni migliori con il traffico di rete inviato tramite Internet alla rete Microsoft rispetto al routing sulla rete interna, come illustrato nei diagrammi introduttivi e riprodotti di seguito.
  
![Connessioni in uscita per il diagramma regionale](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a>Creare il piano di implementazione expressroute Office 365 distribuzione
<a name="implementation"> </a>

Il piano di implementazione deve comprendere sia i dettagli tecnici della configurazione di ExpressRoute che i dettagli della configurazione di tutta l'altra infrastruttura della rete, ad esempio:
  
- Pianificare i servizi suddivisi tra ExpressRoute e Internet.

- Pianificare larghezza di banda, sicurezza, disponibilità elevata e failover.

- Progettare il routing in ingresso e in uscita, incluse le ottimizzazioni corrette dei percorsi di routing per posizioni diverse

- Decidere fino a dove verranno annunciate le route ExpressRoute nella rete e qual è il meccanismo per i client per selezionare il percorso Internet o ExpressRoute; ad esempio, routing diretto o proxy dell'applicazione.

- Pianificare le modifiche ai record DNS, incluse [le voci di Sender Policy Framework.](../security/defender-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- Pianificare la strategia NAT tra cui NAT di origine in uscita e in ingresso.

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a>Pianificare il routing con percorsi di rete Sia Internet che ExpressRoute
<a name="paths"> </a>

- Per la distribuzione iniziale, tutti i servizi in ingresso, ad esempio la posta elettronica in ingresso o la connettività ibrida, sono consigliati per l'utilizzo di Internet.

- Pianificare il routing DELLAN client degli utenti finali, ad esempio la configurazione di un [file PAC/WPAD,](./managing-office-365-endpoints.md)una route predefinita, server proxy e annunci di route BGP.

- Pianificare il routing perimetrale, inclusi server proxy, firewall e proxy cloud.

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a>Pianificare la larghezza di banda, la sicurezza, la disponibilità elevata e il failover
<a name="availability"> </a>

Creare un piano per la larghezza di banda necessaria per ogni carico di lavoro Office 365 principale. Stimare separatamente Exchange Online, SharePoint Online e Skype for Business di larghezza di banda online. Puoi usare i calcolatori di stima forniti per Exchange Online e Skype for Business come punto di partenza; Tuttavia, è necessario un test pilota con un campione rappresentativo dei profili utente e delle posizioni per comprendere appieno le esigenze di larghezza di banda dell'organizzazione.
  
Aggiungi come viene gestita la sicurezza in ogni posizione di uscita di Internet e ExpressRoute al piano, ricorda tutte le connessioni ExpressRoute a Office 365 usa il peering pubblico e deve comunque essere protetta in conformità ai criteri di sicurezza aziendali per la connessione a reti esterne.
  
Aggiungere dettagli al piano sulle persone interessate dal tipo di interruzione e su come tali persone saranno in grado di eseguire il proprio lavoro a piena capacità nel modo più semplice.
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a>Pianificare i requisiti di larghezza di Skype for Business instabilità, latenza, congestione e headroom
  
Skype for Business Online ha anche specifici requisiti di rete aggiuntivi, che sono dettagliati nell'articolo Qualità multimediale e prestazioni della connettività di [rete in Skype for Business Online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).
  
Leggere la sezione **Pianificazione della larghezza di banda per Azure ExpressRoute** in Pianificazione della rete con [ExpressRoute per Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
Quando esegui una valutazione della larghezza di banda con gli utenti pilota, puoi usare la nostra guida; [Office 365 ottimizzazione delle prestazioni utilizzando le previsioni e la cronologia delle prestazioni.](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
  
#### <a name="plan-for-high-availability-requirements"></a>Pianificare i requisiti di disponibilità elevata
  
Creare un piano per la disponibilità elevata in base alle proprie esigenze e incorporarlo nel diagramma della topologia di rete aggiornato. Leggere la sezione **Disponibilità elevata e failover con Azure ExpressRoute** in Pianificazione della rete con [ExpressRoute per Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
#### <a name="plan-for-network-security-requirements"></a>Pianificare i requisiti di sicurezza di rete
  
Creare un piano per soddisfare i requisiti di sicurezza di rete e incorporarlo nel diagramma della topologia di rete aggiornato. Leggere la sezione Applicazione dei controlli di sicurezza ad **Azure ExpressRoute** per scenari Office 365 in Pianificazione della rete con [ExpressRoute per Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
### <a name="design-outbound-service-connectivity"></a>Progettare la connettività del servizio in uscita
<a name="outbound"> </a>

ExpressRoute per Office 365 *ha requisiti* di rete in uscita che potrebbero non essere familiari. In particolare, gli indirizzi IP che rappresentano gli utenti e le reti da Office 365 e agiscono come endpoint di origine per le connessioni di rete in uscita a Microsoft devono soddisfare requisiti specifici descritti di seguito.
  
1. Gli endpoint devono essere indirizzi IP pubblici, registrati nell'azienda o per l'operatore che fornisce la connettività ExpressRoute all'utente.

2. Gli endpoint devono essere annunciati a Microsoft e convalidati/accettati da ExpressRoute.

3. Gli endpoint non devono essere annunciati a Internet con la stessa o più metrica di routing preferita.

4. Gli endpoint non devono essere usati per la connettività servizi Microsoft che non sono configurati su ExpressRoute.

Se la progettazione della rete non soddisfa questi requisiti, esiste un rischio elevato per gli utenti che si verifichino errori di connettività a Office 365 e ad altri servizi Microsoft a causa dell'instradamento nero o del routing asimmetrico. Ciò si verifica quando le richieste di servizi Microsoft vengono instradati tramite ExpressRoute, ma le risposte vengono instradati attraverso Internet o viceversa e le risposte vengono eliminate da dispositivi di rete con stato, ad esempio firewall.
  
Il metodo più comune che puoi usare per soddisfare i requisiti precedenti è usare NAT di origine, implementato come parte della rete o fornito dall'operatore ExpressRoute. Source NAT consente di astrarre i dettagli e l'indirizzamento IP privato della rete Internet da ExpressRoute e; Insieme agli annunci di route IP adeguati, fornisce un meccanismo semplice per garantire la simmetria del percorso. Se si usano dispositivi di rete con stato specifici per le posizioni di peering ExpressRoute, è necessario implementare pool NAT separati per ogni peering ExpressRoute per garantire la simmetria del percorso.
  
Per ulteriori informazioni, [vedere Requisiti NAT expressRoute.](/azure/expressroute/expressroute-nat)
  
Aggiungere le modifiche per la connettività in uscita al diagramma della topologia di rete.
  
### <a name="design-inbound-service-connectivity"></a>Progettare la connettività dei servizi in ingresso
<a name="inbound"> </a>

La maggior parte delle distribuzioni di enterprise Office 365 presuppongono una qualche forma di connettività in ingresso da Office 365 ai servizi locali, ad esempio per gli scenari ibridi di Exchange, SharePoint e Skype for Business, le migrazioni delle cassette postali e l'autenticazione tramite l'infrastruttura ADFS. Quando ExpressRoute abilita un percorso di routing aggiuntivo tra la rete locale e Microsoft per la connettività in uscita, queste connessioni in ingresso potrebbero essere inavvertitamente influenzate dal routing asimmetrico, anche se si prevede che tali flussi continuino a utilizzare Internet. Alcune precauzioni descritte di seguito sono consigliate per garantire che non vi sia alcun impatto sui flussi in ingresso basati su Internet Office 365 ai sistemi locali.
  
Per ridurre al minimo i rischi del routing asimmetrico per i flussi di traffico di rete in ingresso, tutte le connessioni in ingresso devono usare NAT di origine prima di essere instradate in segmenti della rete con visibilità di routing in ExpressRoute. Se le connessioni in ingresso sono consentite su un segmento di rete con visibilità di routing in ExpressRoute senza NAT di origine, le richieste provenienti da Office 365 verranno inviate da Internet, ma la risposta che torna a Office 365 preferirà il percorso di rete ExpressRoute alla rete Microsoft, causando il routing asimmetrico.
  
È possibile prendere in considerazione uno dei modelli di implementazione seguenti per soddisfare questo requisito:
  
1. Eseguire NAT di origine prima che le richieste siano instradati nella rete interna utilizzando apparecchiature di rete come firewall o servizi di bilanciamento del carico nel percorso da Internet ai sistemi locali.

2. Assicurarsi che le route ExpressRoute non vengano propagate ai segmenti di rete in cui risiedono i servizi in ingresso, ad esempio i server front-end o i sistemi proxy inversi, che gestisce le connessioni Internet.

Tenere esplicitamente conto di questi scenari nella rete e mantenere tutto il traffico di rete in ingresso su Internet consente di ridurre al minimo i rischi operativi e di distribuzione del routing asimmetrico.
  
In alcuni casi è possibile scegliere di indirizzare alcuni flussi in ingresso sulle connessioni ExpressRoute. Per questi scenari, tenere conto delle considerazioni aggiuntive seguenti.
  
1. Office 365 possono essere utilizzati solo endpoint locali che usano IP pubblici. Ciò significa che anche se l'endpoint in ingresso locale è esposto solo a Office 365 tramite ExpressRoute, deve comunque avere un INDIRIZZO IP pubblico associato.

2. Tutta la risoluzione dei nomi DNS Office 365 dei servizi per risolvere gli endpoint locali avviene utilizzando DNS pubblico. Ciò significa che è necessario registrare il nome di dominio completo degli endpoint del servizio in ingresso nei mapping IP su Internet.

3. Per ricevere connessioni di rete in ingresso tramite ExpressRoute, le subnet IP pubbliche per questi endpoint devono essere annunciate a Microsoft tramite ExpressRoute.

4. Valutare attentamente questi flussi di traffico di rete in ingresso per assicurarsi che a essi siano applicati controlli di sicurezza e di rete adeguati in conformità con i criteri di sicurezza e di rete dell'azienda.

5. Una volta che gli endpoint in ingresso locali vengono annunciati a Microsoft tramite ExpressRoute, ExpressRoute diventerà effettivamente il percorso di routing preferito per tali endpoint per tutti i servizi Microsoft, incluso Office 365. Ciò significa che tali subnet endpoint devono essere utilizzate solo per le comunicazioni con Office 365 e nessun altro servizio nella rete Microsoft. In caso contrario, la progettazione causerà il routing asimmetrico in cui le connessioni in ingresso da altri servizi Microsoft preferiscono eseguire il routing in ingresso su ExpressRoute, mentre il percorso di ritorno utilizzerà Internet.

6. Nel caso in cui un circuito ExpressRoute o una posizione meet-me non sia disponibile, è necessario verificare che gli endpoint in ingresso locali siano ancora disponibili per accettare le richieste su un percorso di rete separato. Ciò può indicare subnet pubblicitarie per tali endpoint tramite più circuiti ExpressRoute.

7. È consigliabile applicare NAT di origine per tutti i flussi di traffico di rete in ingresso che entrano nella rete tramite ExpressRoute, soprattutto quando questi flussi attraversano dispositivi di rete con stato, ad esempio firewall.

8. Alcuni servizi locali, ad esempio il proxy ADFS o l'individuazione automatica Exchange, possono ricevere richieste in ingresso sia dai servizi Office 365 che dagli utenti da Internet. Per queste richieste Office 365 lo stesso FQDN delle richieste utente su Internet. Consentire le connessioni utente in ingresso da Internet a tali endpoint locali, forzando le connessioni Office 365 a usare ExpressRoute, rappresenta una notevole complessità di routing. Per la maggior parte dei clienti l'implementazione di scenari così complessi su ExpressRoute non è consigliata a causa di considerazioni operative. Questo sovraccarico aggiuntivo include la gestione dei rischi del routing asimmetrico e richiederà di gestire con attenzione gli annunci e i criteri di routing su più dimensioni.

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a>Aggiornare il piano della topologia di rete per mostrare come evitare le route asimmetriche
<a name="asymmetric"> </a>

Si desidera evitare il routing asimmetrico per garantire che gli utenti dell'organizzazione possano utilizzare Office 365 senza problemi e altri servizi importanti su Internet. Esistono due configurazioni comuni che causano il routing asimmetrico. È il momento giusto per esaminare la configurazione di rete che si prevede di usare e verificare se potrebbe esistere uno di questi scenari di routing asimmetrico.
  
Per iniziare, verranno esaminate alcune situazioni diverse associate al diagramma di rete seguente. In questo diagramma, tutti i server che ricevono richieste in ingresso, ad esempio ADFS o i server ibridi locali, sono nel data center del New Jersey e sono annunciati su Internet.
  
1. Mentre la rete perimetrale è sicura, non è disponibile alcun NAT di origine per le richieste in ingresso.

2. I server nel data center del New Jersey sono in grado di visualizzare sia le route Internet che expressRoute.

![Panoramica della connettività ExpressRoute](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
Abbiamo anche suggerimenti su come correggerli.
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a>Problema 1: connessione da cloud a locale tramite Internet
  
Il diagramma seguente illustra il percorso di rete asimmetrico intrapreso quando la configurazione di rete non fornisce NAT per le richieste in ingresso dal cloud Microsoft su Internet.
  
1. La richiesta in ingresso Office 365 recupera l'indirizzo IP dell'endpoint locale dal DNS pubblico e invia la richiesta alla rete perimetrale.

2. In questa configurazione difettosa non è configurato o disponibile alcun NAT di origine nella rete perimetrale in cui viene inviato il traffico, con conseguente utilizzo dell'indirizzo IP di origine effettivo come destinazione di ritorno.

  - Il server della rete instrada il traffico di ritorno Office 365 attraverso qualsiasi connessione di rete ExpressRoute disponibile.

  - Il risultato è un percorso asimmetrico per il flusso Office 365, con conseguente connessione interrotta.

![ExpressRoute Asymetric routing problem 1](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a>Soluzione 1a: NAT di origine
  
La semplice aggiunta di un NAT di origine alla richiesta in ingresso risolve questa rete non configurata correttamente. In questo diagramma:
  
1. La richiesta in arrivo continua a entrare attraverso la rete perimetrale del data center del New Jersey. Questa volta Nat di origine è disponibile.

2. La risposta dal server instrada di nuovo verso l'IP associato al NAT di origine anziché all'indirizzo IP originale, determinando la restituzione della risposta lungo lo stesso percorso di rete.

![Soluzione di routing Asymetric ExpressRoute 1](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a>Soluzione 1b: ambito route
  
In alternativa, è possibile scegliere di non consentire l'annuncio dei prefissi BGP ExpressRoute, rimuovendo il percorso di rete alternativo per tali computer. In questo diagramma:
  
1. La richiesta in arrivo continua a entrare attraverso la rete perimetrale del data center del New Jersey. Questa volta i prefissi annunciati da Microsoft tramite il circuito ExpressRoute non sono disponibili per il data center del New Jersey.

2. La risposta dal server instrada di nuovo verso l'IP associato all'indirizzo IP originale sull'unica route disponibile, determinando la restituzione della risposta lungo lo stesso percorso di rete.

![Soluzione di routing Asymetric ExpressRoute 2](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a>Problema 2: connessione da cloud a locale tramite ExpressRoute
  
Il diagramma seguente illustra il percorso di rete asimmetrico intrapreso quando la configurazione di rete non fornisce NAT per le richieste in ingresso dal cloud Microsoft tramite ExpressRoute.
  
1. La richiesta in ingresso da Office 365 recupera l'indirizzo IP da DNS e invia la richiesta alla rete perimetrale.

2. In questa configurazione difettosa non è configurato o disponibile alcun NAT di origine nella rete perimetrale in cui viene inviato il traffico, con conseguente utilizzo dell'indirizzo IP di origine effettivo come destinazione di ritorno.

  - Il computer della rete instrada il traffico di ritorno Office 365 attraverso qualsiasi connessione di rete ExpressRoute disponibile.

  - Il risultato è una connessione asimmetrica Office 365.

![ExpressRoute Asymetric routing problem 2](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a>Soluzione 2: NAT di origine
  
La semplice aggiunta di un NAT di origine alla richiesta in ingresso risolve questa rete non configurata correttamente. In questo diagramma:
  
1. La richiesta in arrivo continua a entrare attraverso la rete perimetrale del data center di New York. Questa volta Nat di origine è disponibile.

2. La risposta dal server instrada di nuovo verso l'IP associato al NAT di origine anziché all'indirizzo IP originale, determinando la restituzione della risposta lungo lo stesso percorso di rete.

![Soluzione di routing Asymetric ExpressRoute 3](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a>Verificare che la progettazione della rete abbia la simmetria del percorso

A questo punto, è necessario verificare sulla carta che il piano di implementazione offre la simmetria della route per i diversi scenari in cui verrà utilizzato Office 365. Identificherai la route di rete specifica che dovrebbe essere intrapresa quando una persona usa funzionalità diverse del servizio. Dalla rete locale e dal routing WAN, ai dispositivi perimetrali, al percorso di connettività; ExpressRoute o Internet e alla connessione all'endpoint online.
  
È necessario eseguire questa operazione per tutti i servizi Office 365 di rete precedentemente identificati come servizi che verranno adottati dall'organizzazione.
  
Aiuta a fare questo documento a piedi attraverso i percorsi con una seconda persona. Spiegare loro da dove si prevede che ogni hop di rete otterrà la route successiva e assicurarsi di avere familiarità con i percorsi di routing. Tenere presente che ExpressRoute fornirà sempre una route con ambito maggiore agli indirizzi IP del server Microsoft, con un costo di route inferiore rispetto a una route predefinita internet.
  
### <a name="design-client-connectivity-configuration"></a>Progettare la configurazione della connettività client
<a name="asymmetric"> </a>

![Uso di file PAC con ExpressRoute](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
Se si utilizza un server proxy per il traffico associato a Internet, è necessario modificare i file PAC o di configurazione client per assicurarsi che i computer client della rete siano configurati correttamente per inviare il traffico ExpressRoute desiderato Office 365 senza transitare il server proxy e che il traffico rimanente, incluso un traffico Office 365, venga inviato al proxy pertinente. Leggi la nostra guida [sulla gestione Office 365 endpoint,](./managing-office-365-endpoints.md) ad esempio i file PAC.
  
> [!NOTE]
> Gli endpoint cambiano frequentemente, con la frequenza settimanale. È consigliabile apportare modifiche solo in base ai servizi e alle funzionalità adottati dall'organizzazione per ridurre il numero di modifiche da apportare per rimanere al corrente. Prestare particolare attenzione alla data di validità nel feed RSS **in** cui vengono annunciate le modifiche e viene mantenuto un record di tutte le modifiche precedenti, gli indirizzi IP annunciati potrebbero non essere annunciati o rimossi dall'annuncio pubblicitario fino a quando non viene raggiunta la data di validità.
  
## <a name="build-your-deployment-and-testing-procedures"></a>Creare le procedure di distribuzione e test
<a name="testing"> </a>

Il piano di implementazione deve includere sia la pianificazione di test che di rollback. Se l'implementazione non funziona come previsto, il piano deve essere progettato per influire sul minor numero di persone prima che i problemi siano individuati. Di seguito sono riportati alcuni principi di alto livello che il piano deve prendere in considerazione.
  
1. Impostare in fasi il segmento di rete e l'onboarding del servizio utente per ridurre al minimo l'interruzione.

2. Pianificare i test delle route con traceroute e la connessione TCP da un host connesso a Internet separato.

3. Preferibilmente, il test dei servizi in ingresso e in uscita deve essere eseguito in una rete di test isolata con un tenant di test Office 365 tenant.

      - In alternativa, i test possono essere eseguiti in una rete di produzione se il cliente non Office 365 o è in fase pilota.

      - In alternativa, i test possono essere eseguiti durante un'interruzione di produzione che viene messa da parte solo per il test e il monitoraggio.

      - In alternativa, è possibile eseguire test controllando le route per ogni servizio in ogni nodo di router di livello 3. Questo fall back deve essere utilizzato solo se non sono possibili altri test poiché la mancanza di test fisici introduce rischi.

### <a name="build-your-deployment-procedures"></a>Creare le procedure di distribuzione

Le procedure di distribuzione devono essere distribuite a piccoli gruppi di persone in fasi per consentire il testing prima di distribuirlo a gruppi di persone più grandi. Di seguito sono riportati diversi modi per eseguire in fasi la distribuzione di ExpressRoute.
  
1. Configurare ExpressRoute con il peering Microsoft e inoltrare gli annunci di route a un singolo host solo a scopo di test a fasi.

2. Annunciare le route alla rete ExpressRoute a un singolo segmento di rete in un primo momento ed espandere gli annunci di route in base al segmento di rete o all'area geografica.

3. Se si distribuisce Office 365 per la prima volta, usare la distribuzione di rete ExpressRoute come progetto pilota per un numero limitato di persone.

4. Se si usano server proxy, è possibile configurare in alternativa un file PAC di test per indirizzare un numero limitato di persone a ExpressRoute con test e feedback prima di aggiungerlo.

Il piano di implementazione deve elencare tutte le procedure di distribuzione da eseguire o i comandi da utilizzare per distribuire la configurazione di rete. Quando arriva il tempo di interruzione della rete, tutte le modifiche apportate devono essere del piano di distribuzione scritto scritto in anticipo e esaminato peer. Vedi le nostre indicazioni sulla configurazione tecnica di ExpressRoute.
  
- Aggiornamento dei record TXT SPF se sono stati modificati gli indirizzi IP per i server locali che continueranno a inviare posta elettronica.

- Aggiornamento di eventuali voci DNS per i server locali se sono stati modificati indirizzi IP per supportare una nuova configurazione NAT.

- Assicurati di aver sottoscritto il feed RSS per le notifiche Office 365 endpoint per mantenere eventuali configurazioni di routing o proxy.

Al termine della distribuzione di ExpressRoute, è necessario eseguire le procedure del piano di test. I risultati di ogni procedura devono essere registrati. È necessario includere le procedure per il rollback nell'ambiente di produzione originale nel caso in cui i risultati del piano di test indichino che l'implementazione non è riuscita.
  
### <a name="build-your-test-procedures"></a>Creare le procedure di test

Le procedure di test devono includere i test per ogni servizio di rete in ingresso e in uscita per Office 365 che usano ExpressRoute e quelli che non lo saranno. Le procedure devono includere test da ogni percorso di rete univoco, inclusi gli utenti che non sono locali nella rete LAN aziendale.
  
Di seguito sono riportati alcuni esempi di attività di test.
  
1. Eseguire il ping dal router locale al router dell'operatore di rete.

2. Convalidare che oltre 500 Office 365 indirizzi IP e CRM Online siano ricevuti dal router locale.

3. Verificare che il NAT in ingresso e in uscita sia in funzione tra ExpressRoute e la rete interna.

4. Verificare che le route verso NAT vengano annunciate dal router.

5. Verificare che ExpressRoute abbia accettato i prefissi annunciati.

      - Utilizzare il cmdlet seguente per verificare gli annunci di peering:

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. Verificare che l'intervallo IP NAT pubblico non venga annunciato a Microsoft tramite qualsiasi altro circuito di rete ExpressRoute o Internet pubblico, a meno che non si tratta di un sottoinsieme specifico di un intervallo più grande come nell'esempio precedente.

7. I circuiti ExpressRoute sono associati e verificano che entrambe le sessioni BGP siano in esecuzione.

8. Configurare un singolo host all'interno del NAT e usare ping, tracert e tcpping per testare la connettività tra il nuovo circuito e l'host outlook.office365.com. In alternativa, è possibile utilizzare uno strumento come Wireshark o Microsoft Network Monitor 3.4 su una porta con mirroring a MSEE per verificare di essere in grado di connettersi all'indirizzo IP associato a outlook.office365.com.

9. Testare la funzionalità a livello di applicazione Exchange Online.

  - Test Outlook è in grado di connettersi a Exchange Online e inviare/ricevere posta elettronica.

  - Test Outlook è in grado di usare la modalità online.

  - Testare la connettività dello smartphone e la funzionalità di invio/ricezione.

10. Testare la funzionalità a livello di applicazione per SharePoint Online

  - Testare OneDrive for Business client di sincronizzazione.

  - Testare SharePoint Web Access online.

11. Testare la funzionalità a livello di applicazione Skype for Business scenari di chiamata:

  - Partecipare alla conferenza telefonica come utente autenticato [invito avviato dall'utente finale].

  - Invitare l'utente alla conferenza telefonica [invito inviato da MCU].

  - Partecipare alla conferenza come utente anonimo utilizzando l Skype for Business app web.

  - Partecipa alla chiamata dalla connessione pc cablata, dal telefono IP e dal dispositivo mobile.

  - Call to federated user o Call to PSTN Validation: call is completed, call quality is acceptable, connection time is acceptable.

  - Verificare che lo stato di presenza dei contatti sia aggiornato sia per i membri del tenant che per gli utenti federati.

### <a name="common-problems"></a>Problemi comuni

Il routing asimmetrico è il problema di implementazione più comune. Ecco alcune fonti comuni da cercare:
  
- Utilizzo di una topologia di routing di rete aperta o flat senza NAT di origine sul posto.

- Non si usa SNAT per instradare i servizi in ingresso tramite le connessioni Internet ed ExpressRoute.

- Non testare i servizi in ingresso in ExpressRoute in una rete di test prima della distribuzione su larga base.

## <a name="deploying-expressroute-connectivity-through-your-network"></a>Distribuzione della connettività ExpressRoute tramite la rete
<a name="testing"> </a>

Implementare gradualmente la distribuzione in un segmento della rete alla volta, stendendo progressivamente la connettività a diverse parti della rete con un piano di rollback per ogni nuovo segmento di rete. Se la distribuzione è allineata a una distribuzione Office 365, distribuire prima Office 365 utenti pilota ed estendersi da lì.
  
Prima per il test e quindi per la produzione:
  
- Eseguire i passaggi di distribuzione per abilitare ExpressRoute.

- Testare la visualizzazione delle route di rete come previsto.

- Eseguire test su ogni servizio in ingresso e in uscita.

- Eseguire il rollback in caso di problemi.

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a>Configurare una connessione di test a ExpressRoute con un segmento di rete di test

Ora che hai completato il piano su carta, è il momento di testare su piccola scala. In questo test verrà stabilita una singola connessione ExpressRoute con Peering Microsoft a una subnet di prova nella rete locale. È possibile configurare un [tenant di Office 365](https://go.microsoft.com/fwlink/p/?LinkID=403802) di valutazione con connettività da e verso la subnet di test e includere tutti i servizi in uscita e in ingresso che verranno utilizzato in produzione nella subnet di test. Configurare DNS per il segmento di rete di prova e stabilire tutti i servizi in ingresso e in uscita. Eseguire il piano di test e assicurarsi di avere familiarità con il routing per ogni servizio e la propagazione della route.
  
### <a name="execute-the-deployment-and-test-plans"></a>Eseguire i piani di distribuzione e test

Dopo aver completato gli elementi descritti in precedenza, controllare le aree completate e verificare che tu e il team li abbia esaminati prima di eseguire i piani di distribuzione e test.
  
- Elenco dei servizi in uscita e in ingresso coinvolti nella modifica della rete.

- Diagramma dell'architettura di rete globale che mostra sia l'uscita Internet che le posizioni di meet-me ExpressRoute.

- Diagramma di routing di rete che mostra i diversi percorsi di rete utilizzati per ogni servizio distribuito.

- Un piano di distribuzione con la procedura per implementare le modifiche e il rollback, se necessario.

- Un piano di test per testare ogni Office 365 e il servizio di rete.

- Convalida cartacea completata delle route di produzione per i servizi in ingresso e in uscita.

- Test completato in un segmento di rete di test, incluso il test della disponibilità.

Scegliere una finestra di interruzione sufficientemente lunga da poter essere eseguita attraverso l'intero piano di distribuzione e il piano di test, ha un certo tempo disponibile per la risoluzione dei problemi e il tempo per il rollback, se necessario.
  
> [!CAUTION]
> A causa della natura complessa del routing sia su Internet che su ExpressRoute, è consigliabile aggiungere ulteriore tempo del buffer a questa finestra per gestire la risoluzione dei problemi relativi al routing complesso.
  
### <a name="configure-qos-for-skype-for-business-online"></a>Configurare QoS per Skype for Business Online

QoS è necessario per ottenere vantaggi vocali e riunioni per Skype for Business Online. È possibile configurare QoS dopo aver garantito che la connessione di rete ExpressRoute non blocca alcun altro accesso Office 365 servizio. La configurazione per QoS è descritta [nell'articolo ExpressRoute e QoS in Skype for Business Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
## <a name="troubleshooting-your-implementation"></a>Risoluzione dei problemi relativi all'implementazione
<a name="troubleshooting"> </a>

Il primo punto da esaminare è la procedura illustrata in questa guida all'implementazione, mancata nel piano di implementazione? Tornare indietro ed eseguire ulteriori test di rete di piccole dimensioni, se possibile, per replicare l'errore ed eseguirne il debug.
  
Identificare i servizi in ingresso o in uscita non riusciti durante il test. Ottenere in modo specifico gli indirizzi IP e le subnet per ognuno dei servizi che hanno avuto esito negativo. Andare avanti e illustrare il diagramma della topologia di rete su carta e convalidare il routing. Verificare in modo specifico la posizione in cui viene annunciato il routing ExpressRoute, testare il routing durante l'interruzione, se possibile, con le tracce.
  
Eseguire PSPing con una traccia di rete per ogni endpoint del cliente e valutare gli indirizzi IP di origine e di destinazione per verificare che siano come previsto. Eseguire telnet in qualsiasi host di posta esposto sulla porta 25 e verificare che SNAT nasconde l'indirizzo IP di origine originale, se previsto.
  
Tenere presente che durante la distribuzione di Office 365 con una connessione ExpressRoute è necessario verificare che sia la configurazione di rete per ExpressRoute sia progettata in modo ottimale e che siano stati ottimizzati anche gli altri componenti della rete, ad esempio i computer client. Oltre a utilizzare questa guida alla pianificazione per risolvere i problemi relativi ai passaggi che potrebbero non essere stati evasi, è stato scritto anche un piano di risoluzione dei problemi di [prestazioni per Office 365](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c) .
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/implementexpressroute365]()
  
## <a name="related-topics"></a>Argomenti correlati

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute per Office 365](azure-expressroute.md)
  
[Gestione di ExpressRoute per la connettività di Office 365](managing-expressroute-for-connectivity.md)
  
[Routing con ExpressRoute per Office 365](routing-with-expressroute.md)
  
[Pianificazione della rete con ExpressRoute per Office 365](network-planning-with-expressroute.md)
  
[Uso di community BGP in ExpressRoute per Office 365 scenari](bgp-communities-in-expressroute.md)
  
[Qualità multimediale e prestazioni della connettività di rete in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Ottimizzazione della rete per Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute e QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flusso di chiamata con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)
  
[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)
  
[Intervalli di indirizzi IP e URL di Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Ottimizzazione delle prestazioni e della rete di Office 365](network-planning-and-performance.md)