---
title: Creazione di una rete (nel cloud)-punto di vista di un architetto
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
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Creazione di una rete (nel cloud)-punto di vista di un architetto

In questo articolo, [ed Fisher](https://www.linkedin.com/in/edfisher/), Security & Compliance Architect presso Microsoft, viene descritto come ottimizzare la rete per la connettività cloud evitando gli ostacoli più comuni. 

## <a name="about-the-author"></a>Informazioni sull'autore

![Foto di ed Fisher](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Sono attualmente uno specialista tecnico principale nella regione sudorientale incentrato sulla conformità alla sicurezza &. Ho collaborato con i clienti che si trasferiscono in Office 365 negli ultimi 10 anni. Ho collaborato con negozi di piccole dimensioni con una manciata di posizioni a enti governativi e imprese con milioni di utenti distribuiti in tutto il mondo e in molti altri clienti, con la maggioranza con decine di migliaia di utenti, più sedi in varie parti del mondo, la necessità di un livello di sicurezza superiore e una moltitudine di requisiti di conformità. Sono stati aiutati centinaia di aziende e milioni di utenti a passare al cloud in modo sicuro e sicuro.

Con uno sfondo negli ultimi 25 anni che include la sicurezza, l'infrastruttura e la tecnologia di rete, e dopo aver spostato due dei miei precedenti datori di lavoro in Office 365 prima di partecipare a Microsoft, ho avuto un sacco di volte dalla tua parte del tavolo e mi ricordo come è. Anche se non sono presenti due clienti uguali, la maggior parte ha esigenze simili e quando si utilizza un servizio standardizzato, ad esempio qualsiasi piattaforma SaaS o PaaS, gli approcci migliori tendono a essere uguali.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>Non è la rete, è il modo in cui si sta usando (MIS)!

Indipendentemente dal numero di volte in cui si verifica, non riesce mai a stupirmi in che modo i team di sicurezza *creativi* e i team di networking tentano di utilizzare il modo in cui pensano di dover connettersi ai servizi cloud Microsoft. Esistono sempre alcuni criteri di sicurezza, standard di conformità o un modo migliore per insistono sull'utilizzo, senza essere disposti a impegnarsi in una conversazione su ciò che stanno cercando di realizzare o su *come* siano migliori, più facili, più convenienti e più performanti.

Quando questo genere di cose è stato escalated a me, di solito sono disposto a prendere la sfida e a camminare attraverso il come e il perché e farli dove devono essere. Ma se devo essere completamente Franco, devo condividere che a volte voglio solo lasciarli fare quello che vogliono, e tornare a dire che ho detto che quando finalmente ammettono che non funziona. A volte potrebbe essere necessario farlo, ma *non* è possibile. È possibile provare a spiegare tutto quello che verrà incluso in questo post. Indipendentemente dal ruolo, se l'organizzazione desidera utilizzare i servizi cloud Microsoft, è probabile che vi sia una certa saggezza in quanto segue che può essere di aiuto.

## <a name="guiding-principles"></a>Principi guida

Iniziamo con alcune regole di base attorno a ciò che stiamo facendo qui. Stiamo discutendo su come connettersi in modo sicuro ai servizi cloud per garantire la massima complessità e le prestazioni massime, mantenendo la sicurezza reale. Nessuna delle operazioni seguenti è in grado di rispondere a qualsiasi cosa, anche se il cliente non può utilizzare il server proxy preferito per tutto.

- **Solo perché è possibile, non significa che dovrebbe**: o parafrasare il Dr. Ian Malcolm del film Jurassic Park "... Sì, sì, ma il team di sicurezza è stato così preoccupato del fatto che non si siano fermati a pensare se fossero in grado di farlo.
- **La sicurezza non significa complessità**: non si è più sicuri solo perché si spendono più soldi, si passa attraverso più dispositivi o si fa clic su altri pulsanti.
- **È possibile accedere a office 365 tramite Internet**: ma non è la stessa cosa di Office 365 è Internet. Si tratta di un servizio SaaS gestito da Microsoft e amministrato dall'utente. A differenza dei siti Web visitati su Internet, in realtà si arriva a sbirciare dietro le quinte e si possono applicare i controlli necessari per soddisfare i criteri e gli standard di conformità, purché si renda conto che, sebbene sia possibile soddisfare gli obiettivi, potrebbe essere necessario eseguirli in modo diverso.
- **Chokepoints sono cattivi, sblocchi localizzati sono buoni**: tutti vogliono sempre backhaul tutto il loro traffico Internet per tutti gli utenti a un certo punto centrale, di solito in modo che possano monitorarlo e applicare i criteri, ma spesso perché è più conveniente che provisioning di accesso a Internet in tutte le loro posizioni, o è solo come lo fanno. Ma quelli chokepoints sono esattamente quello... punti in cui il traffico si strozza. Non c'è niente di sbagliato nell'impedire agli utenti di accedere a Instagram o di trasmettere video cat, ma non trattano il traffico delle applicazioni aziendali critiche nello stesso modo.
- **Se il DNS non è felice, non** c'è niente di felice: la migliore rete progettata può essere ostacolato dal DNS scadente, se si ricorre a richieste ai server in altre aree del mondo o ai server DNS dell'ISP o ad altri server DNS pubblici che memorizzano nella cache le informazioni sulla risoluzione DNS.
- **Solo perché questo è il modo in cui è stato utilizzato per farlo, non significa che è il modo in cui si dovrebbe fare ora**: la tecnologia cambia costantemente e Office 365 non è un'eccezione. L'applicazione di misure di sicurezza sviluppate e distribuite per i servizi locali o per controllare la navigazione sul Web non è in grado di fornire lo stesso livello di sicurezza e può avere un impatto negativo significativo sulle prestazioni.
- **Office 365 è stato creato per l'accesso tramite Internet**: questo è tutto in poche parole. Indipendentemente da ciò che si vuole fare tra gli utenti e il perimetro, il traffico continua a essere eseguito su Internet una volta che la rete viene lasciata e prima che venga trascinata sul nostro. Anche se si utilizza Azure ExpressRoute per instradare il traffico sensibile alla latenza dalla rete direttamente alla nostra, è assolutamente necessaria la connettività Internet. Accettarlo. Non pensarci troppo.

## <a name="where-bad-choices-are-often-made"></a>In cui vengono spesso eseguite scelte errate

Sebbene esistano numerosi luoghi in cui vengono prese decisioni errate in nome della sicurezza, queste sono le più frequenti con i clienti. Molte conversazioni dei clienti coinvolgono tutte queste contemporaneamente.

### <a name="insufficient-resources-at-the-edge"></a>Risorse insufficienti nel server perimetrale

Pochissimi clienti stanno distribuendo ambienti Greenfield e hanno anni di esperienza con la modalità di funzionamento degli utenti e la loro uscita Internet. Se i clienti dispongono di server proxy o consentono l'accesso diretto e semplicemente il traffico in uscita NAT, lo fanno da anni e non considerano quanto più si sta per iniziare a pompare il proprio perimetro quando si spostano le applicazioni tradizionalmente interne verso il cloud.

La larghezza di banda è sempre un problema, ma i dispositivi NAT potrebbero non avere abbastanza potenza per gestire il carico aumentato e possono avviare la chiusura prematura delle connessioni per liberare le risorse. La maggior parte del software client che si connette a Office 365 prevede connessioni permanenti e un utente che utilizza completamente Office 365 può avere 32 o più connessioni simultanee. Se il dispositivo NAT è in calo prematuramente, tali app potrebbero non rispondere mentre tentano di utilizzare le connessioni che non sono più presenti. Quando si arrendono e tentano di stabilire nuove connessioni, il carico di rete è ancora maggiore.

### <a name="localized-breakout"></a>Breakout localizzato

Tutto il resto di questo elenco si riduce a una sola cosa: la tua rete e il nostro il più velocemente possibile. Backhauling il traffico degli utenti a un punto di uscita centrale, soprattutto quando il punto di uscita è in un'altra area rispetto a quelli degli utenti, introduce latenza non necessaria e incide sia sull'esperienza client che sulla velocità di download. Microsoft ha punti di presenza in tutto il mondo con front-end per tutti i servizi e peering stabiliti con praticamente ogni ISP principale, in modo da instradare il traffico degli utenti fuori *localmente* garantisce che entra rapidamente nella nostra rete con latenza minima.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>Il traffico di risoluzione DNS deve seguire il percorso di uscita Internet

Naturalmente, affinché un client trovi qualsiasi endpoint, deve utilizzare DNS. I server DNS di Microsoft valutano l'origine delle richieste DNS per assicurarsi che venga restituita la risposta che è, in termini Internet, più vicina all'origine della richiesta. Verificare che il DNS sia configurato in modo che le richieste di risoluzione dei nomi rientrino nello stesso percorso del traffico degli utenti, per timore che l'uscita locale sia configurata in un endpoint di un'altra area. Questo significa che i server DNS locali "passano alla radice" anziché inoltrare ai server DNS nei data center remoti. E guardare fuori per i servizi DNS pubblici e privati, che possono memorizzare i risultati da una parte del mondo e servirli alle richieste provenienti da altre parti del mondo.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Per inoltrare o meno il proxy, questa è la domanda

Una delle prime considerazioni da prendere in considerazione è la possibilità di inoltrare le connessioni degli utenti a Office 365. Questo è facile; non eseguire il proxy. È possibile accedere a Office 365 tramite Internet, ma non è Internet. Si tratta di un'estensione dei servizi di base e deve essere trattata come tale. Qualsiasi operazione che potrebbe essere necessaria per un proxy, ad esempio DLP o antimalware o controllo del contenuto, è già disponibile per l'utente nel servizio e può essere utilizzata in scala e senza dover craccare le connessioni crittografate TLS. Tuttavia, se si vuole davvero il traffico proxy che non è possibile controllare, prestare attenzione alle linee guida [https://aka.ms/pnc](https://aka.ms/pnc) e alle categorie di traffico [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) . Sono disponibili tre categorie di traffico per Office 365. Ottimizzare e consentire in realtà dovrebbe andare direttamente e bypassare il proxy. Il valore predefinito può essere inoltrato. I dettagli sono in quei documenti... leggerli.

La maggior parte dei clienti che insistono sull'utilizzo di un proxy, quando effettivamente esaminano cosa stanno facendo, vengono a rendersi conto che quando il client effettua una richiesta di connessione HTTP al proxy, il proxy è ora solo un costoso router aggiuntivo. I protocolli in uso, ad esempio MAPI e RTC, non sono neppure protocolli che i proxy Web capiscono, quindi anche con il cracking di TLS non si ha realmente alcuna sicurezza supplementare. Si *sta* ottenendo latenza supplementare. [https://aka.ms/pnc](https://aka.ms/pnc)Per ulteriori informazioni, vedere le categorie ottimizzazione, Consenti e predefinita per il traffico Microsoft 365.

Infine, prendere in considerazione l'impatto generale del proxy e la risposta corrispondente per gestire tale impatto. Quando si effettuano sempre più connessioni tramite il proxy, è possibile che il fattore di scala TCP diminuisca in modo che il traffico non sia necessario per il buffer. Sono stati visualizzati clienti in cui i proxy sono stati sovraccaricati in modo da utilizzare un fattore di scala pari a 0. Poiché il fattore di scala è un valore esponenziale e ci piace usare 8, ogni riduzione del valore del fattore di scala è un impatto negativo enorme sulla velocità effettiva.

Controllo TLS significa sicurezza. Ma non proprio! Molti clienti con proxy desiderano usarli per ispezionare tutto il traffico e questo significa che TLS "break and ispeziona". Quando si esegue questa operazione per un sito Web a cui si accede tramite HTTPS (nonostante i problemi relativi alla privacy), potrebbe essere necessario che il proxy abbia a che fare con 10 o 20 flussi contemporanei per qualche centinaio di millisecondi. Se è presente un download di grandi dimensioni o un video coinvolto, una o più di queste connessioni potrebbero durare molto più a lungo, ma nel complesso la maggior parte di tali connessioni stabilisce, trasferisce e si chiude molto rapidamente. Fare break and Inspect significa che il proxy deve raddoppiare il lavoro. Per ogni connessione tra il client e il proxy, il proxy deve anche eseguire una connessione separata all'endpoint. Quindi, 1 diventa 2, 2 diventa 4, 32 diventa 64... vedere dove sto per passare? È probabile che le dimensioni della soluzione proxy siano ottimali per la tipica navigazione sul Web, ma quando si tenta di eseguire la stessa operazione per le connessioni client a Office 365, il numero di connessioni simultanee e longeve potrebbe essere superiore a quello di cui si è dimensioni.

### <a name="streaming-isnt-important-except-that-it-is"></a>Lo streaming non è importante, tranne per il fatto che *è*

Gli unici servizi di Office 365 che utilizzano UDP sono Skype (presto per essere ritirati) e Microsoft teams. Teams utilizza UDP per il flusso del traffico, inclusa la condivisione di audio, video e presentazioni. Il traffico in streaming è attivo, ad esempio quando si effettua una riunione online con i deck vocali, video e di presentazione o con le demo. Questi utilizzano UDP perché se i pacchetti vengono eliminati o arrivano fuori ordine, è praticamente impercettibile dall'utente e lo stream può continuare.

Quando non si consente il traffico UDP in uscita dai client al servizio, è possibile eseguire il fallback all'utilizzo di TCP. Tuttavia, se un pacchetto TCP viene eliminato, *tutto si interrompe* fino alla scadenza del timeout di ritrasmissione (RTO) e il pacchetto mancante può essere ritrasmesso. Se un pacchetto arriva fuori ordine, tutto si interrompe fino a quando arrivano gli altri pacchetti e possono essere riassemblati nell'ordine. Entrambi portano a difetti percettibili nell'audio (si ricordi la massima altezza?) e video (si è fatto clic su qualcosa... Oh, eccolo) e portare a scarse prestazioni e una cattiva esperienza utente. E ricorda cosa ho messo sopra sui proxy? Quando si impone a un client di team di utilizzare un proxy, è possibile imporre l'utilizzo di TCP. Così ora si sta causando un impatto negativo sulle prestazioni due volte.

### <a name="split-tunneling-may-seem-scary"></a>Il tunneling suddiviso può sembrare spaventoso

Ma non lo è. Tutte le connessioni a Office 365 sono su TLS. Sono stati offerti TLS 1,2 per un bel po' di tempo e le versioni precedenti verranno disabilitate presto perché i client legacy continuano a usarli e questo è un rischio.

Forzare una connessione TLS, o 32 di essi, per passare da una VPN prima che poi vadano al servizio non aggiunge la sicurezza. Consente di aggiungere latenza e di ridurre la velocità effettiva complessiva. In alcune soluzioni VPN, costringe anche UDP al tunnel tramite TCP, che avrà un impatto molto negativo sul traffico di flusso. E, a meno che non si stia eseguendo il controllo TLS, non c'è alcun lato negativo. Un tema molto comune tra i clienti, ora che la maggior parte dei dipendenti è remoto, è la visualizzazione di una significativa larghezza di banda e un impatto sulle prestazioni per la connessione di tutti gli utenti tramite una VPN, invece di configurare il tunneling suddiviso per l'accesso per [ottimizzare gli endpoint di categoria Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).

Si tratta di una soluzione semplice per eseguire il tunneling suddiviso ed è necessario eseguire questa operazione. Per ulteriori informazioni, vedere [ottimizzare la connettività di Office 365 per gli utenti remoti tramite il tunneling Split VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel).

## <a name="the-sins-of-the-past"></a>Peccati del passato

Molte volte, le scelte errate causate provengono da una combinazione di (1) non sapendo come funziona il servizio, (2) cercando di aderire ai criteri aziendali che sono stati scritti prima di adottare il cloud e (3) squadre di sicurezza che potrebbero non essere facilmente convincenti che esistono più modi per raggiungere i propri obiettivi. Si spera che quanto sopra, e i collegamenti riportati di seguito, siano utili per il primo. La sponsorizzazione esecutiva può essere necessaria per superare la seconda. L'indirizzamento degli obiettivi dei criteri di sicurezza, anziché dei loro metodi, è utile per il terzo. Dall'accesso condizionale alla moderazione del contenuto, alla protezione delle informazioni e alla convalida dell'endpoint alle minacce zero-day, qualsiasi obiettivo finale può essere possibile ottenere un criterio di sicurezza ragionevole con ciò che è disponibile in Office 365 e senza alcuna dipendenza dall'ingranaggio di rete locale, dai tunnel VPN forzati e dall'interruzione di TLS e dall'ispezione.

In altri casi, l'hardware che è stato ridimensionato e acquistato prima che l'organizzazione abbia iniziato a spostarsi nel cloud non può essere ridimensionato per gestire i nuovi modelli e carichi del traffico. Se è effettivamente necessario instradare tutto il traffico tramite un unico punto di uscita e/o inoltrarlo tramite proxy, prepararsi all'aggiornamento delle apparecchiature di rete e della larghezza di banda di conseguenza. Monitorare attentamente l'utilizzo su entrambi, in quanto l'esperienza non diminuirà lentamente man mano che si verificano più utenti. Tutto andrà bene fino a quando non si raggiunge il punto di svolta, quindi tutti soffrono.

## <a name="exceptions-to-the-rules"></a>Eccezioni alle regole

Se l'organizzazione richiede [restrizioni tenant](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions), è necessario utilizzare un proxy con interruzione TLS e ispezionare per forzare il traffico attraverso il proxy, ma non è necessario forzare tutto il traffico.  Non si tratta di una proposta tutto o niente, quindi prestare attenzione a ciò che deve essere modificato dal proxy.

Se si desidera consentire la suddivisione del tunneling ma anche l'utilizzo di un proxy per il traffico Web generale, assicurarsi che il file PAC definisca ciò che deve andare direttamente e come definire il traffico interessante per ciò che passa attraverso il tunnel VPN. I file PAC di esempio sono disponibili in [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) questo modo è più facile da gestire.

## <a name="conclusion"></a>Conclusione

Decine di migliaia di organizzazioni, tra cui quasi tutte le Fortune 500, utilizzano Office 365 tutti i giorni per le loro funzioni mission-critical. Lo fanno in modo sicuro e lo fanno su Internet.

Indipendentemente dagli obiettivi di sicurezza in gioco, esistono diversi modi per eseguire le operazioni che non richiedono connessioni VPN, server proxy, interruzione di TLS e ispezione o l'uscita centralizzata di Internet per ottenere il traffico degli utenti dalla rete e il più velocemente possibile, il che fornisce le prestazioni migliori, se la rete è la sede centrale della società, una sede remota o che l'utente funzioni a casa. Le linee guida si basano sul modo in cui vengono creati i servizi di Office 365 e per garantire un'esperienza utente sicura ed eseguibile.

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

[Connettività di Office 365 per gli utenti remoti tramite il tunneling Split VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)


