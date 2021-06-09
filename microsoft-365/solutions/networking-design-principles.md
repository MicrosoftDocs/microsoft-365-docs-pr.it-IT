---
title: Networking up (to the cloud) - Punto di vista di un architetto
description: Scopri come ottimizzare la rete per la connettività cloud evitando le insidie più comuni.
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
ms.openlocfilehash: 7de9aec29b0a57e85e3539fc2e99384de545c52a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904637"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Networking up (to the cloud) - Punto di vista di un architetto

In questo articolo, [Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & Compliance Architect di Microsoft, descrive come ottimizzare la rete per la connettività cloud evitando le insidie più comuni. 

## <a name="about-the-author"></a>Informazioni sull'autore

![Foto di Ed Fisher](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Attualmente sono uno specialista tecnico principale nell'area sudorientale concentrandosi sulla sicurezza & conformità. Ho lavorato con i clienti che si spostano Office 365 negli ultimi 10 anni. Ho lavorato con negozi più piccoli con una serie di sedi verso agenzie governative e aziende con milioni di utenti distribuiti in tutto il mondo e molti altri clienti in mezzo, con la maggior parte di decine di migliaia di utenti, più sedi in varie parti del mondo, la necessità di un maggiore livello di sicurezza e una serie di requisiti di conformità. Ho aiutato centinaia di aziende e milioni di utenti a passare al cloud in modo sicuro e sicuro.

Con uno sfondo negli ultimi 25 anni che include la sicurezza, l'infrastruttura e l'ingegneria di rete e dopo aver spostato due dei miei precedenti dipendenti a Office 365 prima di entrare a far parte di Microsoft, sono stato dalla tua parte del tavolo un sacco di volte e ricorda cosa significa. Anche se nessun cliente è sempre lo stesso, la maggior parte ha esigenze simili e quando si utilizza un servizio standardizzato come qualsiasi piattaforma SaaS o PaaS, gli approcci migliori tendono a essere gli stessi.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>Non è la rete, ma il modo in cui la si usa (mis)!

Indipendentemente dal numero di volte in cui accade, non manca mai di stupirmi del modo in cui i team creativi di sicurezza e i team di rete cercano di capire come pensano di connettersi ai servizi cloud Microsoft.  C'è sempre qualche criterio di sicurezza, uno standard di conformità o un modo migliore per insistere sull'uso, senza essere disposti a partecipare a una conversazione su ciò che stanno cercando di realizzare o su come sono migliori, più facili, più efficienti e più efficienti. 

Quando questo tipo di cose viene inoltrato a me, in genere sono disposto a prendere la sfida e a illustrare le modalità e i motivi e a portarli dove devono essere. Ma se sono completamente franco, devo condividere che a volte voglio semplicemente lasciare che facciano quello che vogliono, e tornare a dire che ti ho detto così quando alla fine concederanno che non funziona. È possibile che a volte si desideri farlo, ma *non è così.* Quello che faccio è cercare di spiegare tutto ciò che includerò in questo post. Indipendentemente dal ruolo, se l'organizzazione vuole usare i servizi cloud Microsoft, è probabile che ci sia una certa sapienza in ciò che segue che può aiutarti.

## <a name="guiding-principles"></a>Principi guida

Iniziamo con alcune regole di base relative a ciò che stiamo facendo qui. Stiamo discutendo su come connettersi in modo sicuro ai servizi cloud per garantire la complessità minima e le prestazioni massime, pur mantenendo una sicurezza reale. Nessuno dei seguenti elementi è contrario a tutto ciò, anche se tu o il tuo cliente non userà il server proxy preferito per tutto.

- **Solo perché puoi, non** significa che dovresti : O parafrasare il dr. Ian Malcolm dal film Jurassic Park "... Sì, sì, ma il team di sicurezza si preoccupava così tanto del fatto che non si fermavano a pensare se dovevano farlo."
- **La sicurezza non significa complessità:** non sei più sicuro solo perché spendi più denaro, instradi più dispositivi o fai clic su più pulsanti.
- **Office 365 è possibile accedere** tramite Internet: ma non è la stessa cosa Office 365 internet. Si tratta di un servizio SaaS gestito da Microsoft e gestito dall'utente. A differenza dei siti Web visitati su Internet, in realtà si arriva a sbirciare dietro il sipario e si possono applicare i controlli necessari per soddisfare i criteri e gli standard di conformità, purché si comprendi che, sebbene sia possibile raggiungere gli obiettivi, potrebbe essere sufficiente farlo in modo diverso.
- **Chokepoints are bad, localized breakouts are good:** All always wants to backhaul all their Internet traffic for all their users to some central point, usually so they can monitor it and enforce policy, but often because it's either cheaper than provisioning Internet access in all their locations, or it's just how they do it. Ma questi punti di chokepoint sono esattamente questo... punti in cui il traffico si affolla. Non c'è nulla di sbagliato nel impedire agli utenti di accedere a Instagram o trasmettere video di gatti, ma non considerare il traffico delle applicazioni aziendali mission-critical nello stesso modo.
- Se DNS non è soddisfatto, non **c'è** niente di meglio: la rete progettata al meglio può essere ostacolata da UN DNS di qualità scarsa, sia che si tratta di un'operazione che si verifica recintando le richieste ai server in altre aree del mondo o utilizzando i server DNS dell'ISP o altri server DNS pubblici che memorizzano nella cache le informazioni sulla risoluzione DNS.
- Solo perché è così che hai usato per **farlo,** non significa che sia così che dovresti farlo ora: la tecnologia cambia costantemente e Office 365 non fa eccezione. L'applicazione di misure di sicurezza sviluppate e distribuite per i servizi locali o per controllare la navigazione web non fornirà lo stesso livello di garanzia della sicurezza e può avere un impatto negativo significativo sulle prestazioni.
- **Office 365 è stato creato per l'accesso tramite Internet:** è tutto in poche parole. Indipendentemente da ciò che si desidera fare tra gli utenti e il perimetro, il traffico continua a passare attraverso Internet una volta che lascia la rete e prima che venga inserito nella nostra. Anche se si usa Azure ExpressRoute per instradare un traffico sensibile alla latenza dalla rete direttamente alla nostra, la connettività Internet è assolutamente necessaria. Accettalo. Non tralasci.

## <a name="where-bad-choices-are-often-made"></a>Dove spesso vengono effettuate scelte non valide

Anche se ci sono molti luoghi in cui vengono prese decisioni sbagliate in nome della sicurezza, queste sono quelle che incontro più spesso con i clienti. Molte conversazioni dei clienti coinvolgono tutti questi elementi contemporaneamente.

### <a name="insufficient-resources-at-the-edge"></a>Risorse insufficienti nel perimetro

Pochi clienti distribuiscono ambienti greenfield e hanno anni di esperienza nel funzionamento degli utenti e nell'uscita da Internet. Sia che i clienti dispongono di server proxy o consentano l'accesso diretto e semplicemente il traffico nat in uscita, lo fanno da anni e non considerano quanto di più inizieranno a scorrere attraverso il proprio perimetro mentre spostano le applicazioni tradizionalmente interne nel cloud.

La larghezza di banda è sempre un problema, ma i dispositivi NAT potrebbero non avere abbastanza potenza per gestire l'aumento del carico e potrebbero iniziare a chiudere prematuramente le connessioni per liberare risorse. La maggior parte del software client che si connette a Office 365 prevede connessioni persistenti e un utente che utilizza completamente Office 365 può avere 32 o più connessioni simultanee. Se il dispositivo NAT li rilascia prematuramente, tali app potrebbero non rispondere quando tentano di usare le connessioni che non sono più presenti. Quando si arrendono e provano a stabilire nuove connessioni, mettono ancora più carico sul dispositivo di rete.

### <a name="localized-breakout"></a>Breakout localizzato

Tutto il resto dell'elenco è una cosa: uscire dalla rete e accedere alla nostra il più rapidamente possibile. Il backhauling del traffico degli utenti verso un punto di uscita centrale, soprattutto quando il punto di uscita si trova in un'altra area rispetto agli utenti, introduce una latenza non necessaria e influisce sia sull'esperienza client che sulla velocità di download. Microsoft ha punti di presenza in tutto il mondo con front-end per tutti i nostri servizi  e peering stabiliti con praticamente tutti i principali ISP, quindi il routing del traffico degli utenti in locale assicura che venga rapidamente inserito nella rete con latenza minima.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>Il traffico di risoluzione DNS deve seguire il percorso di uscita da Internet

Naturalmente, perché un client trovi qualsiasi endpoint, deve usare DNS. I server DNS di Microsoft valutano l'origine delle richieste DNS per garantire la restituzione della risposta, in termini Internet, più vicina all'origine della richiesta. Assicurati che il DNS sia configurato in modo che le richieste di risoluzione dei nomi esercitino lo stesso percorso del traffico degli utenti, per non concedere loro l'uscita locale, ma a un endpoint in un'altra area. Ciò significa consentire ai server DNS locali di "passare alla radice" anziché inoltrare ai server DNS nei data center remoti. Fai attenzione ai servizi DNS pubblici e privati, che possono memorizzare nella cache i risultati di una parte del mondo e servirli alle richieste provenienti da altre parti del mondo.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Per eseguire il proxy o meno, questa è la domanda

Uno dei primi aspetti da considerare è se eseguire il proxy delle connessioni degli utenti Office 365. Questo è facile; non proxy. Office 365 si accede tramite Internet, ma non è Internet. Si tratta di un'estensione dei servizi di base e deve essere trattata come tale. Qualsiasi operazione che potrebbe essere necessaria per un proxy, ad esempio DLP o antimalware o ispezione del contenuto, è già disponibile nel servizio e può essere utilizzata su larga scala e senza dover crittografare le connessioni crittografate con TLS. Tuttavia, se vuoi veramente determinare il traffico che non puoi controllare in altro modo, presta attenzione alle nostre indicazioni e alle [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) categorie di traffico in [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) . Abbiamo tre categorie di traffico per Office 365. Optimize e Allow dovrebbero andare direttamente e ignorare il proxy. Il valore predefinito può essere proxy. I dettagli sono in questi documenti... leggerli.

La maggior parte dei clienti che insistono sull'utilizzo di un proxy, quando osservano effettivamente cosa stanno facendo, si rendono conto che quando il client effettua una richiesta HTTP CONNECT al proxy, il proxy è ora solo un costoso router aggiuntivo. I protocolli in uso, ad esempio MAPI e RTC, non sono nemmeno protocolli che i proxy Web comprendono, quindi anche con tls cracking non si riceve alcuna sicurezza aggiuntiva. Si *sta ricevendo* una latenza aggiuntiva. Per [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) altre informazioni, vedi le categorie Optimize, Allow e Default per Microsoft 365 traffico.

Infine, considerare l'impatto complessivo sul proxy e la risposta corrispondente per gestire tale impatto. Poiché vengono effettuate sempre più connessioni tramite il proxy, è possibile che il fattore di scala TCP diminuisca in modo che non sia necessario bufferare così tanto traffico. Ho visto clienti in cui i proxy erano così sovraccaricati che usavano un fattore di scala 0. Poiché Fattore di scala è un valore esponenziale e ci piace usare 8, ogni riduzione del valore del fattore di scala è un enorme impatto negativo sulla velocità effettiva.

Tls Inspection significa SICUREZZA! Ma non proprio! Molti clienti con proxy vogliono usarli per controllare tutto il traffico e questo significa che TLS "interrompe e ispeziona". Quando si esegue questa operazione per un sito Web a cui si accede tramite HTTPS (problemi di privacy nonostante) il proxy potrebbe doversi eseguire per 10 o anche 20 flussi simultanei per alcune centinaia di millisecondi. Se è coinvolto un download di grandi dimensioni o un video, una o più di queste connessioni possono durare molto più a lungo, ma nel complesso, la maggior parte di queste connessioni stabilisce, trasferisce e chiude molto rapidamente. L'interruzione e l'ispezione significa che il proxy deve eseguire il doppio del lavoro. Per ogni connessione dal client al proxy, il proxy deve anche effettuare una connessione separata all'endpoint. Quindi, 1 diventa 2, 2 diventa 4, 32 diventa 64...vedi dove sto andando? È probabile che la soluzione proxy sia stata ridimensionata correttamente per la navigazione web tipica, ma quando si tenta di eseguire la stessa operazione per le connessioni client a Office 365, il numero di connessioni contemporanee di lunga durata può essere di ordine di grandezza superiore a quello per cui si è ridimensionato.

### <a name="streaming-isnt-important-except-that-it-is"></a>Lo streaming non è importante, tranne che *è*

Gli unici servizi in Office 365 che utilizzano UDP sono Skype (presto ritirati) e Microsoft Teams. Teams udp per il traffico di streaming, tra cui la condivisione di audio, video e presentazioni. Il traffico di streaming è in tempo reale, ad esempio quando si ha una riunione online con voce, video e presentazione di mazzi o durante l'esecuzione di dimostrazioni. Questi usano UDP perché se i pacchetti vengono eliminati o arrivano fuori ordine, è praticamente impercettibile dall'utente e il flusso può semplicemente continuare.

Quando non si consente il traffico UDP in uscita dai client al servizio, possono eseguire il fall back all'utilizzo di TCP. Tuttavia, se un pacchetto TCP viene *eliminato,* tutto si arresta fino alla scadenza del timeout di ritrasmissione (RTO) e il pacchetto mancante può essere ritrasmesso. Se un pacchetto arriva fuori ordine, tutto si arresta fino all'arrivo degli altri pacchetti e può essere riassemblato nell'ordine. Entrambi portano a problemi percepibili nell'audio (ricorda Max Headroom?) e video (hai fatto clic su qualcosa... oh, eccolo) e portare a prestazioni scarse e a un'esperienza utente negativa. E ti ricordi cosa ho messo sopra sui proxy? Quando si forza un Teams client a utilizzare un proxy, è necessario forzarlo a utilizzare TCP. Quindi ora stai causando un impatto negativo sulle prestazioni due volte.

### <a name="split-tunneling-may-seem-scary"></a>Lo split tunneling può sembrare spaventoso

Ma non lo è. Tutte le connessioni a Office 365 sono su TLS. Abbiamo offerto TLS 1.2 da un po' di tempo e presto verranno disabilitate le versioni precedenti perché i client legacy le usano ancora e questo è un rischio.

Forzare una connessione TLS, o 32 di loro, per passare attraverso una VPN prima che poi vadano al servizio non aggiunge sicurezza. Aggiunge latenza e riduce la velocità effettiva complessiva. In alcune soluzioni VPN, forza persino UDP a eseguire il tunneling attraverso TCP, che di nuovo avrà un impatto molto negativo sul traffico di streaming. E, a meno che non si stia eseguendo l'ispezione TLS, non c'è alcun lato positivo, tutto negativo. Un tema molto comune tra i clienti, ora che la maggior parte della forza lavoro è remota, è che stanno vedendo un impatto significativo sulla larghezza di banda e sulle prestazioni dal fatto che tutti gli utenti si connettono utilizzando una VPN, invece di configurare il split tunneling per l'accesso agli [endpoint](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)di Office 365 di categoria Optimize.

È facile eseguire lo split tunneling ed è consigliabile farlo. Per ulteriori informazioni, vedere Ottimizzare la connettività Office 365 per gli utenti [remoti tramite split tunneling VPN.](../enterprise/microsoft-365-vpn-split-tunnel.md)

## <a name="the-sins-of-the-past"></a>I peccati del passato

Molte volte, il motivo per cui vengono effettuate scelte sbagliate deriva da una combinazione di (1) che non sanno come funziona il servizio, (2) cercando di rispettare i criteri aziendali scritti prima di adottare il cloud e (3) team di sicurezza che potrebbero non essere facilmente convinti che esiste più di un modo per raggiungere i propri obiettivi. Si spera che quanto sopra e i collegamenti seguenti aiuteranno con il primo. La sponsorizzazione esecutiva potrebbe essere necessaria per superare il secondo. La gestione degli obiettivi dei criteri di sicurezza, anziché dei relativi metodi, aiuta con il terzo. Dall'accesso condizionale alla moderazione del contenuto, dalla prevenzione della perdita dei dati alla protezione delle informazioni, dalla convalida degli endpoint alle minacce zero-day: qualsiasi obiettivo finale di un criterio di sicurezza ragionevole può essere raggiunto con ciò che è disponibile in Office 365 e senza alcuna dipendenza dall'attrezzatura di rete locale, dai tunnel VPN forzati e dall'interruzione e ispezione di TLS.

Altre volte, l'hardware che è stato ridimensionato e acquistato prima che l'organizzazione iniziava a passare al cloud semplicemente non può essere ridimensionato per gestire i nuovi modelli di traffico e carichi. Se è veramente necessario instradare tutto il traffico attraverso un singolo punto di uscita e/o proxy, prepararsi ad aggiornare le apparecchiature di rete e la larghezza di banda di conseguenza. Monitora attentamente l'utilizzo su entrambi i sistemi, perché l'esperienza non diminuisce lentamente con l'onboardamento di un maggior numero di utenti. Tutto andrà bene fino a quando non viene raggiunto il punto di svolta, quindi tutti ne risentiranno.

## <a name="exceptions-to-the-rules"></a>Eccezioni alle regole

Se l'organizzazione richiede restrizioni [tenant,](/azure/active-directory/manage-apps/tenant-restrictions)è necessario usare un proxy con l'interruzione TLS e ispezionare per forzare un po' di traffico attraverso il proxy, ma non è necessario forzare tutto il traffico attraverso di esso.  Non si tratta di una proposta tutto o niente, quindi presta attenzione a ciò che deve essere modificato dal proxy.

Se vuoi consentire lo split tunneling ma anche usare un proxy per il traffico Web generale, assicurati che il file PAC definirà cosa deve essere diretto e come definire il traffico interessante per ciò che passa attraverso il tunnel VPN. Offriamo file PAC di esempio [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) per semplificarne la gestione.

## <a name="conclusion"></a>Conclusione

Decine di migliaia di organizzazioni, tra cui quasi tutte le fortune 500, usano Office 365 ogni giorno per le loro funzioni mission critical. Lo fanno in modo sicuro e lo fanno tramite Internet.

Indipendentemente dagli obiettivi di sicurezza in gioco, esistono modi per realizzarli che non richiedono connessioni VPN, server proxy, tls break and inspect o uscita centralizzata di Internet per far uscire il traffico degli utenti dalla rete e dalla nostra il più rapidamente possibile, il che garantisce prestazioni ottimali, indipendentemente dal fatto che la rete sia la sede centrale dell'azienda , un ufficio remoto o l'utente che lavora a casa. Le nostre linee guida si basano su come vengono creati i Office 365 e per garantire un'esperienza utente sicura ed performante.

## <a name="further-reading"></a>Ulteriori letture

[Principi Office 365 connettività di rete](../enterprise/microsoft-365-network-connectivity-principles.md)

[URL e intervalli di indirizzi IP per Office 365](../enterprise/urls-and-ip-address-ranges.md)

[Gestione degli endpoint di Office 365](../enterprise/managing-office-365-endpoints.md)

[Servizio Web per URL e indirizzi IP di Office 365](../enterprise/microsoft-365-ip-web-service.md)

[Valutazione della connettività di rete di Office 365](../enterprise/assessing-network-connectivity.md)

[Ottimizzazione delle prestazioni e della rete di Office 365](../enterprise/network-planning-and-performance.md)

[Valutazione della connettività di rete di Office 365](../enterprise/assessing-network-connectivity.md)

[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](../enterprise/performance-tuning-using-baselines-and-history.md)

[Piano di risoluzione dei problemi di prestazioni per Office 365](../enterprise/performance-troubleshooting-plan.md)

[Reti per la distribuzione di contenuti](../enterprise/content-delivery-networks.md)

[Test di connettività di Microsoft 365](https://connectivity.office.com/)

[Come Microsoft sviluppa la sua rete globale veloce e affidabile](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog di rete di Office 365](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365 per gli utenti remoti che usano lo split tunneling VPN](../enterprise/microsoft-365-vpn-split-tunnel.md)