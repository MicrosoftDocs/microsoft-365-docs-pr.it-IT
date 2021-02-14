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
description: Informazioni su come implementare ExpressRoute per Office 365, che fornisce un percorso di routing alternativo per molti servizi di Office 365 con connessione a Internet.
ms.openlocfilehash: 767a99f3a27f30b7193fd0d0b8376ff4923daffb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691463"
---
# <a name="implementing-expressroute-for-office-365"></a>Implementazione di ExpressRoute per Office 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

ExpressRoute per Office 365 fornisce un percorso di routing alternativo per molti servizi di Office 365 con connessione Internet. L'architettura di ExpressRoute per Office 365 si basa sulla pubblicità dei prefissi IP pubblici dei servizi di Office 365 che sono già accessibili tramite Internet nei circuiti ExpressRoute di cui è stato eseguito il provisioning per la successiva ridistribuzione di tali prefissi IP nella rete. Con ExpressRoute è possibile abilitare in modo efficace diversi percorsi di routing, tramite Internet ed ExpressRoute, per molti servizi di Office 365. Questo stato di routing nella rete può rappresentare una modifica significativa alla modalità di progettazione della topologia di rete interna.
  
 **Stato:** Guida completa v2
  
È necessario pianificare attentamente l'implementazione di ExpressRoute per Office 365 in modo da soddisfare le complessità di rete associate alla disponibilità del routing tramite un circuito dedicato con route iniettate nella rete principale e in Internet. Se l'utente e il team non eseguono la pianificazione dettagliata e i test in questa guida, esiste un rischio elevato che si verifichi intermittente o una perdita totale di connettività ai servizi di Office 365 quando il circuito ExpressRoute è abilitato.
  
Per una corretta implementazione, è necessario analizzare i requisiti dell'infrastruttura, esaminare la valutazione e la progettazione dettagliate della rete, pianificare attentamente l'implementazione in modo a fasi e controllato e creare un piano di convalida e test dettagliato. Per un ambiente distribuito di grandi dimensioni non è raro che le implementazioni si estendono per diversi mesi. Questa guida è progettata per aiutarti a pianificare in anticipo.
  
Le distribuzioni con successo di grandi dimensioni possono richiedere sei mesi di pianificazione e spesso includono membri del team di molte aree dell'organizzazione, tra cui amministratori di rete, firewall e server proxy, amministratori di Office 365, sicurezza, supporto per gli utenti finali, gestione dei progetti e sponsorizzazione esecutiva. L'investimento nel processo di pianificazione ridurrà la probabilità che si verifichino errori di distribuzione causando tempi di inattività o una risoluzione dei problemi complessa e costosa.
  
Ci aspettiamo che i prerequisiti seguenti siano completati prima dell'avvio di questa guida all'implementazione.
  
1. È stata completata una valutazione di rete per determinare se ExpressRoute è consigliato e approvato.

