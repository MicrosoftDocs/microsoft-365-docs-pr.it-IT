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
ms.openlocfilehash: b29eb29cd390c3febd0992e942cf8ab39f652fb2
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "49569988"
---
# <a name="microsoft-365-network-connectivity-test-tool-preview"></a>Strumento di test della connettività di rete di Microsoft 365 (anteprima)

Lo strumento di test della connettività di rete di Microsoft 365 si trova in <https://connectivity.office.com> . Si tratta di uno strumento di aggiunta alle informazioni dettagliate sulla rete e sulla valutazione della rete disponibili nell'interfaccia di amministrazione di Microsoft 365 nella sezione **Health | Menu Connettività.**

> [!IMPORTANT]
> È importante accedere al tenant di Microsoft 365 perché tutti i report di test vengono condivisi con l'amministratore e caricati nel tenant durante l'accesso.

![Strumento di test della connettività](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>Lo strumento di test della connettività di rete supporta i tenant in WW Commercial e Germania, ma non GCC Moderate, GCC High, DoD o Cina.

Le informazioni dettagliate sulla rete nell'interfaccia di amministrazione di Microsoft 365 si basano sulle normali misurazioni nel prodotto per il tenant di Microsoft 365 che vengono aggregate ogni giorno. In confronto, le informazioni dettagliate sulla rete del test di connettività di rete di Microsoft 365 vengono eseguite in locale e una volta nello strumento. I test che possono essere eseguiti nel prodotto sono limitati e eseguendo test locali per l'utente è possibile raccogliere più dati e ottenere approfondimenti più approfonditi. Considerare quindi che le informazioni dettagliate sulla rete nell'interfaccia di amministrazione di Microsoft 365 mostreranno che esiste un problema di rete per l'uso di Microsoft 365 in una posizione specifica dell'ufficio. Il test di connettività di Microsoft 365 consente di identificare la causa principale del problema, determinando un'azione di miglioramento delle prestazioni di rete consigliata.

È consigliabile usare questi elementi insieme dove lo stato della qualità della rete può essere valutato per ogni sede dell'interfaccia di amministrazione di Microsoft 365 e sono disponibili altre informazioni specifiche dopo la distribuzione dei test in base al test di connettività di Microsoft 365.

>[!IMPORTANT]
>Le informazioni dettagliate sulla rete, i consigli sulle prestazioni e le valutazioni nell'interfaccia di amministrazione di Microsoft 365 sono attualmente in stato di anteprima ed è disponibile solo per i tenant di Microsoft 365 che sono stati registrati nel programma di anteprima delle funzionalità.

## <a name="what-happens-at-each-test-step"></a>Cosa accade a ogni passaggio del test

### <a name="office-location-identification"></a>Identificazione della posizione dell'ufficio

Quando si fa clic sul pulsante Esegui test, viene visualizzata la pagina di test in esecuzione e viene identificata la posizione dell'ufficio. È possibile digitare la posizione in base alla città, allo stato e al paese oppure è possibile rilevarla dal Web browser. Se lo rilevi, richiediamo la latitudine e la longitudine dal Web browser e limitiamo l'accuratezza a 300 metri per 300 m prima dell'uso. Questo perché non è necessario identificare la posizione in modo più accurato rispetto all'edificio per le prestazioni di rete. 

### <a name="javascript-tests"></a>Test JavaScript

Dopo l'identificazione della posizione dell'ufficio viene eseguito un test di latenza TCP in JavaScript e vengono richieste informazioni dal servizio sui server front-door del servizio Office 365 in uso e consigliati. Al termine, questi elementi vengono visualizzati sulla mappa e nella scheda dei dettagli in cui possono essere visualizzati prima del passaggio successivo.

### <a name="download-the-advanced-tests-client-application"></a>Scaricare l'applicazione client per i test avanzati

Viene quindi avviato il download dell'applicazione client per i test avanzati. Ci affidiamo all'utente per avviare l'applicazione client e deve avere installato anche .NET Core.

Il test della connettività di rete di Microsoft 365 è in due parti. il sito Web <https://connectivity.office.com> e un'applicazione client di Windows scaricabile che esegue test avanzati di connettività di rete. La maggior parte dei test richiede l'esecuzione dell'applicazione. I risultati verranno popolati nuovamente nella pagina Web durante l'esecuzione.

Al termine dei test del Web browser verrà richiesto di scaricare l'applicazione di test client avanzata dal sito Web. Aprire ed eseguire il file quando richiesto.

![Applicazione client per test avanzati](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>Avviare l'applicazione client di test avanzati

Una volta avviata l'applicazione client, la pagina Web verrà aggiornerà in modo da visualizzare questo messaggio e i dati di test inizieranno a essere ricevuti nella pagina Web. Viene aggiornato ogni volta che vengono ricevuti nuovi dati ed è possibile esaminare i dati non appena arrivano.

### <a name="advanced-tests-completed-and-test-report-upload"></a>Test avanzati completati e caricamento di report di test

Una volta completati i test, la pagina Web e il client dei test avanzati lo indicherà e se l'utente ha effettuato l'accesso al report di test verrà caricato nel tenant dei clienti.

## <a name="sharing-your-test-report"></a>Condivisione del report di test

Il report di test richiede l'accesso all'account di Office 365. L'amministratore seleziona la modalità di condivisione del report di test.

### <a name="sharing-your-report-with-your-administrator"></a>Condivisione del report con l'amministratore

Tutti i report di test quando si è connessi vengono condivisi con l'amministratore.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Condivisione con il team dell'account Microsoft, supporto o altro personale

I report di test che escludono qualsiasi identificazione personale vengono condivisi con i dipendenti Microsoft. Questa opzione è abilitata per impostazione predefinita e può essere disabilitata dall'amministratore nel | **Pagina Connettività** di rete nell'interfaccia di amministrazione di Microsoft 365.

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>Condivisione con altri utenti che attuino l'accesso allo stesso tenant di Office 365

È possibile scegliere gli utenti con cui condividere il report e questa opzione è abilitata per impostazione predefinita. Può anche essere disabilitata dall'amministratore.

![Condivisione di un collegamento ai risultati dei test con un utente](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>Condivisione con chiunque utilizzi un collegamento ReportID

È possibile condividere il report di test con chiunque fornendo l'accesso a un collegamento ReportID. In questo modo viene generato un URL che è possibile inviare a un utente in modo che possa visualizzare il report di test senza effettuare l'accesso. Questa opzione è disabilitata per impostazione predefinita e deve essere abilitata dall'amministratore.

![Condivisione di un collegamento ai risultati dei test](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>Risultati del test della connettività di rete

I risultati vengono visualizzati nelle **schede Riepilogo** **e** Dettagli. La scheda di riepilogo mostra una mappa del perimetro di rete rilevato e un confronto della valutazione della rete con altri clienti di Office 365 nelle vicinanze. Consente inoltre la condivisione del report di test. Ecco l'aspetto della visualizzazione dei risultati di riepilogo.

![Risultati di riepilogo dello strumento di test della connettività di rete](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

Ecco un esempio dell'output della scheda dei dettagli mostrato con lo strumento. Nella scheda dei dettagli viene visualizzato un segno di spunta di cerchio verde se il risultato è stato confrontato favorevolmente con una soglia. Mostriamo un punto esclamativo di triangolo rosso se il risultato ha superato una soglia che indica una conoscenza della rete. Le sezioni seguenti descrivono ognuna delle righe dei risultati della scheda dettagli e illustrano le soglie utilizzate per le informazioni dettagliate sulla rete.

![Risultati dei test dello strumento di test della connettività di rete](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>Informazioni sulla posizione

In questa sezione vengono mostrati i risultati dei test correlati alla posizione.

#### <a name="your-location"></a>La tua posizione

La posizione dell'utente viene rilevata dal Web browser degli utenti oppure può essere digitata a scelta dell'utente. Viene utilizzato per identificare le distanze di rete verso parti specifiche del perimetro della rete aziendale. Nel report vengono salvate solo la città del rilevamento della posizione e la distanza da altri punti di rete.

La posizione dell'ufficio dell'utente viene visualizzata nella visualizzazione mappa.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>Posizione di uscita dalla rete (posizione in cui la rete si connette all'ISP)

L'indirizzo IP di uscita dalla rete viene identificato sul lato server. I database delle località vengono utilizzati per cercare il percorso approssimativo per l'uscita di rete. Questi database hanno in genere un'accuratezza di circa il 90% degli indirizzi IP. Se il percorso cercato dall'indirizzo IP di uscita dalla rete non è accurato, ciò potrebbe portare a un risultato falso da questo test. Per verificare se si verifica questo errore per un indirizzo IP specifico, è possibile utilizzare siti Web di posizione dell'indirizzo IP di rete pubblicamente accessibili da confrontare con la posizione effettiva.

#### <a name="your-distance-from-the-network-egress-location"></a>La distanza dalla posizione di uscita dalla rete

Microsoft determina la distanza da tale posizione alla sede dell'ufficio. Ciò viene mostrato come informazioni dettagliate  sulla rete se la distanza è superiore a 800 chilometri, poiché è probabile che la latenza TCP aumenti di oltre 25 ms e possa influire sull'esperienza utente.

La posizione di uscita dalla rete viene visualizzata nella visualizzazione mappa e connessa alla posizione dell'ufficio dell'utente che indica il backhaul di rete all'interno della wan aziendale.

L'implementazione dell'uscita dalla rete locale e diretta dalle posizioni degli uffici degli utenti a Internet è consigliata per la connettività di rete di Microsoft 365. I miglioramenti all'uscita locale e diretta sono il modo migliore per affrontare queste informazioni dettagliate sulla rete.

#### <a name="proxy-server-information"></a>Informazioni sul server proxy

Identifiamo i server proxy configurati nel computer locale. Viene identificato se una di queste impostazioni è configurata nel percorso di rete per ottimizzare il traffico di rete di Microsoft 365. Viene identificata la distanza tra la sede dell'utente e i server proxy. La distanza viene testata prima dal ping ICMP e, in caso di esito negativo, viene eseguito il test con il ping TCP e infine, in caso di esito negativo, viene eseguita la ricerca dell'indirizzo IP del server proxy in un database delle località degli indirizzi IP. Viene mostrata una panoramica della rete  se il server proxy si trova a più di 800 chilometri dalla sede dell'utente.

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>Rete privata virtuale (VPN) utilizzata per connettersi all'organizzazione

Questo rileva se si usa una VPN per connettersi a Office 365. Un risultato che passa verrà visualizzato se non si dispone di una VPN o se si dispone di una VPN con la configurazione split tunneling consigliata per Office 365.

#### <a name="vpn-split-tunnel"></a>Split Tunneling VPN

Ogni route di categoria ottimizzata per Exchange Online, SharePoint Online e Microsoft Teams viene testata per verificare se è stata o meno instradata nella VPN. Un carico di lavoro suddiviso evita completamente la VPN. Un carico di lavoro con tunneling viene inviato attraverso la VPN. Un carico di lavoro selettivo con tunneling include alcune route inviate tramite VPN e altre suddivise. Se tutti i carichi di lavoro sono suddivisi o selettivi, verrà visualizzato un risultato che indica se tutti i carichi di lavoro sono suddivisi o selettivi.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>Clienti nell'area metropolitana con prestazioni migliori

La latenza TCP di rete della sede dell'utente all'ingresso del servizio Exchange Online viene confrontata con altri clienti di Microsoft 365 nella stessa area della metropolitana. Se il 10% o più clienti nella stessa area della metropolitana hanno prestazioni migliori, viene visualizzata una panoramica della rete. Ciò significa che gli utenti avranno prestazioni migliori nell'interfaccia utente di Microsoft 365.

Queste informazioni sulla rete vengono generate sulla base del fatto che tutti gli utenti di una città hanno accesso alla stessa infrastruttura di telecomunicazione e alla stessa prossimità ai circuiti Internet e alla rete Di Microsoft.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>Tempo per effettuare una richiesta DNS sulla rete

Mostra il server DNS configurato nel computer client che ha eseguito i test. Potrebbe trattarsi di un server resolver ricorsivo DNS, ma non è raro. È più probabile che si tratta di un server d'inoltro DNS che memorizza nella cache i risultati DNS e inoltra eventuali richieste DNS non memorizzate nella cache a un altro server DNS.

Questo viene fornito solo a scopo di informazioni e non contribuisce ad alcuna analisi della rete.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>La distanza da e/o il tempo necessario per connettersi a un resolver ricorsivo DNS

Il resolver ricorsivo DNS in uso viene identificato effettuando una richiesta DNS specifica e quindi richiedendo al server dei nomi DNS l'indirizzo IP da cui ha ricevuto la stessa richiesta. Questo indirizzo IP è il resolver ricorsivo DNS e verrà cercato nei database delle località degli indirizzi IP per trovare il percorso. Viene quindi calcolata la distanza dalla sede dell'utente alla posizione del server del resolver ricorsivo DNS. Questo viene visualizzato come approfondimento della rete se la distanza è maggiore di **800** chilometri.

Il percorso cercato dall'indirizzo IP di uscita dalla rete potrebbe non essere accurato e ciò potrebbe portare a un risultato falso da questo test. Per verificare se si verifica questo errore per un indirizzo IP specifico, è possibile utilizzare siti Web di posizione indirizzo IP di rete accessibili pubblicamente.

Queste informazioni dettagliate sulla rete incideranno in modo specifico sulla selezione della porta d'ingresso del servizio Exchange Online. Per risolvere questo problema, l'uscita dalla rete locale e diretta deve essere un requisito preliminare e quindi il resolver ricorsivo DNS deve trovarsi vicino a tale uscita di rete.

### <a name="exchange-online"></a>Exchange Online

Questa sezione mostra i risultati dei test relativi a Exchange Online.

#### <a name="exchange-service-front-door-location"></a>Posizione della porta principale del servizio Exchange

Il front door del servizio Exchange in uso viene identificato nello stesso modo in cui Outlook esegue questa operazione e viene misurata la latenza TCP di rete dalla posizione dell'utente. Viene visualizzata la latenza TCP e la porta d'ingresso del servizio Exchange in uso viene confrontata con l'elenco delle porte anteriori del servizio migliori per la posizione corrente. Questo viene visualizzato come informazioni dettagliate sulla rete se non è in uso uno dei migliori front door del servizio Exchange.

Il non utilizzo di uno dei migliori front door del servizio Exchange potrebbe essere causato dal backhaul di rete prima dell'uscita della rete aziendale, nel qual caso è consigliabile l'uscita dalla rete locale e diretta. Potrebbe anche essere causato dall'uso di un server resolver ricorsivo DNS remoto, nel qual caso è consigliabile allineare il server del resolver ricorsivo DNS all'uscita dalla rete.

Viene calcolato un potenziale miglioramento della latenza TCP (ms) al front door del servizio Exchange. Per ottenere questo risultato, si esamina la latenza di rete della posizione dell'ufficio dell'utente testato e si sottrae la latenza di rete dalla posizione corrente alla porta d'ingresso del servizio Exchange. La differenza rappresenta le potenziali opportunità di miglioramento.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>Porta d'ingresso del servizio Exchange migliore per la propria posizione

In questo elenco sono elencate le migliori posizioni della porta d'ingresso del servizio Exchange per città per la posizione.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Porta anteriore del servizio registrata nel DNS client

In questo modo vengono visualizzati il nome DNS e l'indirizzo IP del server front-door del servizio Exchange a cui è stato indirizzato l'utente. Viene fornito solo per le informazioni e non sono disponibili informazioni dettagliate sulla rete associate.

### <a name="sharepoint-online"></a>SharePoint Online

Questa sezione mostra i risultati dei test correlati a SharePoint Online e OneDrive.

#### <a name="the-service-front-door-location"></a>Posizione della porta principale del servizio

La porta d'ingresso del servizio SharePoint in uso è identificata nello stesso modo in cui si trova il client di OneDrive e viene misurata la latenza TCP di rete dalla posizione dell'ufficio dell'utente.

#### <a name="download-speed"></a>Velocità di download

La velocità di download per un file di 15 Mb viene misurata dal front door del servizio SharePoint. Il risultato viene visualizzato in megabyte al secondo per indicare le dimensioni del file in megabyte che possono essere scaricate da SharePoint o OneDrive in **un secondo.** Il numero deve essere simile a un decimo della larghezza di banda minima del circuito in megabit al secondo. Ad esempio, se si dispone di una connessione Internet a 100 mbps, è possibile prevedere 10 megabyte al secondo (10 MBps).

#### <a name="buffer-bloat"></a>Buffer bloat

Durante il download da 15 Mb viene misurata la latenza TCP per il front door del servizio SharePoint. Questa è la latenza sotto carico e viene confrontata con la latenza quando non è sotto carico. L'aumento della latenza in caso di carico è spesso attribuibile ai buffer dei dispositivi di rete consumer caricati (o gonfiati). Viene visualizzata una panoramica della rete per qualsiasi gonfiabile di 1.000 o più.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Porta anteriore del servizio registrata nel DNS client

Vengono visualizzati il nome DNS e l'indirizzo IP del server front-door del servizio SharePoint a cui è stato indirizzato l'utente. Viene fornito solo per le informazioni e non sono disponibili informazioni dettagliate sulla rete associate.

### <a name="microsoft-teams"></a>Microsoft Teams

Questa sezione mostra i risultati dei test correlati a Microsoft Teams.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>Connettività multimediale (audio, video e condivisione applicazioni)

In questo modo viene verificata la connettività UDP all'ingresso del servizio Microsoft Teams. Se il problema è bloccato, Microsoft Teams potrebbe comunque funzionare con TCP, ma l'audio e il video saranno compromessi. Altre informazioni su queste misurazioni della rete UDP che si applicano anche a Microsoft Teams in Qualità multimediale e Prestazioni della connettività di [rete in Skype for Business online](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

#### <a name="packet-loss"></a>Perdita di pacchetti

Mostra la perdita di pacchetti UDP misurata in una chiamata audio di prova di 10 secondi dal client all'ingresso del servizio Microsoft Teams. Il valore deve essere inferiore **all'1,00%** per un passaggio.

#### <a name="latency"></a>Latenza

Mostra la latenza UDP misurata, che deve essere inferiore a **100 ms.**

#### <a name="jitter"></a>Instabilità

Mostra l'instabilità UDP misurata, che deve essere inferiore a **30 ms.**

#### <a name="connectivity"></a>Connettività

Viene verificata la connettività HTTP dalla posizione dell'ufficio dell'utente a tutti gli endpoint di rete di Microsoft 365 necessari. Questi sono pubblicati all'indirizzo [https://aka.ms/o365ip](https://aka.ms/o365ip) . Vengono visualizzate informazioni dettagliate sulla rete per tutti gli endpoint di rete necessari a cui non è possibile connettersi.

La connettività può essere bloccata da un server proxy, da un firewall o da un altro dispositivo di sicurezza di rete nel perimetro della rete aziendale. La connettività alla porta TCP 80 viene testata con una richiesta HTTP e la connettività alla porta TCP 443 viene testata con una richiesta HTTPS. Se non è presente alcuna risposta, il nome di dominio completo viene contrassegnato come errore. Se è presente un codice di risposta HTTP 407, il nome di dominio completo viene contrassegnato come errore. Se è presente un codice di risposta HTTP 403, viene verificato l'attributo Server della risposta e, se sembra essere un server proxy, viene contrassegnato come errore. Puoi simulare i test eseguiti con lo strumento da riga di comando di Windows curl.exe.

Il certificato SSL viene testato in ogni endpoint di rete di Microsoft 365 necessario che si trova nella categoria di ottimizzazione o di autorizzazione come definito in [https://aka.ms/o365ip](https://aka.ms/o365ip) . Se alcuni test non trovano un certificato SSL Microsoft, la rete crittografata connessa deve essere stata intercettata da un dispositivo di rete intermedio. Le informazioni dettagliate sulla rete vengono visualizzate in tutti gli endpoint di rete crittografati intercettati.

Se viene trovato un certificato SSL non fornito da Microsoft, viene visualizzato il nome di dominio completo per il test e il proprietario del certificato SSL in uso. Il proprietario del certificato SSL può essere un fornitore di server proxy o un certificato autofirmato aziendale.

#### <a name="network-path"></a>Percorso di rete

Questa sezione mostra i risultati di una traccia ICMP verso la porta d'ingresso del servizio Exchange Online, la porta d'ingresso del servizio SharePoint Online e la porta d'ingresso del servizio Microsoft Teams. Viene fornito solo per le informazioni e non sono disponibili informazioni dettagliate sulla rete associate. Sono disponibili tre traceroute. Un traceroute a _outlook.office365.com,_ un traceroute per il front-end di SharePoint dei clienti o _a microsoft.sharepoint.com_ se non ne è stato fornito uno e un traceroute a _world.tr.teams.microsoft.com_.

## <a name="connectivity-reports"></a>Rapporti di connettività

Dopo aver eseguito l'accesso, è possibile esaminare i report precedenti eseguiti. Puoi anche condividerli o eliminarli dall'elenco.

![Report](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>Stato di integrità della rete

Questo mostra eventuali problemi di integrità significativi con la rete globale di Microsoft che potrebbero influire sui clienti di Microsoft 365.

![Stato di integrità della rete](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>Domande frequenti

Ecco le risposte ad alcune delle domande frequenti.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>Questo strumento è stato rilasciato e supportato da Microsoft?

Attualmente è un'anteprima e microsoft prevede di fornire aggiornamenti regolarmente fino a quando non raggiungiamo lo stato di rilascio della disponibilità generale con il supporto di Microsoft. Fornisci feedback per aiutarci a migliorare. Microsoft prevede di pubblicare una guida di onboarding di rete di Office 365 più dettagliata come parte di questo strumento, che viene personalizzato per l'organizzazione in base ai risultati dei test.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>Cosa è necessario per eseguire il client di test avanzato?

Il client di test avanzato richiede .NET Core 3.1 Desktop Runtime. Se si esegue il client di test avanzato senza che sia installato, si verrà reindirizzati alla pagina del programma di installazione [di .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1) Assicurati di installare Desktop Runtime e non l'SDK o ASP.NET Core Runtime più in alto nella pagina. Per installare .NET Core sono necessarie le autorizzazioni di amministratore nel computer.

### <a name="what-is-microsoft-365-service-front-door"></a>Che cos'è la porta d'ingresso del servizio Microsoft 365?

La porta d'ingresso del servizio Microsoft 365 è un punto di ingresso nella rete globale di Microsoft in cui i client e i servizi di Office terminano la connessione di rete. Per una connessione di rete ottimale a Microsoft 365, è consigliabile che la connessione di rete venga terminata nella porta d'ingresso di Microsoft 365 più vicina nella città o nella metropolitana.

Nota: la porta d'ingresso del servizio Microsoft 365 non ha alcuna relazione diretta con il prodotto **Azure Front Door Service** disponibile in Azure Marketplace.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>Qual è la migliore porta d'ingresso del servizio Microsoft 365?

Una migliore porta d'ingresso del servizio Microsoft 365 (in precedenza nota come porta di servizio ottimale) è quella più vicina all'uscita della rete, in genere nella città o nella zona della metropolitana. Usare lo strumento per le prestazioni di rete di Microsoft 365 per determinare la posizione della porta d'ingresso del servizio Microsoft 365 in uso e la porta d'ingresso del servizio migliore. Se lo strumento determina che la porta d'ingresso in uso è una delle migliori, è consigliabile aspettarsi una connettività ottimale nella rete globale di Microsoft.

### <a name="what-is-an-internet-egress-location"></a>Che cos'è una posizione di uscita da Internet?

La posizione di uscita da Internet è la posizione in cui il traffico di rete esce dalla rete aziendale e si connette a Internet. Viene inoltre identificato come la posizione in cui si dispone di un dispositivo NAT (Network Address Translation) e in genere in cui ci si connette con un provider di servizi Internet (ISP). Se viene visualizzata una lunga distanza tra la posizione e la posizione di uscita da Internet, è possibile identificare un backhaul WAN significativo.

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md)

[Informazioni dettagliate sulle prestazioni di rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-insights.md)

[Valutazione della rete di Microsoft 365 (anteprima)](office-365-network-mac-perf-score.md)

[Microsoft 365 Network Connectivity Location Services (anteprima)](office-365-network-mac-location-services.md)
