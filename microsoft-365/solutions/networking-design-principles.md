---
title: Networking up (to the cloud) - Punto di vista di un architetto
description: Informazioni su come ottimizzare la rete per la connettività cloud evitando le insidie più comuni.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 175903949b639740ad00b29013d5748b99bdb2de
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771848"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Networking up (to the cloud) - Punto di vista di un architetto

In questo articolo, [Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & Compliance Architect di Microsoft, descrive come ottimizzare la rete per la connettività cloud evitando le insidie più comuni. 

## <a name="about-the-author"></a>Informazioni sull'autore

![Ed Fisher photo](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Attualmente sono un principal technical specialist nell'area sud-orientale che si concentra sulla sicurezza & conformità. Ho lavorato con i clienti che si spostano in Office 365 negli ultimi 10 anni. Ho lavorato con negozi più piccoli con poche sedi in agenzie governative e aziende con milioni di utenti distribuiti in tutto il mondo e molti altri clienti in mezzo, con la maggior parte di decine di migliaia di utenti, più sedi in varie parti del mondo, la necessità di un livello superiore di sicurezza e una miriade di requisiti di conformità. Ho consentito a centinaia di aziende e milioni di utenti di passare al cloud in modo sicuro e sicuro.

Con un background negli ultimi 25 anni che include la sicurezza, l'infrastruttura e l'ingegneria di rete e dopo aver spostato due dei miei precedenti dipendenti in Office 365 prima di entrare a far parte di Microsoft, sono stato dalla tua parte del tavolo per un numero molto lungo di volte e ricorda cosa succede. Anche se nessun cliente è sempre lo stesso, la maggior parte ha esigenze simili e quando si utilizza un servizio standardizzato come qualsiasi piattaforma SaaS o PaaS, gli approcci migliori tendono a essere gli stessi.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>Non si tratta della rete, ma del modo in cui la si usa (in modo erre).

Indipendentemente dal numero di volte in cui accade, non manca mai di stupore di come i team di sicurezza creativi e i team di rete provano a capire come pensano di connettersi ai servizi cloud Microsoft.  Esiste sempre un criterio di sicurezza, uno standard di conformità o un modo migliore in cui insistono nell'usare, senza essere disposti a partecipare a una conversazione su ciò che stanno cercando di realizzare o su come sono migliori, più semplici, più efficienti e più efficienti. 

Quando questo tipo di cosa viene inoltrata a me, di solito sono disposto a affrontare la sfida e a illustrare le modalità e i motivi e a portarli dove devono essere. Ma se sono completamente sincero, devo condividere che a volte voglio semplicemente consentire loro di fare ciò che vogliono e tornare a dire che ti ho detto che quando alla fine lo concederanno non funziona. A volte è possibile eseguire questa operazione, ma *non è così.* Quello che devo fare è cercare di spiegare tutto ciò che includerò in questo post. Indipendentemente dal ruolo dell'utente, se l'organizzazione vuole usare i servizi cloud Microsoft, è probabile che ciò che segue possa essere utile.

## <a name="guiding-principles"></a>Principi guida

Iniziamo con alcune regole di base relative a ciò che stiamo facendo qui. We are discussing how to securely connect to cloud services to ensure the minimum complexity, and the maximum performance, while maintaining real security. Nessuno di questi elementi è contrario a tutto ciò, anche se tu o il tuo cliente non userà il server proxy preferito per tutto.

- **Solo perché puoi,** non significa che dovresti : o parafrasare il dr. Ian Malcolm dal film Jurassic Park "... Sì, sì, ma il team di sicurezza era così preoccupata di sapere se potevano o meno non fermarsi a pensare se dovevano farlo."
- **La sicurezza non significa complessità:** non sei più sicuro solo perché spendi più denaro, passi attraverso più dispositivi o fai clic su più pulsanti.
- **Office 365 è** accessibile tramite Internet: ma non è la stessa cosa di Office 365 è Internet. Si tratta di un servizio SaaS gestito da Microsoft e gestito dall'utente. A differenza dei siti Web visitati su Internet, in realtà si arriva a sbirciare dietro le tende e si possono applicare i controlli necessari per soddisfare i criteri e gli standard di conformità, purché si comprendi che, anche se è possibile raggiungere gli obiettivi, potrebbe essere sufficiente farlo in modo diverso.
- I punti di **chokepoint** sono un buon punto di interruzione localizzato: tutti vogliono sempre eseguire il backhaul di tutto il traffico Internet per tutti gli utenti fino a un punto centrale, in genere in modo che possano monitorarlo e applicare i criteri, ma spesso perché è più conveniente del provisioning dell'accesso a Internet in tutte le loro posizioni o è proprio come lo fanno. Ma questi chokepoint sono esattamente questo... punti in cui il traffico si intasa. Non c'è nulla di sbagliato nell'impedire agli utenti di accedere a Video di Instagram o di streaming per i gatti, ma non considerare il traffico delle applicazioni aziendali cruciali allo stesso modo.
- Se DNS non è soddisfatto, non **c'è** niente di meglio: la rete più progettata può essere ostacolata da UN DNS di qualità scarsa, sia che si utilizzino richieste a server in altre aree del mondo o che utilizzino i server DNS dell'ISP o altri server DNS pubblici che memorizzano nella cache le informazioni sulla risoluzione DNS.
- Solo perché è così che è stato **fatto,** non significa che sia così che si dovrebbe farlo ora: la tecnologia cambia costantemente e Office 365 non fa eccezione. L'applicazione di misure di sicurezza sviluppate e distribuite per i servizi locali o per controllare la navigazione web non fornirà lo stesso livello di garanzia della sicurezza e può avere un impatto negativo significativo sulle prestazioni.
- **Office 365 è** stato creato per l'accesso tramite Internet: in breve. Indipendentemente da ciò che si vuole fare tra gli utenti e il perimetro, il traffico continua a passare attraverso Internet una volta che lascia la rete e prima che venga inserito nella nostra. Anche se si usa Azure ExpressRoute per instradare il traffico sensibile alla latenza dalla rete direttamente alla nostra, è assolutamente necessaria la connettività Internet. Accettarla. Non sorrenderlo.

## <a name="where-bad-choices-are-often-made"></a>Dove spesso vengono effettuate scelte non valide

Anche se ci sono molti luoghi in cui vengono prese decisioni sbagliate in nome della sicurezza, queste sono quelle che incontro più spesso con i clienti. Molte conversazioni dei clienti coinvolgono tutti questi elementi contemporaneamente.

### <a name="insufficient-resources-at-the-edge"></a>Risorse insufficienti nel perimetro

Pochi clienti stanno distribuendo ambienti greenfield e hanno anni di esperienza nel funzionamento degli utenti e nell'uscita da Internet. Sia che i clienti dispongono di server proxy o consentano l'accesso diretto e semplicemente il traffico nat in uscita, lo fanno da anni e non considerano quanto in più inizieranno a passare attraverso il proprio perimetro mentre spostano le applicazioni interne tradizionalmente nel cloud.

La larghezza di banda è sempre un problema, ma i dispositivi NAT potrebbero non avere una potenza sufficiente per gestire l'aumento del carico e potrebbero iniziare a chiudere prematuramente le connessioni per liberare risorse. La maggior parte del software client che si connette a Office 365 prevede connessioni persistenti e un utente che utilizza completamente Office 365 può avere 32 o più connessioni simultanee. Se il dispositivo NAT li rilascia prematuramente, queste app potrebbero non rispondere quando tentano di usare le connessioni che non sono più presenti. Quando si arrendono e provano a stabilire nuove connessioni, mettono ancora più carico sulla marcia di rete.

### <a name="localized-breakout"></a>Breakout localizzato

Tutto il resto di questo elenco si presenta con una cosa: uscire dalla rete e accedere alla rete il prima possibile. Il backhauling del traffico degli utenti verso un punto di uscita centrale, soprattutto quando tale punto di uscita si trova in un'area diversa da quella in cui si trova l'utente, introduce una latenza non necessaria e influisce sia sull'esperienza client che sulla velocità di download. Microsoft ha punti di presenza in tutto il mondo con front-end per tutti i servizi e  il peering stabiliti praticamente con tutti i principali ISP, quindi il routing del traffico degli utenti in uscita in locale assicura che venga rapidamente inserito nella rete con latenza minima.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>Il traffico di risoluzione DNS deve seguire il percorso di uscita da Internet

Naturalmente, per trovare qualsiasi endpoint, un client deve usare DNS. I server DNS di Microsoft valutano l'origine delle richieste DNS per garantire la restituzione della risposta, in termini Internet, più vicina all'origine della richiesta. Assicurarsi che il DNS sia configurato in modo che le richieste di risoluzione dei nomi esercitino lo stesso percorso del traffico degli utenti, per non concedere loro l'uscita locale, ma verso un endpoint in un'altra area geografica. Ciò significa consentire ai server DNS locali di "passare alla radice" anziché inoltrare ai server DNS nei data center remoti. E fai attenzione ai servizi DNS pubblici e privati, che possono memorizzare nella cache i risultati di una parte del mondo e servirli alle richieste da altre parti del mondo.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Per proxy o meno, questa è la domanda

Uno dei primi aspetti da considerare è se eseguire il proxy delle connessioni degli utenti a Office 365. Questo è facile; non proxy. Office 365 è accessibile tramite Internet, ma non è Internet. Si tratta di un'estensione dei servizi di base e deve essere trattata come tale. Tutto ciò che potrebbe essere necessario eseguire un proxy, ad esempio dlp o antimalware o ispezione del contenuto, è già disponibile nel servizio e può essere utilizzato su vasta scala e senza dover crittografare le connessioni crittografate con TLS. Tuttavia, se vuoi veramente determinare il traffico proxy che non puoi controllare in altro modo, presta attenzione alle nostre indicazioni e alle [https://aka.ms/pnc](https://aka.ms/pnc) categorie di traffico in [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) . Sono disponibili tre categorie di traffico per Office 365. Optimize e Allow devono andare direttamente e ignorare il proxy. Il valore predefinito può essere proxy. I dettagli sono in questi documenti... leggerli.

La maggior parte dei clienti che insistono sull'uso di un proxy, quando osservano effettivamente ciò che stanno facendo, si rendono conto che quando il client effettua una richiesta HTTP CONNECT al proxy, il proxy è ora solo un router aggiuntivo dispendioso. I protocolli in uso, ad esempio MAPI e RTC, non sono nemmeno protocolli che i proxy Web comprendono, quindi anche con la comprovazione tls non si riceve alcuna sicurezza aggiuntiva. Si *riceve* una latenza aggiuntiva. Per [https://aka.ms/pnc](https://aka.ms/pnc) altre informazioni, incluse le categorie Optimize, Allow e Default per il traffico di Microsoft 365.

Infine, considera l'impatto complessivo sul proxy e la risposta corrispondente per gestire tale impatto. Poiché vengono effettuate sempre più connessioni tramite il proxy, potrebbe diminuire il fattore di scala TCP in modo che non sia necessario bufferare così tanto traffico. Ho visto i clienti in cui i loro proxy erano così sovraccarichi che usavano un fattore di scala 0. Poiché fattore di scala è un valore esponenziale e ci piace usare 8, ogni riduzione del valore del fattore di scala è un enorme impatto negativo sulla velocità effettiva.

Ispezione TLS significa SICUREZZA! Ma non proprio! Molti clienti con proxy vogliono usarli per esaminare tutto il traffico e ciò significa che TLS "interrompi e ispeziona". Quando si esegue questa operazione per un sito Web a cui si accede tramite HTTPS (nonostante i problemi di privacy), il proxy potrebbe doversi fare per 10 o anche 20 flussi simultanei per alcune centinaia di millisecondi. Se è coinvolto un download di grandi dimensioni o un video, una o più di queste connessioni possono durare molto più a lungo, ma nel complesso, la maggior parte di queste connessioni stabilisce, trasferisce e chiude molto rapidamente. L'interruzione e l'ispezione implicano che il proxy deve eseguire il doppio del lavoro. Per ogni connessione dal client al proxy, il proxy deve anche effettuare una connessione separata all'endpoint. Quindi, 1 diventa 2, 2 diventa 4, 32 diventa 64...vedi dove devo andare? È probabile che la soluzione proxy sia stata ridimensionata correttamente per la navigazione web tipica, ma quando si tenta di eseguire la stessa operazione per le connessioni client a Office 365, il numero di connessioni simultanee di lunga durata può essere maggiore di quello per cui si è ridimensionato.

### <a name="streaming-isnt-important-except-that-it-is"></a>Lo streaming non è importante, tranne per il *fatto che è*

Gli unici servizi in Office 365 che usano UDP sono Skype (presto ritirato) e Microsoft Teams. Teams usa UDP per il traffico di streaming, inclusa la condivisione di audio, video e presentazioni. Il traffico di streaming è in tempo reale, ad esempio quando si ha una riunione online con funzionalità vocali, video e presentazione di mazzi o durante l'esecuzione di dimostrazioni. Questi usano UDP perché se i pacchetti vengono eliminati o arrivano fuori ordine, l'utente praticamente non è visibile e lo stream può continuare.

Quando non si consente il traffico UDP in uscita dai client al servizio, possono eseguire il fall back all'uso di TCP. Tuttavia, se un pacchetto TCP viene *eliminato,* tutto si arresta fino alla scadenza del timeout di ritrasmissione (RTO) e il pacchetto mancante può essere ritrasmesso. Se un pacchetto arriva fuori ordine, tutto si arresta fino all'arrivo degli altri pacchetti e può essere riassemblato nell'ordine. Entrambi conducono a problemi percepibili nell'audio (ricorda Max Headroom?) e video (hai fatto clic su qualcosa... oh, eccolo) e portare a prestazioni scarse e a un'esperienza utente negativa. E ricorda cosa ho descritto sopra sui proxy? Quando si impone a un client di Teams di utilizzare un proxy, è necessario forzarlo per l'utilizzo di TCP. A questo punto si stanno causando due volte effetti negativi sulle prestazioni.

### <a name="split-tunneling-may-seem-scary"></a>Lo split tunneling può sembrare un problema

Ma non lo è. Tutte le connessioni a Office 365 sono su TLS. Microsoft offre TLS 1.2 da molto tempo e presto verranno disabilitate le versioni precedenti perché i client legacy le usano ancora e questo rappresenta un rischio.

Forzare una connessione TLS, o 32 di esse, per passare attraverso una VPN prima di passare al servizio non aggiunge sicurezza. Aggiunge latenza e riduce la velocità effettiva complessiva. In alcune soluzioni VPN, forza persino UDP a eseguire il tunneling tramite TCP, che di nuovo avrà un impatto molto negativo sul traffico di streaming. E, a meno che non si stia eseguendo l'ispezione TLS, non c'è alcun svantaggio, tutto negativo. Un tema molto comune tra i clienti, ora che la maggior parte della forza lavoro è remota, è che vedono un impatto significativo sulla larghezza di banda e sulle prestazioni dal fatto che tutti gli utenti si connettono utilizzando una VPN, invece di configurare lo split tunneling per l'accesso agli endpoint di [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories)di categoria Optimize.

È facile risolvere il problema di split tunneling ed è consigliabile farlo. Per altre informazioni, consultare Ottimizzare la connettività [di Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)per gli utenti remoti tramite split tunneling vpn.

## <a name="the-sins-of-the-past"></a>I sins del passato

Molte volte, il motivo per cui vengono effettuate scelte sbagliate deriva da una combinazione di (1) che non sanno come funziona il servizio, (2) che provano a rispettare i criteri aziendali scritti prima di adottare il cloud e (3) team di sicurezza che potrebbero non essere facilmente consapevoli che esiste più di un modo per raggiungere i propri obiettivi. Probabilmente quanto sopra e i collegamenti seguenti saranno utili per il primo. Potrebbe essere necessaria una sponsorizzazione esecutiva per superare il secondo. La gestione degli obiettivi dei criteri di sicurezza, anziché dei relativi metodi, è utile per il terzo. Dall'accesso condizionale alla moderazione del contenuto, dalla prevenzione della perdita dei dati alla protezione delle informazioni, dalla convalida degli endpoint alle minacce zero-day: qualsiasi obiettivo finale che può essere raggiunto da un criterio di sicurezza ragionevole può essere raggiunto con ciò che è disponibile in Office 365 e senza alcuna dipendenza dall'ingranaggio di rete locale, dai tunnel VPN forzati e dall'interruzione e ispezione di TLS.

In altri casi, l'hardware ridimensionato e acquistato prima che l'organizzazione inizia a passare al cloud non può semplicemente essere ridimensionato per gestire i nuovi modelli e carichi di traffico. Se è effettivamente necessario instradare tutto il traffico attraverso un singolo punto di uscita e/o proxy, prepararsi ad aggiornare le apparecchiature di rete e la larghezza di banda di conseguenza. Monitora attentamente l'utilizzo di entrambi, perché l'esperienza non diminuisce lentamente con l'onboardamento di un numero maggiore di utenti. Tutto andrà bene fino a quando non viene raggiunto il punto di puntamento, quindi tutti ne risentiranno.

## <a name="exceptions-to-the-rules"></a>Eccezioni alle regole

Se l'organizzazione richiede restrizioni [tenant,](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)è necessario usare un proxy con interruzione TLS e ispezionare per forzare il traffico attraverso il proxy, ma non è necessario forzare tutto il traffico attraverso di esso.  Non si tratta di una proposta tutto o niente, quindi presta attenzione a ciò che deve essere modificato dal proxy.

Se vuoi consentire lo split tunneling ma anche usare un proxy per il traffico Web generale, assicurati che il file PAC definirà cosa deve essere diretto e come definire il traffico interessante per ciò che passa attraverso il tunnel VPN. Offriamo file PAC di esempio [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) per semplificarne la gestione.

## <a name="conclusion"></a>Conclusione

Decine di migliaia di organizzazioni, tra cui quasi tutte le fortune 500, usano Office 365 ogni giorno per le loro funzioni cruciali. Lo fanno in modo sicuro e lo fanno tramite Internet.

Indipendentemente dagli obiettivi di sicurezza in gioco, esistono modi per realizzarli che non richiedono connessioni VPN, server proxy, TLS break and inspect o uscita centralizzata di Internet per far uscire il traffico degli utenti dalla rete e accedere alla rete il prima possibile, il che offre le migliori prestazioni, indipendentemente dal fatto che la rete sia la sede aziendale, un ufficio remoto o l'utente che lavora a casa. Le linee guida si basano su come vengono creati i servizi di Office 365 e per garantire un'esperienza utente sicura ed performante.

## <a name="further-reading"></a>Ulteriori letture

[Principi di connettività di rete di Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[URL e intervalli di indirizzi IP per Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Gestione degli endpoint di Office 365](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints)

[Servizio Web per URL e indirizzi IP di Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-ip-web-service)

[Valutazione della connettività di rete di Office 365](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[Ottimizzazione delle prestazioni e della rete di Office 365](https://docs.microsoft.com/microsoft-365/enterprise/network-planning-and-performance)

[Valutazione della connettività di rete di Office 365](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](https://docs.microsoft.com/microsoft-365/enterprise/performance-tuning-using-baselines-and-history)

[Piano di risoluzione dei problemi di prestazioni per Office 365](https://docs.microsoft.com/microsoft-365/enterprise/performance-troubleshooting-plan)

[Reti per la distribuzione di contenuti](https://docs.microsoft.com/microsoft-365/enterprise/content-delivery-networks)

[Test di connettività di Microsoft 365](https://connectivity.office.com/)

[Come Microsoft sviluppa la sua rete globale veloce e affidabile](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog di rete di Office 365](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Connettività di Office 365 per utenti remoti che utilizzano split tunneling VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)