2. È stato selezionato un provider di servizi di rete ExpressRoute. Informazioni dettagliate sui [partner ExpressRoute e sulle posizioni di peering.](https://azure.microsoft.com/documentation/articles/expressroute-locations/)

3. Hai già letto e compreso la documentazione [di ExpressRoute](https://azure.microsoft.com/documentation/services/expressroute/) e la rete interna è in grado di soddisfare i prerequisiti di ExpressRoute end-to-end.

4. Il team ha letto tutte le indicazioni e la documentazione pubblica su , e ha seguito la serie di corsi di formazione di Azure ExpressRoute per [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365) [https://aka.ms/ert](https://aka.ms/ert) Office [365](https://channel9.msdn.com/series/aer) su Channel 9 per comprendere i dettagli tecnici critici, tra cui:

      - Le dipendenze Internet dei servizi SaaS.

      - Come evitare le route asimmetriche e gestire il routing complesso.

      - Come incorporare i controlli a livello di applicazione, disponibilità e sicurezza perimetrale.

## <a name="begin-by-gathering-requirements"></a>Iniziare raccogliendo i requisiti
<a name="requirements"> </a>

Iniziare determinando quali funzionalità e servizi si intende adottare all'interno dell'organizzazione. È necessario determinare quali funzionalità dei diversi servizi di Office 365 verranno utilizzate e quali posizioni della rete ospiteranno gli utenti che usano tali funzionalità. Con il catalogo di scenari, è necessario aggiungere gli attributi di rete richiesti da ognuno di questi scenari; ad esempio i flussi di traffico di rete in ingresso e in uscita e se gli endpoint di Office 365 sono disponibili su ExpressRoute o meno.
  
Per raccogliere i requisiti dell'organizzazione:
  
- Catalogare il traffico di rete in ingresso e in uscita per i servizi di Office 365 in uso nell'organizzazione. Consultare la pagina degli URL e degli intervalli di indirizzi IP di Office 365 per la descrizione dei flussi richiesti da diversi scenari di Office 365.

- Raccogliere la documentazione relativa alla topologia di rete esistente che mostra i dettagli della backbone e della topologia WAN interna, la connettività dei siti satellite, la connettività utente dell'ultimo chilometro, il routing ai punti di uscita del perimetro della rete e i servizi proxy.

  - Identificare gli endpoint del servizio in ingresso nei diagrammi di rete a cui si connetteranno Office 365 e altri servizi Microsoft, mostrando sia i percorsi di connessione Internet che i percorsi di connessione ExpressRoute proposti.

  - Identificare tutte le posizioni geografiche degli utenti e la connettività WAN tra le posizioni con le posizioni attualmente in uscita verso Internet e le posizioni proposte per l'uscita a una posizione peering ExpressRoute.

  - Identificare tutti i dispositivi perimetrali, ad esempio proxy, firewall e così via, e catalogare la relazione con i flussi che passano su Internet ed ExpressRoute.

  - Documentare se gli utenti finali accederanno ai servizi di Office 365 tramite routing diretto o proxy di applicazione indiretto per i flussi Internet ed ExpressRoute.

- Aggiungere la posizione dei percorsi tenant e meet-me al diagramma di rete.

- Stimare le prestazioni di rete previste e osservate e le caratteristiche di latenza dalle principali posizioni degli utenti a Office 365. Tenere presente che Office 365 è un set globale e distribuito di servizi e gli utenti si connetteranno a posizioni che potrebbero essere diverse dalla posizione del tenant. Per questo motivo, è consigliabile misurare e ottimizzare la latenza tra l'utente e il perimetro più vicino della rete globale Microsoft tramite ExpressRoute e connessioni Internet. È possibile utilizzare i risultati della valutazione della rete per facilitare questa attività.

- Elencare i requisiti di sicurezza della rete aziendale e disponibilità elevata che devono essere soddisfatti con la nuova connessione ExpressRoute. Ad esempio, in che modo gli utenti continuano ad accedere a Office 365 in caso di uscita da Internet o errore del circuito ExpressRoute.

- Documentare quali flussi di rete di Office 365 in ingresso e in uscita useranno il percorso Internet e che useranno ExpressRoute. Le specifiche delle posizioni geografiche degli utenti e i dettagli della topologia di rete locale potrebbero richiedere che il piano sia diverso da una posizione utente a un'altra.

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a>Catalogare il traffico di rete in ingresso e in uscita
<a name="trafficCatalog"> </a>

Per ridurre al minimo il routing e altre complessità di rete, è consigliabile usare ExpressRoute solo per Office 365 per i flussi di traffico di rete necessari per passare attraverso una connessione dedicata a causa di requisiti normativi o come risultato della valutazione della rete. È inoltre consigliabile impostare l'ambito del routing ExpressRoute e affrontare i flussi di traffico di rete in ingresso e in uscita come fasi diverse e distinte del progetto di implementazione. Distribuire ExpressRoute per Office 365 solo per i flussi di traffico di rete in uscita avviati dall'utente e lasciare i flussi di traffico di rete in ingresso su Internet può aiutare a controllare l'aumento della complessità topologica e i rischi derivanti dall'introduzione di ulteriori possibilità di routing asimmetrico.
  
Il catalogo del traffico di rete deve contenere elenchi di tutte le connessioni di rete in ingresso e in uscita di cui si dispone tra la rete locale e Microsoft.
  
- I flussi di traffico di rete in uscita sono qualsiasi scenario in cui viene avviata una connessione dall'ambiente locale, ad esempio da client o server interni, con una destinazione dei servizi Microsoft. Queste connessioni possono essere dirette a Office 365 o indirette, ad esempio quando la connessione passa attraverso server proxy, firewall o altri dispositivi di rete nel percorso di Office 365.

- I flussi di traffico di rete in ingresso sono tutti gli scenari in cui viene avviata una connessione dal cloud Microsoft a un host locale. Queste connessioni in genere devono passare attraverso il firewall e altre infrastrutture di sicurezza necessarie ai criteri di sicurezza dei clienti per i flussi originati esternamente.

Leggere  la sezione Verifica della simmetria della route dell'articolo Routing con ExpressRoute per [Office 365](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) per determinare quali servizi invieranno il traffico in ingresso e cercare la colonna contrassegnata come ExpressRoute per **Office 365** nell'articolo di riferimento sugli endpoint di [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) per determinare il resto delle informazioni sulla connettività.
  
Per ogni servizio che richiede una connessione in uscita, è necessario descrivere la connettività pianificata per il servizio, inclusi routing di rete, configurazione proxy, ispezione dei pacchetti e esigenze di larghezza di banda.
  
Per ogni servizio che richiede una connessione in ingresso, sono necessarie alcune informazioni aggiuntive. I server nel cloud Microsoft stabiliranno connessioni alla rete locale. per assicurarsi che le connessioni vengano effettuate correttamente, è necessario descrivere tutti gli aspetti di questa connettività, tra cui; le voci DNS pubbliche per i servizi che accetteranno queste connessioni in ingresso, gli indirizzi IP IPv4 formattati CIDR, le apparecchiature ISP coinvolte e la modalità di gestione di NAT in ingresso o NAT di origine per queste connessioni.
  
Le connessioni in ingresso devono essere esaminate indipendentemente dal fatto che si connettono tramite Internet o ExpressRoute per garantire che il routing asimmetrico non sia stato introdotto. In alcuni casi, gli endpoint locali a cui i servizi di Office 365 avviano le connessioni in ingresso potrebbero dover essere accessibili anche da altri servizi Microsoft e non Microsoft. È fondamentale che l'abilitazione del routing ExpressRoute a questi servizi per office 365 non interrompa altri scenari. In molti casi, i clienti potrebbero dover implementare modifiche specifiche alla rete interna, ad esempio NAT basata sull'origine, per garantire che i flussi in ingresso da Microsoft rimangano simmetrici dopo l'a attivazione di ExpressRoute.
  
Ecco un esempio del livello di dettaglio necessario. In questo caso, Exchange ibrido instraderebbe al sistema locale tramite ExpressRoute.

|**Proprietà Connection**|**Valore**|
|:-----|:-----|
|**Direzione del traffico di rete** <br/> |In ingresso  <br/> |
|**Servizio** <br/> |Ambiente Exchange ibrido  <br/> |
|**Endpoint pubblico di Office 365 (origine)** <br/> |Exchange Online (indirizzi IP)  <br/> |
|**Endpoint locale pubblico (destinazione)** <br/> |5.5.5.5  <br/> |
|**Voce DNS pubblica (Internet)** <br/> |Autodiscover.contoso.com  <br/> |
|**Questo endpoint locale verrà usato da altri servizi Microsoft (non Office 365)** <br/> |No  <br/> |
|**Questo endpoint locale verrà utilizzato da utenti/sistemi su Internet** <br/> |Sì  <br/> |
|**Sistemi interni pubblicati tramite endpoint pubblici** <br/> |Exchange Server ruolo Accesso client (locale) 192.168.101, 192.168.102, 192.168.103  <br/> |
|**Annuncio IP dell'endpoint pubblico** <br/> |**A Internet**: 5.5.0.0/16  <br/> **To ExpressRoute**: 5.5.5.0/24  <br/> |
|**Controlli di sicurezza/perimetro** <br/> |**Percorso Internet**: DeviceID_002  <br/> **Percorso ExpressRoute**: DeviceID_003  <br/> |
|**Disponibilità elevata** <br/> |Attivo/attivo su 2 con ridondanza geografica  <br/> Circuiti ExpressRoute - Chicago e Dallas  <br/> |
|**Controllo della simmetria del percorso** <br/> |**Metodo**: NAT di origine  <br/> **Percorso Internet:** connessioni NAT di origine in ingresso a 192.168.5.5  <br/> |**Percorso ExpressRoute**: connessioni NAT di origine a 192.168.1.0 (Chicago) e 192.168.2.0 (Dallas)  <br/> |

Ecco un esempio di un servizio solo in uscita:

|**Proprietà Connection**|**Valore**|
|:-----|:-----|
|**Direzione del traffico di rete** <br/> |In uscita  <br/> |
|**Servizio** <br/> |SharePoint Online  <br/> |
|**Endpoint locale (origine)** <br/> |Workstation utente  <br/> |
|**Endpoint pubblico di Office 365 (destinazione)** <br/> |SharePoint Online (indirizzi IP)  <br/> |
|**Voce DNS pubblica (Internet)** <br/> |\*.sharepoint.com (e FQDN aggiuntivi)  <br/> |
|**Riferimenti alla rete CDN** <br/> |cdn.sharepointonline.com (e FQDN aggiuntivi) - Indirizzi IP gestiti dai provider della rete CDN  <br/> |
|**Annuncio IP e NAT in uso** <br/> |**Percorso Internet/NAT di origine**: 1.1.1.0/24  <br/> **ExpressRoute path/Source NAT**: 1.1.2.0/24 (Chicago) e 1.1.3.0/24 (Dallas)  <br/> |
|**Metodo di connettività** <br/> |**Internet:** tramite proxy di livello 7 (file PAC)  <br/> **ExpressRoute:** instradamento diretto (nessun proxy)  <br/> |
|**Controlli di sicurezza/perimetro** <br/> |**Percorso Internet**: DeviceID_002  <br/> **Percorso ExpressRoute**: DeviceID_003  <br/> |
|**Disponibilità elevata** <br/> |**Percorso Internet**: uscita Internet ridondante  <br/> **Percorso ExpressRoute**: routing attivo/attivo tra 2 circuiti ExpressRoute con ridondanza geografica - Chicago e Dallas  <br/> |
|**Controllo della simmetria del percorso** <br/> |**Metodo**: NAT di origine per tutte le connessioni  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a>Progettazione della topologia di rete con connettività regionale
<a name="topology"> </a>

Dopo aver compreso i servizi e i flussi di traffico di rete associati, è possibile creare un diagramma di rete che incorpora questi nuovi requisiti di connettività e illustra le modifiche da apportare per usare ExpressRoute per Office 365. Il diagramma deve includere:
  
1. Tutte le posizioni degli utenti da cui sarà possibile accedere a Office 365 e ad altri servizi.

2. Tutti i punti di uscita di Internet ed ExpressRoute.

3. Tutti i dispositivi in ingresso e in uscita che gestiscono la connettività all'interno e all'esterno della rete, inclusi router, firewall, server proxy dell'applicazione e rilevamento/prevenzione delle intrusioni.

4. Destinazioni interne per tutto il traffico in ingresso, ad esempio server ADFS interni che accettano connessioni dai server proxy dell'applicazione Web ADFS.

5. Catalogo di tutte le subnet IP che verranno annunciate

6. Identificare ogni posizione da cui gli utenti accederanno a Office 365 ed elencare le posizioni meet-me che verranno usate per ExpressRoute.

7. I percorsi e le parti della topologia di rete interna, in cui i prefissi IP Microsoft appresi da ExpressRoute verranno accettati, filtrati e propagati.

8. La topologia di rete deve illustrare la posizione geografica di ogni segmento di rete e il modo in cui si connette alla rete Microsoft tramite ExpressRoute e/o Internet.

Il diagramma seguente mostra ogni posizione in cui gli utenti usano Office 365 insieme agli annunci di routing in ingresso e in uscita a Office 365.
  
![ExpressRoute regional geographic meet-me](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
Per il traffico in uscita, gli utenti accedono a Office 365 in uno dei tre modi seguenti:
  
1. Attraverso una sede di meet-me in Nord America per le persone in California.

2. Attraverso una sede di meet-me a Hong Kong per gli utenti di Hong Kong.

3. Attraverso Internet in Bangladesh, dove ci sono meno persone e nessun circuito ExpressRoute è stato effettuato.

![Connessioni in uscita per il diagramma regionale](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
Analogamente, il traffico di rete in ingresso da Office 365 viene restituito in uno dei tre modi seguenti:
  
1. Attraverso una sede di meet-me in Nord America per le persone in California.

2. Attraverso una sede di meet-me a Hong Kong per gli utenti di Hong Kong.

3. Attraverso Internet in Bangladesh, dove ci sono meno persone e nessun circuito ExpressRoute è stato effettuato.

![Connessioni in ingresso per diagramma regionale](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a>Determinare la posizione di meet-me appropriata

La selezione di posizioni meet-me, ovvero la posizione fisica da cui il circuito ExpressRoute connette la rete alla rete Microsoft, è influenzata dalle posizioni da cui gli utenti accederanno a Office 365. Come offerta SaaS, Office 365 non funziona con il modello regionale IaaS o PaaS allo stesso modo di Azure. Office 365 è invece un set distribuito di servizi di collaborazione, in cui gli utenti potrebbero dover connettersi agli endpoint in più data center e aree geografiche, che potrebbero non essere necessariamente nella stessa posizione o area geografica in cui è ospitato il tenant dell'utente.
  
Ciò significa che la considerazione più importante da prendere quando si selezionano le posizioni meet-me per ExpressRoute per Office 365 è la posizione da cui si connetteranno gli utenti dell'organizzazione. Il consiglio generale per una connettività ottimale di Office 365 è implementare il routing, in modo che le richieste degli utenti ai servizi di Office 365 vengano inviate nella rete Microsoft attraverso il percorso di rete più breve, anche questo viene spesso definito routing a caldo. Ad esempio, se la maggior parte degli utenti di Office 365 si trova in una o due posizioni, la selezione di posizioni meet-me che si trovano nella prossimità più vicina alla posizione di tali utenti creerà la progettazione ottimale. Se l'azienda ha una grande popolazione di utenti in molte aree geografiche diverse, è consigliabile avere più circuiti ExpressRoute e posizioni meet-me. Per alcune delle posizioni degli utenti, il percorso più breve/ottimale nella rete Microsoft e Office 365 potrebbe non essere attraverso la WAN interna e i punti meet-me di ExpressRoute, ma tramite Internet.
  
Spesso, esistono più posizioni meet-me che possono essere selezionate all'interno di un'area geografica con prossimità relativa agli utenti. Compila la tabella seguente per guidare le tue decisioni.

|**Sedi expressroute meet-me pianificate in California e New York**||
|:-----|:-----|
|Posizione  <br/> |Numero di persone  <br/> |Latenza prevista per l'uscita dalla rete Microsoft tramite Internet  <br/> |Latenza prevista per la rete Microsoft su ExpressRoute  <br/> |
|Roma  <br/> |10.000  <br/> |~15 ms  <br/> |~10 ms (tramite Silicon Valle)  <br/> |
|Washington DC  <br/> |15,000  <br/> |~20 ms  <br/> |~10 ms (via New York)  <br/> |
|Dallas  <br/> |5,000  <br/> |~15 ms  <br/> |~40 ms (via New York)  <br/> |

Dopo aver sviluppato l'architettura di rete globale che mostra l'area di Office 365, le posizioni del provider di servizi di rete ExpressRoute e la quantità di persone in base alla posizione, può essere usata per identificare se è possibile eseguire ottimizzazioni. Può anche mostrare connessioni di rete hairpin globali in cui il traffico instrada verso una posizione distante per ottenere la posizione meet-me. Se viene rilevato un hairpin nella rete globale, è necessario correggere l'errore prima di continuare. Trova un'altra posizione di meet-me o usa punti di uscita internet selettivi per evitare l'hairpin.
  
Il primo diagramma mostra un esempio di un cliente con due posizioni fisiche in Nord America. È possibile visualizzare le informazioni sulle posizioni degli uffici, le posizioni tenant di Office 365 e diverse scelte per le posizioni meet-me di ExpressRoute. In questo esempio, il cliente ha selezionato la posizione meet-me in base a due principi, in ordine:
  
1. Prossimità più vicina alle persone dell'organizzazione.

2. Più vicino a un datacenter Microsoft in cui è ospitato Office 365.

![ExpressRoute US geographic meet-me](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
Espandendo leggermente questo concetto, il secondo diagramma mostra un esempio di cliente multi-nazionale che si trova ad affrontare informazioni e processi decisionali simili. Questo cliente ha un piccolo ufficio in Bangladesh con solo un piccolo team di dieci persone incentrato sulla crescita della propria impronta nella regione. C'è una posizione meet-me a Chennai e un datacenter Microsoft con Office 365 ospitato a Chennai, quindi una posizione meet-me avrebbe senso; Tuttavia, per dieci persone, i costi del circuito aggiuntivo sono oneri. Quando si osserva la rete, è necessario determinare se la latenza coinvolta nell'invio del traffico di rete attraverso la rete è più efficace della spesa del capitale per acquisire un altro circuito ExpressRoute.
  
In alternativa, le dieci persone in Bangladesh potrebbero avere prestazioni migliori con il traffico di rete inviato tramite Internet alla rete Microsoft rispetto al routing sulla rete interna, come illustrato nei diagrammi introduttivi e riprodotti di seguito.
  
![Connessioni in uscita per il diagramma regionale](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a>Creare il piano di implementazione ExpressRoute per Office 365
<a name="implementation"> </a>

Il piano di implementazione deve comprendere sia i dettagli tecnici della configurazione di ExpressRoute che i dettagli della configurazione di tutte le altre infrastrutture della rete, ad esempio:
  
- Pianificare i servizi suddivisi tra ExpressRoute e Internet.

- Pianificare larghezza di banda, sicurezza, disponibilità elevata e failover.

- Progettare il routing in ingresso e in uscita, incluse le ottimizzazioni corrette del percorso di routing per posizioni diverse

- Decidere fino a dove verranno annunciate le route ExpressRoute nella rete e qual è il meccanismo per i client di selezionare internet o percorso ExpressRoute; ad esempio il routing diretto o il proxy dell'applicazione.

- Pianificare le modifiche ai record DNS, incluse le [voci di Sender Policy Framework.](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx)

- Pianificare la strategia NAT, inclusa la nat di origine in ingresso e in uscita.

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a>Pianificare il routing con percorsi di rete Sia Internet che ExpressRoute
<a name="paths"> </a>

- Per la distribuzione iniziale, tutti i servizi in ingresso, ad esempio la posta elettronica in ingresso o la connettività ibrida, sono consigliati per l'utilizzo di Internet.

- Pianificare il routing DELLAN client degli utenti finali, ad esempio la configurazione di [un file PAC/WPAD,](https://aka.ms/manageo365endpoints)una route predefinita, server proxy e annunci di route BGP.

- Pianificare il routing perimetrale, inclusi server proxy, firewall e proxy cloud.

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a>Pianificare larghezza di banda, sicurezza, disponibilità elevata e failover
<a name="availability"> </a>

Creare un piano per la larghezza di banda necessaria per ogni carico di lavoro principale di Office 365. Valutare separatamente i requisiti di larghezza di banda di Exchange Online, SharePoint Online e Skype for Business Online. È possibile utilizzare i calcolatori di stima forniti per Exchange Online e Skype for Business come punto di partenza; Tuttavia, è necessario un test pilota con un campione rappresentativo dei profili utente e delle posizioni per comprendere appieno le esigenze di larghezza di banda dell'organizzazione.
  
Aggiungere il modo in cui la sicurezza viene gestita in ogni posizione internet ed ExpressRoute in uscita dal piano, ricordare che tutte le connessioni ExpressRoute a Office 365 usano il peering pubblico e devono comunque essere protette in conformità ai criteri di sicurezza aziendali per la connessione a reti esterne.
  
Aggiungere dettagli al piano su quali persone saranno interessate dal tipo di interruzione e in che modo tali persone saranno in grado di svolgere il proprio lavoro a piena capacità nel modo più semplice.
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a>Pianificare i requisiti di larghezza di banda, inclusi i requisiti di Skype for Business su instabilità, latenza, congestione e headroom
  
Skype for Business online ha anche requisiti di rete aggiuntivi specifici, che sono dettagliati nell'articolo Qualità multimediale e prestazioni della connettività di [rete in Skype for Business online.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
Leggere la sezione **Pianificazione della larghezza di banda per Azure ExpressRoute** nella pianificazione della rete con [ExpressRoute per Office 365.](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)
  
Quando si esegue una valutazione della larghezza di banda con gli utenti pilota, è possibile utilizzare la nostra guida; [Ottimizzazione delle prestazioni di Office 365 utilizzando le linee di base e la cronologia delle prestazioni.](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
  
#### <a name="plan-for-high-availability-requirements"></a>Pianificare i requisiti di disponibilità elevata
  
Creare un piano per la disponibilità elevata in base alle proprie esigenze e incorporarlo nel diagramma della topologia di rete aggiornato. Leggere la sezione **Disponibilità elevata e failover con Azure ExpressRoute** nella pianificazione della rete con [ExpressRoute per Office 365.](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)
  
#### <a name="plan-for-network-security-requirements"></a>Pianificare i requisiti di sicurezza di rete
  
Creare un piano per soddisfare i requisiti di sicurezza della rete e incorporarlo nel diagramma della topologia di rete aggiornato. Leggere la sezione Applicazione dei controlli di sicurezza agli scenari di Azure ExpressRoute per **Office 365** in Pianificazione della rete con [ExpressRoute per Office 365.](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)
  
### <a name="design-outbound-service-connectivity"></a>Progettare la connettività dei servizi in uscita
<a name="outbound"> </a>

ExpressRoute per Office 365 presenta requisiti  *di*  rete in uscita che potrebbero non essere familiari. In particolare, gli indirizzi IP che rappresentano gli utenti e le reti verso Office 365 e agiscono come endpoint di origine per le connessioni di rete in uscita a Microsoft devono soddisfare requisiti specifici descritti di seguito.
  
1. Gli endpoint devono essere indirizzi IP pubblici, registrati nell'azienda o all'operatore che fornisce connettività ExpressRoute all'utente.

2. Gli endpoint devono essere annunciati a Microsoft e convalidati/accettati da ExpressRoute.

3. Gli endpoint non devono essere annunciati a Internet con la stessa o più metrica di routing preferita.

4. Gli endpoint non devono essere utilizzati per la connettività ai servizi Microsoft non configurati su ExpressRoute.

Se la progettazione della rete non soddisfa questi requisiti, esiste un rischio elevato per gli utenti che si verifichino errori di connettività a Office 365 e ad altri servizi Microsoft a causa dell'instradamento del black holing o del routing asimmetrico. Ciò si verifica quando le richieste ai servizi Microsoft vengono instradati tramite ExpressRoute, ma le risposte vengono instradati attraverso Internet o viceversa e le risposte vengono eliminate dai dispositivi di rete con stato, ad esempio i firewall.
  
Il metodo più comune che puoi usare per soddisfare i requisiti precedenti è usare NAT di origine, implementato come parte della rete o fornito dal gestore di ExpressRoute. Source NAT consente di astrarre i dettagli e l'indirizzamento IP privato della rete Internet da ExpressRoute e; Abbinato a annunci di route IP adeguati, fornisce un meccanismo semplice per garantire la simmetria del percorso. Se si usano dispositivi di rete con stato specifici per le posizioni di peering ExpressRoute, è necessario implementare pool NAT separati per ogni peering ExpressRoute per garantire la simmetria del percorso.
  
Altre informazioni sui requisiti [NAT di ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-nat/)
  
Aggiungere le modifiche per la connettività in uscita al diagramma della topologia di rete.
  
### <a name="design-inbound-service-connectivity"></a>Progettare la connettività dei servizi in ingresso
<a name="inbound"> </a>

La maggior parte delle distribuzioni aziendali di Office 365 presuppone una qualche forma di connettività in ingresso da Office 365 ai servizi locali, ad esempio per scenari ibridi di Exchange, SharePoint e Skype for Business, migrazioni delle cassette postali e autenticazione tramite l'infrastruttura ADFS. Quando ExpressRoute abilita un percorso di routing aggiuntivo tra la rete locale e Microsoft per la connettività in uscita, queste connessioni in ingresso potrebbero essere inavvertitamente influenzate dal routing asimmetrico, anche se si intende che tali flussi continuino a utilizzare Internet. Alcune precauzioni descritte di seguito sono consigliate per garantire che non vi sia alcun impatto sui flussi in ingresso basati su Internet da Office 365 ai sistemi locali.
  
Per ridurre al minimo i rischi del routing asimmetrico per i flussi di traffico di rete in ingresso, tutte le connessioni in ingresso devono usare NAT di origine prima di essere instradate in segmenti della rete con visibilità di routing in ExpressRoute. Se le connessioni in ingresso sono consentite su un segmento di rete con visibilità di routing in ExpressRoute senza NAT di origine, le richieste provenienti da Office 365 entrano da Internet, ma la risposta che torna a Office 365 preferirà il percorso di rete ExpressRoute alla rete Microsoft, causando il routing asimmetrico.
  
Puoi prendere in considerazione uno dei modelli di implementazione seguenti per soddisfare questo requisito:
  
1. Eseguire nat di origine prima che le richieste siano instradati nella rete interna utilizzando apparecchiature di rete come firewall o servizi di bilanciamento del carico nel percorso da Internet ai sistemi locali.

2. Assicurarsi che le route ExpressRoute non vengano propagate ai segmenti di rete in cui risiedono i servizi in ingresso, ad esempio server front-end o sistemi proxy inversi, che gestisce le connessioni Internet.

Tenere esplicitamente conto di questi scenari nella rete e mantenere tutti i flussi di traffico di rete in ingresso su Internet consente di ridurre al minimo il rischio di distribuzione e operativo del routing asimmetrico.
  
In alcuni casi è possibile scegliere di indirizzare alcuni flussi in ingresso sulle connessioni ExpressRoute. Per questi scenari, tenere conto delle considerazioni aggiuntive seguenti.
  
1. Office 365 può essere utilizzato solo come destinazione degli endpoint locali che usano ip pubblici. Ciò significa che anche se l'endpoint in ingresso locale è esposto solo a Office 365 tramite ExpressRoute, deve comunque avere un IP pubblico associato.

2. Tutta la risoluzione dei nomi DNS eseguita dai servizi di Office 365 per risolvere gli endpoint locali avviene tramite DNS pubblico. Ciò significa che è necessario registrare l'FQDN degli endpoint del servizio in ingresso nei mapping IP su Internet.

3. Per ricevere connessioni di rete in ingresso tramite ExpressRoute, le subnet IP pubbliche per questi endpoint devono essere annunciate a Microsoft tramite ExpressRoute.

4. Valutare attentamente questi flussi di traffico di rete in ingresso per garantire che a tali flussi siano applicati controlli di rete e di sicurezza adeguati in base ai criteri di rete e di sicurezza della società.

5. Dopo che gli endpoint in ingresso locali sono stati annunciati a Microsoft tramite ExpressRoute, ExpressRoute diventerà effettivamente il percorso di routing preferito per tali endpoint per tutti i servizi Microsoft, incluso Office 365. Ciò significa che queste subnet degli endpoint devono essere utilizzate solo per le comunicazioni con i servizi di Office 365 e nessun altro servizio nella rete Microsoft. In caso contrario, la progettazione causerà il routing asimmetrico in cui le connessioni in ingresso da altri servizi Microsoft preferiscono instradare l'ingresso su ExpressRoute, mentre il percorso di ritorno utilizzerà Internet.

6. Nel caso in cui un circuito ExpressRoute o una posizione meet-me non sia disponibile, è necessario assicurarsi che gli endpoint in ingresso locali siano ancora disponibili per accettare richieste su un percorso di rete separato. Ciò può indicare subnet pubblicitarie per tali endpoint tramite più circuiti ExpressRoute.

7. È consigliabile applicare NAT di origine per tutti i flussi di traffico di rete in ingresso che entrano nella rete tramite ExpressRoute, soprattutto quando questi flussi attraversano dispositivi di rete con stato, ad esempio firewall.

8. Alcuni servizi locali, ad esempio il proxy ADFS o l'individuazione automatica di Exchange, possono ricevere richieste in ingresso sia dai servizi di Office 365 che dagli utenti da Internet. Per queste richieste, Office 365 avrà come destinazione lo stesso FQDN delle richieste degli utenti su Internet. Consentire le connessioni utente in ingresso da Internet a tali endpoint locali, forzando le connessioni di Office 365 all'uso di ExpressRoute, rappresenta una notevole complessità di routing. Per la maggior parte dei clienti, l'implementazione di scenari così complessi su ExpressRoute non è consigliata a causa di considerazioni operative. Questo sovraccarico aggiuntivo include la gestione dei rischi del routing asimmetrico e richiederà una gestione attentamente degli annunci e dei criteri di routing su più dimensioni.

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a>Aggiornare il piano della topologia di rete per mostrare come evitare le route asimmetriche
<a name="asymmetric"> </a>

Si desidera evitare il routing asimmetrico per garantire che gli utenti dell'organizzazione possano usare facilmente Office 365 e altri servizi importanti su Internet. Esistono due configurazioni comuni che causano il routing asimmetrico. È il momento giusto per esaminare la configurazione di rete che si prevede di usare e verificare se potrebbe esistere uno di questi scenari di routing asimmetrico.
  
Per iniziare, verranno esaminate alcune situazioni diverse associate al diagramma reticolare seguente. In questo diagramma, tutti i server che ricevono richieste in ingresso, ad esempio ADFS o i server ibridi locali, sono nel data center del New Jersey e sono annunciati su Internet.
  
1. Anche se la rete perimetrale è protetta, non è disponibile nat di origine per le richieste in ingresso.

2. I server nel data center del New Jersey sono in grado di visualizzare sia le route Internet che le route ExpressRoute.

![Panoramica della connettività ExpressRoute](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
Sono inoltre disponibili suggerimenti su come correggerli.
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a>Problema 1: connessione da cloud a locale tramite Internet
  
Il diagramma seguente illustra il percorso di rete asimmetrico intrapreso quando la configurazione di rete non fornisce NAT per le richieste in ingresso dal cloud Microsoft tramite Internet.
  
1. La richiesta in ingresso da Office 365 recupera l'indirizzo IP dell'endpoint locale dal DNS pubblico e invia la richiesta alla rete perimetrale.

2. In questa configurazione difettosa non è configurato o disponibile nat di origine nella rete perimetrale in cui viene inviato il traffico, con conseguente utilizzo dell'indirizzo IP di origine effettivo come destinazione di ritorno.

  - Il server della rete instrada il traffico di ritorno a Office 365 tramite qualsiasi connessione di rete ExpressRoute disponibile.

  - Il risultato è un percorso asimmetrico per il flusso verso Office 365, causando una connessione interrotta.

![ExpressRoute Asymetric routing problem 1](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a>Soluzione 1a: NAT di origine
  
La semplice aggiunta di un NAT di origine alla richiesta in ingresso risolve questa rete non configurata correttamente. In questo diagramma:
  
1. La richiesta in arrivo continua a entrare attraverso la rete perimetrale del data center del New Jersey. Questa volta è disponibile Source NAT.

2. La risposta dal server instrada di nuovo verso l'IP associato al NAT di origine anziché all'indirizzo IP originale, determinando la restituzione della risposta lungo lo stesso percorso di rete.

![Soluzione di routing ExpressRoute asymetric 1](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a>Soluzione 1b: ambito route
  
In alternativa, è possibile scegliere di non consentire l'annuncio dei prefissi BGP ExpressRoute, rimuovendo il percorso di rete alternativo per tali computer. In questo diagramma:
  
1. La richiesta in arrivo continua a entrare attraverso la rete perimetrale del data center del New Jersey. Questa volta i prefissi annunciati da Microsoft sul circuito ExpressRoute non sono disponibili per il data center del New Jersey.

2. La risposta del server instrada nuovamente verso l'IP associato all'indirizzo IP originale sull'unica route disponibile, determinando la restituzione della risposta lungo lo stesso percorso di rete.

![Soluzione di routing ExpressRoute asymetric 2](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a>Problema 2: connessione da cloud a locale tramite ExpressRoute
  
Il diagramma seguente illustra il percorso di rete asimmetrico effettuato quando la configurazione di rete non fornisce NAT per le richieste in ingresso dal cloud Microsoft tramite ExpressRoute.
  
1. La richiesta in ingresso da Office 365 recupera l'indirizzo IP da DNS e invia la richiesta alla rete perimetrale.

2. In questa configurazione difettosa non è configurato o disponibile nat di origine nella rete perimetrale in cui viene inviato il traffico, con conseguente utilizzo dell'indirizzo IP di origine effettivo come destinazione di ritorno.

  - Il computer nella rete instrada il traffico di ritorno a Office 365 tramite qualsiasi connessione di rete ExpressRoute disponibile.

  - Il risultato è una connessione asimmetrica a Office 365.

![ExpressRoute Asymetric routing problem 2](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a>Soluzione 2: NAT di origine
  
La semplice aggiunta di un NAT di origine alla richiesta in ingresso risolve questa rete non configurata correttamente. In questo diagramma:
  
1. La richiesta in arrivo continua a entrare attraverso la rete perimetrale del data center di New York. Questa volta è disponibile Source NAT.

2. La risposta dal server instrada di nuovo verso l'IP associato al NAT di origine anziché all'indirizzo IP originale, determinando la restituzione della risposta lungo lo stesso percorso di rete.

![Soluzione di routing ExpressRoute asymetric 3](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a>Verificare che la progettazione della rete abbia la simmetria del percorso

A questo punto, è necessario verificare in formato cartaceo che il piano di implementazione offre la simmetria del percorso per i diversi scenari in cui verrà utilizzato Office 365. Identificherai la route di rete specifica che dovrebbe essere intrapresa quando una persona usa funzionalità diverse del servizio. Dalla rete locale e dal routing WAN, ai dispositivi perimetrali, al percorso di connettività; ExpressRoute o Internet e alla connessione all'endpoint online.
  
È necessario eseguire questa operazione per tutti i servizi di rete di Office 365 precedentemente identificati come servizi che verranno adottati dall'organizzazione.
  
Aiuta a fare questo documento a piedi attraverso gli itinerari con una seconda persona. Spiegare loro da dove si prevede che ogni hop di rete otterrà la route successiva e assicurarsi di avere familiarità con i percorsi di routing. Tenere presente che ExpressRoute fornirà sempre una route con ambito maggiore agli indirizzi IP del server Microsoft, con un costo di route inferiore rispetto a una route predefinita internet.
  
### <a name="design-client-connectivity-configuration"></a>Progettare la configurazione della connettività client
<a name="asymmetric"> </a>

![Uso di file PAC con ExpressRoute](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
Se si usa un server proxy per il traffico associato a Internet, è necessario modificare i file PAC o di configurazione client per assicurarsi che i computer client sulla rete siano configurati correttamente per inviare il traffico ExpressRoute desiderato a Office 365 senza transitare il server proxy e che il traffico rimanente, incluso il traffico di Office 365, venga inviato al proxy pertinente. Leggere la guida sulla [gestione degli endpoint di Office 365,](https://aka.ms/manageo365endpoints) ad esempio i file PAC.
  
> [!NOTE]
> Gli endpoint cambiano frequentemente, ogni settimana. È consigliabile apportare modifiche solo in base ai servizi e alle funzionalità adottati dall'organizzazione per ridurre il numero di modifiche da apportare per rimanere al corrente. Prestare particolare attenzione alla data di validità nel feed RSS **in** cui vengono annunciate le modifiche e viene mantenuto un record di tutte le modifiche passate, gli indirizzi IP annunciati potrebbero non essere annunciati o rimossi dall'annuncio pubblicitario fino a quando non viene raggiunta la data di validità.
  
## <a name="build-your-deployment-and-testing-procedures"></a>Creare le procedure di distribuzione e test
<a name="testing"> </a>

Il piano di implementazione deve includere sia la pianificazione di test che la pianificazione del rollback. Se l'implementazione non funziona come previsto, il piano deve essere progettato per influire sul minor numero di persone prima di individuare i problemi. Di seguito sono riportati alcuni principi generali che il piano deve prendere in considerazione.
  
1. Eseguire l'onboarding del segmento di rete e del servizio utente per ridurre al minimo l'interruzione.

2. Pianificare il test delle route con traceroute e la connessione TCP da un host connesso a Internet separato.

3. Preferibilmente, il test dei servizi in ingresso e in uscita deve essere eseguito in una rete di test isolata con un tenant di Office 365 di prova.

      - In alternativa, i test possono essere eseguiti in una rete di produzione se il cliente non usa ancora Office 365 o è in fase pilota.

      - In alternativa, i test possono essere eseguiti durante un'interruzione di produzione che viene messa da parte solo per il test e il monitoraggio.

      - In alternativa, è possibile eseguire il test controllando le route per ogni servizio in ogni nodo di router di livello 3. Questo fall back deve essere utilizzato solo se non sono possibili altri test poiché la mancanza di test fisici introduce rischi.

### <a name="build-your-deployment-procedures"></a>Creare le procedure di distribuzione

Le procedure di distribuzione devono essere distribuite a piccoli gruppi di persone in fasi per consentire il testing prima della distribuzione in gruppi di persone più grandi. Di seguito sono riportati diversi modi per eseguire in fasi la distribuzione di ExpressRoute.
  
1. Configurare ExpressRoute con peering Microsoft e inoltrare gli annunci di route a un singolo host solo a scopo di test a fasi.

2. Annunciare le route alla rete ExpressRoute a un singolo segmento di rete ed espandere gli annunci di route in base al segmento o all'area di rete.

3. Se si distribuisce Office 365 per la prima volta, usare la distribuzione di rete ExpressRoute come progetto pilota per un numero limitato di persone.

4. Se si usano server proxy, è possibile configurare in alternativa un file PAC di test per indirizzare un numero limitato di persone a ExpressRoute con test e feedback prima di aggiungervi altri elementi.

Il piano di implementazione deve elencare tutte le procedure di distribuzione da eseguire o i comandi da usare per distribuire la configurazione di rete. Quando arriva il tempo di interruzione della rete, tutte le modifiche apportate devono essere del piano di distribuzione scritto scritto in anticipo e esaminato da un peer. Vedere le indicazioni sulla configurazione tecnica di ExpressRoute.
  
- Aggiornamento dei record TXT SPF se sono stati modificati gli indirizzi IP per i server locali che continueranno a inviare posta elettronica.

- Aggiornamento di eventuali voci DNS per i server locali se sono stati modificati indirizzi IP per supportare una nuova configurazione NAT.

- Assicurarsi di aver sottoscritto il feed RSS per le notifiche degli endpoint di Office 365 per mantenere eventuali configurazioni di routing o proxy.

Al termine della distribuzione di ExpressRoute, è necessario eseguire le procedure del piano di test. I risultati per ogni procedura devono essere registrati. È necessario includere le procedure per il rollback nell'ambiente di produzione originale nel caso in cui i risultati del piano di test indichino che l'implementazione non è riuscita.
  
### <a name="build-your-test-procedures"></a>Creare le procedure di test

Le procedure di test devono includere i test per ogni servizio di rete in ingresso e in uscita per Office 365 che verrà utilizzato ExpressRoute e quelli che non lo saranno. Le procedure devono includere il test da ogni percorso di rete univoco, inclusi gli utenti che non sono locali nella rete LAN aziendale.
  
Di seguito sono riportati alcuni esempi di attività di test.
  
1. Eseguire il ping dal router locale al router dell'operatore di rete.

2. Verificare che oltre 500 annunci di indirizzi IP di Office 365 e CRM Online siano ricevuti dal router locale.

3. Verificare che la NAT in ingresso e in uscita sia in funzione tra ExpressRoute e la rete interna.

4. Verificare che le route verso nat vengano annunciate dal router.

5. Verificare che ExpressRoute abbia accettato i prefissi annunciati.

      - Utilizzare il cmdlet seguente per verificare gli annunci di peering:

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. Verificare che l'intervallo IP NAT pubblico non sia annunciato a Microsoft tramite altri circuiti ExpressRoute o internet pubblici, a meno che non si tratta di un sottoinsieme specifico di un intervallo più ampio, come nell'esempio precedente.

7. I circuiti ExpressRoute sono associati e verificano che entrambe le sessioni BGP siano in esecuzione.

8. Configurare un singolo host all'interno del NAT e usare ping, tracert e tcpping per testare la connettività nel nuovo circuito all'host outlook.office365.com. In alternativa, è possibile utilizzare uno strumento come Wireshark o Microsoft Network Monitor 3.4 su una porta con mirroring a MSEE per verificare che sia possibile connettersi all'indirizzo IP associato a outlook.office365.com.

9. Verificare la funzionalità a livello di applicazione per Exchange Online.

  - Verificare che Outlook sia in grado di connettersi a Exchange Online e inviare/ricevere messaggi di posta elettronica.

  - Verificare che Outlook sia in grado di utilizzare la modalità online.

  - Testare la connettività degli smartphone e la funzionalità di invio/ricezione.

10. Testare la funzionalità a livello di applicazione per SharePoint Online

  - Testare il client di sincronizzazione di OneDrive for Business.

  - Testare l'accesso Web di SharePoint Online.

11. Testare la funzionalità a livello di applicazione per gli scenari di chiamata di Skype for Business:

  - Partecipare alla conferenza telefonica come utente autenticato [invito avviato dall'utente finale].

  - Invitare l'utente alla conferenza telefonica [invito inviato da MCU].

  - Partecipare alla conferenza come utente anonimo usando l'applicazione Web Skype for Business.

  - Partecipare alla chiamata dalla connessione pc cablata, dal telefono IP e dal dispositivo mobile.

  - Chiamata all'utente federato o Chiamata alla convalida PSTN: chiamata completata, qualità della chiamata accettabile, tempo di connessione accettabile.

  - Verificare che lo stato presenza per i contatti sia aggiornato per i membri del tenant e per gli utenti federati.

### <a name="common-problems"></a>Problemi comuni

Il routing asimmetrico è il problema di implementazione più comune. Ecco alcune fonti comuni da cercare:
  
- Utilizzo di una topologia di routing di rete aperta o piatta senza NAT di origine sul posto.

- Non utilizzare SNAT per instradare i servizi in ingresso tramite le connessioni Internet ed ExpressRoute.

- Non testare i servizi in ingresso su ExpressRoute in una rete di test prima della distribuzione su larga base.

## <a name="deploying-expressroute-connectivity-through-your-network"></a>Distribuzione della connettività ExpressRoute tramite la rete
<a name="testing"> </a>

Implementare gradualmente la distribuzione in un segmento della rete alla volta, stendando progressivamente la connettività a diverse parti della rete con un piano di rollback per ogni nuovo segmento di rete. Se la distribuzione è allineata a una distribuzione di Office 365, distribuire prima agli utenti pilota di Office 365 ed estendersi da qui.
  
Prima per il test e poi per la produzione:
  
- Eseguire i passaggi di distribuzione per abilitare ExpressRoute.

- Verificare che le route di rete siano come previsto.

- Eseguire test su ogni servizio in ingresso e in uscita.

- Eseguire il rollback in caso di problemi.

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a>Configurare una connessione di prova a ExpressRoute con un segmento di rete di test

Ora che hai completato il piano su carta, è il momento di testarlo su scala ridotta. In questo test verrà stabilita una singola connessione ExpressRoute con Peering Microsoft a una subnet di prova nella rete locale. È possibile configurare un tenant di [valutazione di Office 365](https://go.microsoft.com/fwlink/p/?LinkID=403802) con connettività da e verso la subnet di test e includere tutti i servizi in ingresso e in uscita che verranno inclusi nell'ambiente di produzione nella subnet di test. Configurare DNS per il segmento di rete di test e stabilire tutti i servizi in ingresso e in uscita. Eseguire il piano di test e assicurarsi di avere familiarità con il routing per ogni servizio e la propagazione della route.
  
### <a name="execute-the-deployment-and-test-plans"></a>Eseguire i piani di distribuzione e di test

Una volta completati gli elementi descritti in precedenza, controllare le aree completate e assicurarsi che il team li abbia esaminati prima di eseguire i piani di distribuzione e test.
  
- Elenco dei servizi in ingresso e in uscita coinvolti nella modifica della rete.

- Diagramma dell'architettura di rete globale che mostra sia l'uscita internet che le posizioni meet-me di ExpressRoute.

- Diagramma del routing di rete che mostra i diversi percorsi di rete utilizzati per ogni servizio distribuito.

- Un piano di distribuzione con la procedura per implementare le modifiche e il rollback, se necessario.

- Un piano di test per testare ogni servizio di rete e Office 365.

- Convalida cartacea completata delle route di produzione per i servizi in ingresso e in uscita.

- Test completato in un segmento di rete di test, incluso il test della disponibilità.

Scegliere una finestra di interruzione sufficientemente lunga da poter essere eseguita nell'intero piano di distribuzione e nel piano di test, ha a disposizione del tempo per la risoluzione dei problemi e il tempo necessario per il rollback, se necessario.
  
> [!CAUTION]
> A causa della natura complessa del routing su Internet ed ExpressRoute, è consigliabile aggiungere ulteriore tempo di buffer a questa finestra per gestire la risoluzione dei problemi di routing complesso.
  
### <a name="configure-qos-for-skype-for-business-online"></a>Configurare QoS per Skype for Business online

QoS è necessaria per ottenere i vantaggi vocali e per le riunioni per Skype for Business online. È possibile configurare QoS dopo aver garantito che la connessione di rete ExpressRoute non blocca alcun altro accesso al servizio Office 365. La configurazione per QoS è descritta nell'articolo [ExpressRoute e QoS in Skype for Business online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
## <a name="troubleshooting-your-implementation"></a>Risoluzione dei problemi relativi all'implementazione
<a name="troubleshooting"> </a>

Il primo punto da esaminare è la procedura descritta in questa guida all'implementazione, mancata nel piano di implementazione? Tornare indietro ed eseguire ulteriori test di rete di piccole dimensioni, se possibile, per replicare l'errore ed eseguirne il debug.
  
Identificare i servizi in ingresso o in uscita non riusciti durante il test. Ottenere in modo specifico gli indirizzi IP e le subnet per ognuno dei servizi che hanno avuto esito negativo. Procedere e illustrare il diagramma della topologia di rete su carta e convalidare il routing. Verificare in modo specifico dove viene annunciato il routing ExpressRoute, testarlo durante l'interruzione, se possibile, con le tracce.
  
Eseguire PSPing con una traccia di rete per ogni endpoint del cliente e valutare gli indirizzi IP di origine e di destinazione per verificare che siano nel modo previsto. Eseguire telnet su qualsiasi host di posta esposto sulla porta 25 e verificare che SNAT nasconde l'indirizzo IP di origine, se previsto.
  
Tenere presente che durante la distribuzione di Office 365 con una connessione ExpressRoute è necessario verificare che sia la configurazione di rete per ExpressRoute sia progettata in modo ottimale e che siano stati ottimizzati anche gli altri componenti della rete, ad esempio i computer client. Oltre a usare questa guida alla pianificazione per risolvere i problemi relativi ai passaggi che potrebbero non essere stati evasi, è stato scritto anche un piano per la risoluzione dei problemi relativi alle prestazioni [per Office 365.](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c)
  
Ecco un collegamento breve per tornare alla pagina: [https://aka.ms/implementexpressroute365](https://aka.ms/implementexpressroute365)
  
## <a name="related-topics"></a>Argomenti correlati

[Valutazione della connettività di rete di Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute per Office 365](azure-expressroute.md)
  
[Gestione di ExpressRoute per la connettività di Office 365](managing-expressroute-for-connectivity.md)
  
[Routing con ExpressRoute per Office 365](routing-with-expressroute.md)
  
[Pianificazione della rete con ExpressRoute per Office 365](network-planning-with-expressroute.md)
  
[Uso delle community BGP in ExpressRoute per scenari di Office 365](bgp-communities-in-expressroute.md)
  
[Qualità multimediale e prestazioni della connettività di rete in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Ottimizzazione della rete per Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute e QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flusso di chiamata con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)
  
[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)
  
[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Ottimizzazione delle prestazioni e della rete di Office 365](network-planning-and-performance.md)
