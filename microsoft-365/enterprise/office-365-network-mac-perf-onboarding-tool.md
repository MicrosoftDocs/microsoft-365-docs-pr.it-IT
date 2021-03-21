---
title: Strumento di test della connettività di rete di Microsoft 365 (anteprima)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Strumento di test della connettività di rete di Microsoft 365 (anteprima)
ms.openlocfilehash: 3597996a74cccc3a178f7a5a637c956e0393641b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926119"
---
# <a name="microsoft-365-network-connectivity-test-tool-preview"></a>Strumento di test della connettività di rete di Microsoft 365 (anteprima)

Lo strumento di test della connettività di rete di Microsoft 365 si trova all'indirizzo <https://connectivity.office.com> . Si tratta di uno strumento di aggiunta alle informazioni sulla valutazione della rete e sulle informazioni dettagliate sulla rete disponibili nell'interfaccia di amministrazione di Microsoft 365 in **Health | Menu Connettività.**

> [!IMPORTANT]
> È importante accedere al tenant di Microsoft 365 perché tutti i report di test vengono condivisi con l'amministratore e caricati nel tenant durante l'accesso.

![Strumento di test della connettività](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>Lo strumento di test della connettività di rete supporta i tenant in WW Commercial e Germania, ma non GCC Moderate, GCC High, DoD o Cina.

Le informazioni dettagliate sulla rete nell'interfaccia di amministrazione di Microsoft 365 si basano su misurazioni regolari nel prodotto per il tenant di Microsoft 365 che vengono aggregate ogni giorno. In confronto, le informazioni dettagliate sulla rete del test di connettività di rete di Microsoft 365 vengono eseguite in locale e una volta nello strumento. I test che possono essere eseguiti nel prodotto sono limitati e eseguendo test locali per l'utente è possibile raccogliere più dati, con conseguente approfondimenti più approfonditi. Considerare quindi che le informazioni dettagliate sulla rete nell'interfaccia di amministrazione di Microsoft 365 mostreranno che esiste un problema di rete per l'utilizzo di Microsoft 365 in una posizione specifica dell'ufficio. Il test di connettività di Microsoft 365 può aiutare a identificare la causa principale del problema che conduce a un'azione di miglioramento delle prestazioni di rete consigliata.

È consigliabile usare questi elementi insieme per valutare lo stato di qualità della rete per ogni sede nell'interfaccia di amministrazione di Microsoft 365 e trovare altre specifiche dopo la distribuzione dei test in base al test di connettività di Microsoft 365.

>[!IMPORTANT]
>Informazioni dettagliate sulla rete, consigli sulle prestazioni e valutazioni nell'interfaccia di amministrazione di Microsoft 365 è attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 registrati nel programma di anteprima delle funzionalità.

## <a name="what-happens-at-each-test-step"></a>Cosa accade a ogni passaggio del test

### <a name="office-location-identification"></a>Identificazione della posizione di Office

Quando si fa clic sul pulsante Esegui test, viene visualizzata la pagina di test in esecuzione e viene identificata la posizione dell'ufficio. È possibile digitare la posizione in base alla città, allo stato e al paese oppure rilevarla dal Web browser. Se lo rilevi, richiediamo la latitudine e la longitudine dal web browser e limitiamo l'accuratezza a 300 metri per 300 m prima dell'uso. A tale scopo, non è necessario identificare la posizione in modo più accurato rispetto all'edificio per ottenere prestazioni di rete. 

### <a name="javascript-tests"></a>Test JavaScript

Dopo l'identificazione della posizione dell'ufficio eseiamo un test di latenza TCP in JavaScript e richiediamo dati al servizio sui server porta anteriore del servizio Office 365 in uso e consigliati. Una volta completati, li mostriamo sulla mappa e nella scheda dei dettagli in cui possono essere visualizzati prima del passaggio successivo.

### <a name="download-the-advanced-tests-client-application"></a>Scaricare l'applicazione client di test avanzati

Viene quindi avviato il download dell'applicazione client di test avanzati. Ci affidiamo all'utente per avviare l'applicazione client e deve avere installato anche .NET Core.

Il test della connettività di rete di Microsoft 365 è in due parti. il sito Web e <https://connectivity.office.com> un'applicazione client Windows scaricabile che esegue test avanzati di connettività di rete. La maggior parte dei test richiede l'esecuzione dell'applicazione. I risultati verranno popolati nuovamente nella pagina Web durante l'esecuzione.

Al termine dei test del Web browser verrà richiesto di scaricare l'applicazione di test client avanzata dal sito Web. Aprire ed eseguire il file quando richiesto.

![Applicazione client di test avanzati](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>Avviare l'applicazione client di test avanzati

Una volta avviata l'applicazione client, la pagina Web verrà aggiornerà per mostrare questo valore e i dati di test inizieranno a essere ricevuti nella pagina Web. Si aggiorna ogni volta che vengono ricevuti nuovi dati ed è possibile esaminare i dati non appena arrivano.

### <a name="advanced-tests-completed-and-test-report-upload"></a>Test avanzati completati e caricamento del report di test

Una volta completati i test, la pagina Web verrà indicata dal client dei test avanzati e se l'utente ha effettuato l'accesso al report di test verrà caricato nel tenant dei clienti.

## <a name="sharing-your-test-report"></a>Condivisione del report di test

Il report di test richiede l'accesso all'account di Office 365. L'amministratore seleziona la modalità di condivisione del report di test.

### <a name="sharing-your-report-with-your-administrator"></a>Condivisione del report con l'amministratore

Tutti i report di test dopo l'accesso vengono condivisi con l'amministratore.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Condivisione con il team dell'account Microsoft, il supporto o altro personale

I report di test che escludono qualsiasi identificazione personale vengono condivisi con i dipendenti Microsoft. Questa opzione è abilitata per impostazione predefinita e può essere disabilitata dall'amministratore nel | **Pagina Connettività** di rete nell'interfaccia di amministrazione di Microsoft 365.

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>Condivisione con altri utenti che a questo tipo di accesso a un tenant di Office 365

È possibile scegliere gli utenti con cui condividere il report e questo è abilitato per impostazione predefinita. Può anche essere disabilitato dall'amministratore.

![Condivisione di un collegamento ai risultati dei test con un utente](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>Condivisione con chiunque utilizzi un collegamento ReportID

È possibile condividere il report di test con chiunque fornendo l'accesso a un collegamento ReportID. In questo modo viene generato un URL che è possibile inviare a un utente in modo che possa visualizzare il report di test senza eseguire l'accesso. Questa opzione è disabilitata per impostazione predefinita e deve essere abilitata dall'amministratore.

![Condivisione di un collegamento ai risultati dei test](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>Risultati test connettività di rete

I risultati vengono visualizzati nelle **schede Riepilogo** **e** Dettagli. La scheda di riepilogo mostra una mappa del perimetro di rete rilevato e un confronto della valutazione della rete con altri clienti di Office 365 nelle vicinanze. Consente inoltre la condivisione del report di test. Ecco l'aspetto della visualizzazione dei risultati di riepilogo.

![Risultati di riepilogo dello strumento di test della connettività di rete](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

Ecco un esempio dell'output della scheda dettagli visualizzato con lo strumento. Nella scheda dei dettagli viene visualizzato un segno di spunta cerchio verde se il risultato è stato confrontato favorevolmente con una soglia. Se il risultato ha superato una soglia che indica una conoscenza della rete, viene visualizzato un punto esclamativo con triangolo rosso. Nelle sezioni seguenti vengono descritte tutte le righe dei risultati della scheda Dettagli e vengono illustrate le soglie utilizzate per le informazioni dettagliate sulla rete.

![Risultati del test dello strumento di test della connettività di rete](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>Informazioni sulla posizione

In questa sezione vengono mostrati i risultati dei test correlati alla posizione.

#### <a name="your-location"></a>La tua posizione

La posizione dell'utente viene rilevata dal Web browser degli utenti oppure può essere digitata a scelta degli utenti. Viene utilizzato per identificare le distanze di rete verso parti specifiche del perimetro della rete aziendale. Nel report vengono salvate solo la città di questo rilevamento della posizione e la distanza da altri punti di rete.

La posizione dell'ufficio utente viene visualizzata nella visualizzazione mappa.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>Posizione di uscita dalla rete (la posizione in cui la rete si connette all'ISP)

L'indirizzo IP di uscita dalla rete viene identificato sul lato server. I database delle località vengono utilizzati per cercare la posizione approssimativa per l'uscita di rete. Questi database hanno in genere una precisione di circa il 90% degli indirizzi IP. Se la posizione cercata dall'indirizzo IP di uscita della rete non è accurata, questo potrebbe causare un risultato falso da questo test. Per verificare se questo errore si verifica per uno specifico indirizzo IP, è possibile utilizzare siti Web di posizione dell'indirizzo IP di rete accessibili pubblicamente da confrontare con la posizione effettiva.

#### <a name="your-distance-from-the-network-egress-location"></a>La distanza dalla posizione di uscita dalla rete

Microsoft determina la distanza da tale posizione alla sede dell'ufficio. Questo viene mostrato come un'analisi della rete se la distanza è superiore a **500 miglia** (800 chilometri) dal momento che è probabile che aumenti la latenza TCP di più di 25 ms e possa influire sull'esperienza utente.

La posizione di uscita della rete viene visualizzata nella visualizzazione mappa e connessa alla posizione dell'ufficio dell'utente che indica il backhaul di rete all'interno della rete WAN aziendale.

Per la connettività di rete di Microsoft 365 è consigliabile implementare l'uscita di rete locale e diretta dalle posizioni degli uffici degli utenti a Internet. I miglioramenti all'uscita locale e diretta sono il modo migliore per affrontare queste informazioni di rete.

#### <a name="proxy-server-information"></a>Informazioni sul server proxy

Identifidiamo i server proxy configurati nel computer locale. Viene identificato se una di queste impostazioni è configurata nel percorso di rete per ottimizzare il traffico di rete di Microsoft 365. Viene identificata la distanza tra la sede dell'utente e i server proxy. La distanza viene testata prima dal ping ICMP e in caso di esito negativo viene eseguito il test con il ping TCP e infine, in caso di esito negativo, viene eseguita la ricerca dell'indirizzo IP del server proxy in un database della posizione dell'indirizzo IP. Viene mostrata una panoramica della rete  se il server proxy si trova a più di 800 chilometri dalla sede dell'utente.

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>Rete privata virtuale (VPN) utilizzata per connettersi all'organizzazione

Questo rileva se si usa una VPN per connettersi a Office 365. Un risultato di passaggio mostrerà se non si dispone di una VPN o se si dispone di una VPN con la configurazione split tunnel consigliata per Office 365.

#### <a name="vpn-split-tunnel"></a>VPN Split Tunnel

Ogni route di ottimizzazione delle categorie per Exchange Online, SharePoint Online e Microsoft Teams viene testata per verificare se è stata o meno tunneled nella VPN. Un carico di lavoro diviso evita completamente la VPN. Un carico di lavoro tunneling viene inviato tramite VPN. Un carico di lavoro con tunneling selettivo ha alcune route inviate sulla VPN e alcune sono suddivise. Un risultato di passaggio mostrerà se tutti i carichi di lavoro sono suddivisi o selettivi.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>Clienti nell'area metropolitana con prestazioni migliori

La latenza TCP di rete della sede dell'utente alla porta principale del servizio Exchange Online viene confrontata con altri clienti di Microsoft 365 nella stessa area della metropolitana. Viene visualizzata una panoramica della rete se il 10% o più clienti nella stessa area della metropolitana hanno prestazioni migliori. Ciò significa che gli utenti avranno prestazioni migliori nell'interfaccia utente di Microsoft 365.

Queste informazioni sulla rete vengono generate in base al fatto che tutti gli utenti di una città hanno accesso alla stessa infrastruttura di telecomunicazione e alla stessa prossimità ai circuiti Internet e alla rete di Microsoft.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>È ora di effettuare una richiesta DNS nella rete

In questo modo viene visualizzato il server DNS configurato nel computer client che ha eseguito i test. Potrebbe trattarsi di un server Resolver ricorsivo DNS, ma ciò non è raro. È più probabile che si tratta di un server d'inoltro DNS che memorizza nella cache i risultati DNS e inoltra eventuali richieste DNS non memorizzate nella cache a un altro server DNS.

Questo viene fornito solo per le informazioni e non contribuisce ad alcuna conoscenza della rete.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>Distanza da e/o tempo per la connessione a un resolver ricorsivo DNS

Il Resolver ricorsivo DNS in uso viene identificato effettuando una richiesta DNS specifica e quindi richiedendo al server dei nomi DNS l'indirizzo IP da cui ha ricevuto la stessa richiesta. Questo indirizzo IP è il Resolver ricorsivo DNS e verrà cercato nei database delle località degli indirizzi IP per trovare il percorso. Viene quindi calcolata la distanza dalla posizione dell'ufficio dell'utente alla posizione del server Resolver ricorsivo DNS. Questo viene visualizzato come un'analisi della rete se la distanza è maggiore di **500 miglia** (800 chilometri).

Il percorso cercato dall'indirizzo IP di uscita della rete potrebbe non essere accurato e ciò potrebbe causare un risultato falso da questo test. Per verificare se questo errore si verifica per un indirizzo IP specifico, è possibile utilizzare siti Web percorso indirizzo IP di rete accessibile pubblicamente.

Queste informazioni dettagliate sulla rete incideranno in modo specifico sulla selezione della porta principale del servizio Exchange Online. Per risolvere questo problema, l'uscita di rete locale e diretta deve essere un requisito preliminare e quindi il resolver ricorsivo DNS deve trovarsi vicino a tale uscita di rete.

### <a name="exchange-online"></a>Exchange Online

In questa sezione vengono mostrati i risultati dei test relativi a Exchange Online.

#### <a name="exchange-service-front-door-location"></a>Posizione della porta principale del servizio Exchange

La porta anteriore del servizio Exchange in uso è identificata nello stesso modo in cui Outlook esegue questa operazione e viene misurata la latenza TCP di rete dalla posizione dell'utente ad esso. Viene visualizzata la latenza TCP e la porta anteriore del servizio Exchange in uso viene confrontata con l'elenco delle migliori porte anteriori del servizio per la posizione corrente. Questo viene visualizzato come un'analisi della rete se non è in uso una delle migliori porte anteriori del servizio Exchange.

Il non utilizzo di una delle migliori porte anteriori del servizio Exchange potrebbe essere causato dal backhaul di rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita della rete locale e diretta. Potrebbe anche essere causato dall'utilizzo di un server resolver ricorsivo DNS remoto nel qual caso è consigliabile allineare il server resolver ricorsivo DNS con l'uscita di rete.

Viene calcolato un potenziale miglioramento della latenza TCP (ms) alla porta principale del servizio Exchange. A tale scopo, si esamina la latenza di rete della posizione dell'ufficio dell'utente testata e si sottrae la latenza di rete dalla posizione corrente alla porta principale del servizio Exchange. La differenza rappresenta la potenziale opportunità di miglioramento.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>Porta principale del servizio Exchange migliore per la propria posizione

In questo elenco sono elencate le migliori posizioni delle porte anteriori del servizio Exchange per città per la propria posizione.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Porta anteriore del servizio registrata nel DNS client

In questo modo vengono visualizzati il nome DNS e l'indirizzo IP del server della porta principale del servizio Exchange a cui si è stati indirizzati. Viene fornito solo per le informazioni e non sono disponibili informazioni dettagliate sulla rete associate.

### <a name="sharepoint-online"></a>SharePoint Online

Questa sezione mostra i risultati dei test correlati a SharePoint Online e OneDrive.

#### <a name="the-service-front-door-location"></a>Posizione della porta principale del servizio

La porta principale del servizio SharePoint in uso è identificata nello stesso modo in cui viene utilizzato dal client OneDrive e viene misurata la latenza TCP di rete dalla posizione dell'ufficio dell'utente.

#### <a name="download-speed"></a>Velocità di download

Viene misurata la velocità di download per un file da 15 Mb dalla porta principale del servizio SharePoint. Il risultato viene visualizzato in megabyte al secondo per indicare le dimensioni del file in megabyte che possono essere scaricate da SharePoint o OneDrive in **un secondo.** Il numero deve essere simile a un decimo della larghezza di banda minima del circuito in megabit al secondo. Ad esempio, se si dispone di una connessione Internet a 100 mbps, è possibile aspettarsi 10 megabyte al secondo (10 MBps).

#### <a name="buffer-bloat"></a>Buffer bloat

Durante il download da 15 Mb viene misurata la latenza TCP per la porta d'ingresso del servizio SharePoint. Questa è la latenza sotto carico e viene confrontata con la latenza quando non è sotto carico. L'aumento della latenza in caso di carico è spesso attribuibile ai buffer dei dispositivi di rete consumer caricati (o gonfiati). Viene visualizzata una panoramica della rete per qualsiasi gonfio di 1.000 o più.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Porta anteriore del servizio registrata nel DNS client

In questo modo vengono visualizzati il nome DNS e l'indirizzo IP del server della porta principale del servizio SharePoint a cui si è stati indirizzati. Viene fornito solo per le informazioni e non sono disponibili informazioni dettagliate sulla rete associate.

### <a name="microsoft-teams"></a>Microsoft Teams

In questa sezione vengono mostrati i risultati dei test correlati a Microsoft Teams.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>Connettività multimediale (condivisione audio, video e applicazioni)

In questo modo viene verificata la connettività UDP alla porta principale del servizio Microsoft Teams. Se questo è bloccato, Microsoft Teams potrebbe comunque funzionare con TCP, ma audio e video saranno compromessi. Per altre informazioni su queste misurazioni di rete UDP che si applicano anche a Microsoft Teams, vedere [Media Quality and Network Connectivity Performance in Skype for Business online](/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

#### <a name="packet-loss"></a>Perdita di pacchetti

Mostra la perdita di pacchetti UDP misurata in una chiamata audio di prova di 10 secondi dal client alla porta principale del servizio Microsoft Teams. Questo valore deve essere inferiore **all'1,00%** per un passaggio.

#### <a name="latency"></a>Latenza

Mostra la latenza UDP misurata, che deve essere inferiore a **100 ms.**

#### <a name="jitter"></a>Instabilità

Mostra l'instabilità UDP misurata, che deve essere inferiore a **30 ms.**

#### <a name="connectivity"></a>Connettività

Testiamo la connettività HTTP dalla posizione dell'ufficio dell'utente a tutti gli endpoint di rete di Microsoft 365 necessari. Questi sono pubblicati all'indirizzo [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) . Viene visualizzata una panoramica della rete per tutti gli endpoint di rete necessari a cui non è possibile connettersi.

La connettività può essere bloccata da un server proxy, un firewall o un altro dispositivo di sicurezza di rete nel perimetro della rete aziendale. La connettività alla porta TCP 80 viene testata con una richiesta HTTP e la connettività alla porta TCP 443 viene testata con una richiesta HTTPS. Se non è presente alcuna risposta, il nome di dominio completo viene contrassegnato come errore. Se è presente un codice di risposta HTTP 407, il nome di dominio completo viene contrassegnato come errore. Se è presente un codice di risposta HTTP 403, viene verificato l'attributo Server della risposta e se sembra essere un server proxy viene contrassegnato come errore. Puoi simulare i test eseguiti con lo strumento da riga di comando di Windows curl.exe.

Il certificato SSL viene testato in ogni endpoint di rete Di Microsoft 365 necessario nella categoria ottimizza o consenti, come definito in [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) . Se i test non trovano un certificato SSL Microsoft, la rete crittografata connessa deve essere stata intercettata da un dispositivo di rete intermedio. Viene visualizzata una panoramica della rete su qualsiasi endpoint di rete crittografato intercettato.

Se viene trovato un certificato SSL non fornito da Microsoft, viene visualizzato il nome di dominio completo per il test e il proprietario del certificato SSL in uso. Il proprietario del certificato SSL può essere un fornitore di server proxy o un certificato autofirmato aziendale.

#### <a name="network-path"></a>Percorso di rete

In questa sezione vengono mostrati i risultati di un percorso di traccia ICMP verso la porta d'ingresso del servizio Exchange Online, la porta d'ingresso del servizio SharePoint Online e la porta principale del servizio Microsoft Teams. Viene fornito solo per le informazioni e non sono disponibili informazioni dettagliate sulla rete associate. Sono disponibili tre traceroute. Un traceroute per _outlook.office365.com_, un traceroute al front-end di SharePoint dei clienti o _a microsoft.sharepoint.com_ se non ne è stato fornito uno e un traceroute a _world.tr.teams.microsoft.com_.

## <a name="connectivity-reports"></a>Rapporti di connettività

Dopo aver effettuato l'accesso, è possibile esaminare i report precedenti eseguiti. Puoi anche condividerli o eliminarli dall'elenco.

![Report](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>Stato di integrità della rete

Questo mostra eventuali problemi di integrità significativi con la rete globale di Microsoft che potrebbero influire sui clienti di Microsoft 365.

![Stato di integrità della rete](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>Domande frequenti

Ecco le risposte ad alcune delle domande frequenti.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>Questo strumento è stato rilasciato e supportato da Microsoft?

Attualmente è un'anteprima e microsoft prevede di fornire aggiornamenti regolarmente fino a quando non raggiungiamo lo stato di rilascio della disponibilità generale con il supporto di Microsoft. Fornisci feedback per aiutarci a migliorare. Microsoft prevede di pubblicare una guida più dettagliata sull'onboarding di rete di Office 365 nell'ambito di questo strumento, personalizzato per l'organizzazione in base ai risultati dei test.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>Cosa è necessario per eseguire il client di test avanzato?

Il client di test avanzato richiede .NET Core 3.1 Desktop Runtime. Se si esegue il client di test avanzato senza che sia installato, si verrà reindirizzati alla pagina del programma di installazione [di .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1) Assicurati di installare Desktop Runtime e non l'SDK o ASP.NET Core Runtime più in alto nella pagina. Per installare .NET Core sono necessarie autorizzazioni di amministratore nel computer.

### <a name="what-is-microsoft-365-service-front-door"></a>Che cos'è la porta d'ingresso del servizio Microsoft 365?

La porta principale del servizio Microsoft 365 è un punto di ingresso nella rete globale di Microsoft in cui i client e i servizi di Office terminano la connessione di rete. Per una connessione di rete ottimale a Microsoft 365, è consigliabile che la connessione di rete venga terminata nella porta principale di Microsoft 365 più vicina nella città o nella metropolitana.

Nota: la porta anteriore del servizio Microsoft 365 non ha alcuna relazione diretta con il **prodotto Azure Front Door Service** disponibile nel marketplace di Azure.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>Qual è la migliore porta d'ingresso del servizio Microsoft 365?

Una migliore porta d'ingresso del servizio Microsoft 365 (in precedenza nota come porta d'ingresso di servizio ottimale) è quella più vicina all'uscita della rete, in genere nella città o nell'area della metropolitana. Usare lo strumento prestazioni di rete di Microsoft 365 per determinare la posizione della porta d'ingresso del servizio Microsoft 365 in uso e la porta principale del servizio migliore. Se lo strumento determina che la porta d'ingresso in uso è una delle migliori, è consigliabile aspettarsi una connettività ottimale nella rete globale di Microsoft.

### <a name="what-is-an-internet-egress-location"></a>Che cos'è una posizione di uscita da Internet?

La posizione in uscita da Internet è la posizione in cui il traffico di rete esce dalla rete aziendale e si connette a Internet. Questo è anche identificato come la posizione in cui si dispone di un dispositivo NAT (Network Address Translation) e in genere in cui ci si connette con un provider di servizi Internet (ISP). Se viene visualizzata una lunga distanza tra la posizione e la posizione di uscita da Internet, è possibile che venga identificato un backhaul WAN significativo.

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md)

[Informazioni dettagliate sulle prestazioni di rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-insights.md)

[Valutazione della rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-score.md)

[Servizi percorso connettività di rete Microsoft 365 (anteprima)](office-365-network-mac-location-services.md)