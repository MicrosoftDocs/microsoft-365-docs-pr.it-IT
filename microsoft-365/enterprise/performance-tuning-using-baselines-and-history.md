---
title: Ottimizzazione delle prestazioni di Office 365 con le linee di base e la cronologia delle prestazioni
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/31/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 1492cb94-bd62-43e6-b8d0-2a61ed88ebae
ms.collection:
- M365-security-compliance
- Ent_O365
- SPO_Content
description: Informazioni su come controllare la cronologia delle connessioni dei computer client per individuare precocemente i problemi emergenti.
ms.openlocfilehash: 2337b14542f894e9a62037b2f032632147e45e09
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691218"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Ottimizzazione delle prestazioni di Office 365 con le linee di base e la cronologia delle prestazioni

Esistono alcuni modi semplici per controllare le prestazioni della connessione tra Office 365 e la propria azienda che consentirà di stabilire una linea di base approssimativa della connettività. Se si conosce la cronologia delle prestazioni delle connessioni dei computer client, è possibile rilevare i problemi emergenti in anticipo, identificare e stimare.
  
Se non si è abituati a lavorare sui problemi di prestazioni, questo articolo è stato creato per aiutare a prendere in considerazione alcune domande comuni, come sapere se il problema che si sta vedendo è un problema di prestazioni e non un incidente di servizio di Office 365? Come si può pianificare una buona prestazione, a lungo termine? Come si può tenere d'occhio le prestazioni? Se il team o i client stanno visualizzando le prestazioni lente durante l'utilizzo di Office 365 e si chiede se si tratta di una di queste domande, leggere.
  
> [!IMPORTANT]
> **Si dispone di un problema di prestazioni tra il client e Office 365 in questo momento?** Seguire la procedura descritta nel [piano di risoluzione dei problemi relativi alle prestazioni per Office 365](performance-troubleshooting-plan.md). 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Qualcosa che è necessario conoscere le prestazioni di Office 365

Office 365 risiede all'interno di una rete Microsoft dedicata e a elevata capacità, che viene costantemente monitorata non solo dall'automazione, ma da persone reali. Parte del ruolo di manutenzione del cloud di Office 365 è l'ottimizzazione delle prestazioni e la razionalizzazione dei casi in cui è possibile. Poiché i client del cloud di Office 365 devono connettersi su Internet, è possibile ottimizzare le prestazioni anche tra i servizi di Office 365. I miglioramenti delle prestazioni non si interrompono mai nel cloud e sono presenti molte esperienze accumulate con la conservazione del cloud in modo rapido e integro. Se si verifica un problema di prestazioni che si connette dal percorso a Office 365, è preferibile non iniziare e attendere un caso di supporto. In alternativa, è consigliabile iniziare a esaminare il problema da "all'interno". In altri termini, iniziare dall'interno della rete e procedere con l'uscita a Office 365. Prima di aprire un caso con il supporto di Office 365, è possibile raccogliere dati e intraprendere azioni che analizzino e possano risolvere il problema.
  
> [!IMPORTANT]
> Tenere conto della pianificazione della capacità e dei limiti in Office 365. Tali informazioni consentiranno di superare la curva quando si tenta di risolvere un problema di prestazioni. Di seguito è indicato un collegamento alle [descrizioni del servizio Microsoft 365 e Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library). Si tratta di un hub centrale e tutti i servizi offerti da Office 365 dispongono di un collegamento che passa alla propria descrizione dei servizi da qui. Questo significa che, se è necessario visualizzare i limiti standard per SharePoint Online, ad esempio, fare clic su [Descrizione servizio SharePoint Online](https://technet.microsoft.com/library/sharepoint-online-service-description.aspx) e individuare la [sezione limiti di SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113). 
  
Assicurarsi di andare alla risoluzione dei problemi con la comprensione che le prestazioni sono una scala scorrevole, non si tratta di ottenere un valore idealizzato e di mantenerlo permanentemente (se si ritiene che sia così, quindi occasionali attività a larghezza di banda elevata come l'imbarco di un numero elevato di utenti o la migrazione di dati di grandi dimensioni saranno molto stressanti). È possibile, e deve, avere una vaga idea dei vostri obiettivi di prestazioni, ma molte variabili giocano nelle prestazioni, pertanto, le prestazioni variano. Questa è la natura delle prestazioni. 
  
La risoluzione dei problemi relativi alle prestazioni non riguarda la riunione di obiettivi specifici e la gestione di tali numeri a tempo indeterminato, ovvero il miglioramento delle attività esistenti, date tutte le variabili. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Ok, che aspetto ha un problema di prestazioni?

In primo luogo, è necessario assicurarsi che le operazioni riscontrate siano effettivamente un problema di prestazioni e non un incidente di servizio. Un problema di prestazioni è diverso da un incidente di servizio in Office 365. Ecco come distinguerli.
  
Se il servizio Office 365 ha problemi, si tratta di un incidente di servizio. Nell'interfaccia di amministrazione di Microsoft 365 vengono visualizzate icone rosse o gialle in **stato di integrità corrente** , è anche possibile notare prestazioni lente sui computer client che si connettono a Office 365. Ad esempio, se lo stato corrente segnala un'icona rossa e si visualizza l' **analisi** accanto a Exchange, è possibile ricevere anche un gruppo di chiamate provenienti da persone dell'organizzazione che si lamentano che le cassette postali client che utilizzano Exchange Online stanno eseguendo una cattiva esecuzione. In tal caso, è ragionevole presumere che le prestazioni di Exchange Online siano diventate solo una vittima di problemi all'interno del servizio. 
  
![Dashboard di integrità di Office 365 con tutti i carichi di lavoro che mostrano verde, tranne Exchange, in cui viene visualizzato il servizio ripristinato.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
A questo punto, l'amministratore di Office 365 deve controllare l' **integrità corrente** e quindi **visualizzare i dettagli e la cronologia**, spesso, per essere sempre aggiornati sulle operazioni di manutenzione eseguite nel sistema. Il dashboard di **integrità corrente** è stato creato per aggiornare le modifiche apportate al servizio e i relativi problemi. Le note e le spiegazioni scritte nella cronologia dell'integrità, dall'amministratore all'amministratore, sono disponibili per aiutarti a valutare l'impatto e a mantenere la pubblicazione sul lavoro in atto. 
  
![Un'immagine del dashboard di integrità di Office 365 che spiega che il servizio Exchange Online è stato ripristinato e perché.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Un problema di prestazioni non è un incidente di servizio, anche se gli incidenti possono causare una prestazione lenta. Un problema di prestazioni è simile al seguente:
  
- Si verifica un problema di prestazioni indipendentemente dall' **integrità corrente** del centro di amministrazione per il servizio. 
    
-  Un comportamento utilizzato per essere relativamente semplice richiede molto tempo per il completamento o non viene mai completato. 
    
- È possibile replicare il problema troppo o, almeno, si è certi che accadrà se si esegue la serie di passaggi corretti.
    
-  Se il problema è intermittente, vi è ancora un modello, ad esempio, si sa che per 10:00 AM si avranno chiamate provenienti da utenti che non sono in grado di accedere in modo attendibile a Office 365 e che le chiamate si estingueranno verso mezzogiorno. 
    
Questo probabilmente suona familiare; Forse troppo familiare. Una volta che si sa che si tratta di un problema di prestazioni, la domanda diventa: "cosa fare dopo?" Il resto di questo articolo aiuta a determinare esattamente questo.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Come definire e testare il problema delle prestazioni

I problemi di prestazioni spesso emergono nel tempo, quindi può essere difficile definire il problema reale. È necessario creare un'istruzione Good problem e una buona idea del contesto del problema e quindi è necessario ripetere i passaggi di test per vincere la giornata. In caso contrario, non è possibile che si verifichino errori. Perché? Ebbene, ecco alcuni esempi di istruzioni relative ai problemi che non forniscono informazioni sufficienti:
  
- Passare dalla posta in arrivo al calendario utilizzato per essere una cosa che non ho notato e ora è un'interruzione di caffè. È possibile farlo agire come prima?
    
- Il caricamento di file personali in SharePoint Online richiede sempre. Perché è lento nel pomeriggio, ma qualsiasi altro momento, è veloce? Non può essere solo veloce?
    
Sono presenti diverse grandi sfide poste dalle istruzioni sul problema sopra riportate. In particolare, sono presenti molte ambiguità da gestire. Per esempio:
  
- Non è chiaro in che modo il passaggio tra posta in arrivo e calendario utilizzato per agire sul laptop.
    
- Quando l'utente dice: "non è solo veloce", che cos'è "Fast"?
    
- Per quanto tempo è "Forever"? È che alcuni secondi, o minuti, o l'utente può andare a pranzo e sarebbe finire dieci minuti dopo che l'utente è tornato?
    
Tutto ciò non può essere considerato che l'amministratore e la risoluzione dei problemi non possono essere a conoscenza di molti dettagli delle istruzioni relative ai problemi come questi. Ad esempio, quando si verifica il problema. Il fatto che l'utente funzioni da casa e veda solo il cambio lento in una rete domestica; Che l'utente deve eseguire diverse altre applicazioni di RAM intensiva nel client locale o che l'utente esegua un sistema operativo meno recente o che non esegua aggiornamenti recenti.
  
Quando gli utenti segnalano un problema di prestazioni, sono presenti numerose informazioni da raccogliere. La raccolta di queste informazioni è parte di un processo denominato ambito del problema o di analisi. Di seguito è riportato un elenco di base di ambito che è possibile utilizzare per raccogliere informazioni sul problema delle prestazioni. Questo elenco non è esaustivo, ma è un luogo in cui è possibile eseguire una delle operazioni seguenti: 
  
- In quale data si è verificata la problematica e circa l'ora del giorno o della notte?
    
- Che tipo di computer client stavi usando e come si connette alla rete aziendale (VPN, Wired, wireless)?
    
- Se si lavora in remoto o si è in ufficio?
    
- Si è tentato di eseguire le stesse operazioni su un altro computer e si vede lo stesso comportamento?
    
- È possibile eseguire la procedura che consente di scrivere le azioni che si stanno creando.
    
- Le prestazioni sono rallentate in secondi o minuti?
    
- Dove si trovano in tutto il mondo?
    
Alcune di queste domande sono più evidenti di altre. La maggior parte di tutti capirà che un risoluzione dei problemi richiederà i passaggi esatti per riprodurre il problema. Dopo tutto, in quale altro modo è possibile registrare ciò che è sbagliato e in quale altro modo è possibile verificare se il problema è stato risolto? Meno evidenti sono cose come "data e ora in cui è stato visualizzato il problema?" e "dove nel mondo si trova?", informazioni che possono essere utilizzate in tandem. A seconda della modalità di funzionamento dell'utente, alcune ore di differenza di tempo possono significare che la manutenzione è già in corso in parti della rete aziendale. Se ad esempio la società ha un'implementazione ibrida, come una ricerca ibrida di SharePoint, in grado di eseguire query sugli indici di ricerca in SharePoint Online e in un'istanza di SharePoint Server 2013 locale, è possibile che gli aggiornamenti siano in corso nella farm locale. Se l'azienda è tutto nel cloud, la manutenzione del sistema può includere l'aggiunta o la rimozione di hardware di rete, l'implementazione di aggiornamenti a livello di azienda o la modifica del DNS o di un'altra infrastruttura di base.
  
Quando si esegue la risoluzione di un problema di prestazioni, è un po' come una scena del crimine, è necessario essere precisi e attento a trarre conclusioni dall'evidenza. Per eseguire questa operazione, è necessario ottenere un'istruzione di buon problema tramite la raccolta di elementi probatori. Dovrebbe includere il contesto del computer, il contesto dell'utente, quando il problema è iniziato, e la procedura esatta che ha esposto il problema delle prestazioni. Questa dichiarazione del problema dovrebbe essere, e rimanere, la pagina di primo livello nelle note. Se si esegue di nuovo l'istruzione del problema dopo aver eseguito la risoluzione, vengono eseguite le operazioni necessarie per testare e verificare se le azioni intraprese hanno risolto il problema. Questo è fondamentale per sapere quando il lavoro è stato completato.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Si sa in che modo le prestazioni sono state utilizzate per l'aspetto quando è stato utile?

Se si è sfortunati, nessuno lo sa. Nessuno aveva numeri. Questo significa che nessuno può rispondere alla domanda semplice "informazioni su quanti secondi sono stati utilizzati per visualizzare una posta in arrivo in Office 365?" oppure "per quanto tempo è stato utilizzato quando i dirigenti avevano una riunione di Lync Online?", che è uno scenario comune per molte aziende.
  
Ciò che manca è una previsione delle prestazioni.
  
Le linee di base forniscono un contesto per le prestazioni. A seconda delle esigenze della propria azienda, è consigliabile utilizzare occasionalmente una linea di base. Se si è una società di dimensioni maggiori, il team operativo può già prendere le previsioni per l'ambiente locale. Ad esempio, se si esegue la patch di tutti i server di Exchange del primo lunedì del mese e di tutti i server di SharePoint il terzo lunedì, il team operativo ha probabilmente un elenco di attività e scenari che eseguono la post-Patching per dimostrare che le funzioni critiche sono operative. Ad esempio, aprire la posta in arrivo, fare clic su Invia/Ricevi e verificare che le cartelle vengano aggiornate oppure, in SharePoint, esplorare la pagina principale del sito, accedere alla pagina di ricerca dell'organizzazione ed eseguire una ricerca che restituisca i risultati.
  
Se le applicazioni sono presenti in Office 365, alcune delle linee di base più importanti è possibile misurare il tempo (in millisecondi) da un computer client all'interno della rete, a un punto di uscita o al punto in cui si lascia la rete e si esce a Office 365. Di seguito sono riportate alcune utili linee di base che è possibile analizzare e registrare:
  
- Identificare i dispositivi tra il computer client e il punto di uscita, ad esempio il server proxy.
    
  - È necessario conoscere i dispositivi in modo da disporre di un contesto (indirizzi IP, tipo di dispositivo e così via) per i problemi di prestazioni che si verificano.
    
  - I server proxy sono punti di uscita comuni, quindi è possibile controllare il Web browser per visualizzare il server proxy che è impostato per l'utilizzo, se disponibile.
    
  - Sono disponibili strumenti di terze parti in grado di individuare e mappare la rete, ma il modo più sicuro per conoscere i dispositivi consiste nel chiedere a un membro del team di rete.
    
- Identificare il provider di servizi Internet (ISP), annotare le informazioni di contatto e chiedere quanti circuiti è la quantità di larghezza di banda.
    
- All'interno dell'azienda, identificare le risorse per i dispositivi tra il client e il punto di uscita oppure identificare un contatto di emergenza a cui rivolgersi per informazioni sui problemi di rete.
    
Di seguito sono riportate alcune linee di base che è possibile eseguire il calcolo semplice con gli strumenti:
  
- Tempo dal computer client al punto di uscita in millisecondi
    
- Data e ora dal punto di uscita a Office 365 in millisecondi
    
- Percorso nel mondo del server che risolve gli URL di Office 365 quando si Esplora
    
- Velocità della risoluzione DNS dell'ISP in millisecondi, incoerenze nell'arrivo dei pacchetti (instabilità della rete), tempi di caricamento e download in millisecondi
    
Se non si ha familiarità con l'esecuzione di questi passaggi, in questo articolo verranno illustrati più in dettaglio. 
  
## <a name="what-is-a-baseline"></a>Che cos'è una linea di base?

È possibile conoscere l'impatto quando si verificano problemi, ma se non si conoscono i dati relativi alle prestazioni cronologiche, non si può avere un contesto in cui potrebbe essere stato danneggiato e quando. Quindi, senza una linea di base, si sta perdendo l'indizio chiave per risolvere il puzzle: l'immagine nella casella puzzle. Per la risoluzione dei problemi relativi alle prestazioni, è necessario un punto di  *confronto*  . Le linee di base per le prestazioni semplici non sono difficili da eseguire. Il team operativo può essere incaricato di eseguire queste operazioni in base a una pianificazione. Ad esempio, si supponga che la connessione sia simile alla seguente: 
  
![Un grafico di rete di base che Mostra client, proxy e cloud di Office 365.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Questo significa che è stato verificato con il team di rete e ha scoperto che si lascia l'azienda per Internet tramite un server proxy e che il proxy gestisce tutte le richieste inviate dal computer client al cloud. In questo caso, è consigliabile disegnare una versione semplificata della connessione in cui sono elencati tutti i dispositivi che intervengono. A questo punto, inserire gli strumenti che è possibile utilizzare per testare le prestazioni tra il client, l'area di uscita (in cui si lascia la rete per Internet) e il cloud di Office 365.
  
![Rete di base con client, proxy e cloud e suggerimenti per gli strumenti PSPing, TraceTCP e le tracce di rete.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
Le opzioni sono elencate come **semplici** e **Avanzate** a causa della quantità di conoscenze necessarie per trovare i dati sulle prestazioni. Una traccia di rete richiede molto tempo rispetto all'esecuzione di strumenti della riga di comando come PsPing e TraceTCP. Questi due strumenti della riga di comando sono stati scelti perché non utilizzano pacchetti ICMP, che verranno bloccati da Office 365, e perché forniscono il tempo in millisecondi necessari per lasciare il computer client o il server proxy (se si ha accesso) e arrivare a Office 365. Ogni singolo hop da un computer a un altro si concluderà con un valore di tempo e questo è l'ideale per le linee di base. Altrettanto importante, questi strumenti della riga di comando consentono di aggiungere un numero di porta al comando, questo è utile perché Office 365 comunica con la porta 443, ovvero la porta utilizzata da Secure Sockets Layer e Transport Layer Security (SSL e TLS). Tuttavia, altri strumenti di terze parti possono essere soluzioni migliori per la propria situazione. Microsoft non supporta tutti questi strumenti, quindi se, per qualche motivo, non è possibile ottenere PsPing e TraceTCP di lavoro, passare a una traccia di rete con uno strumento come Netmon. 
  
È possibile prendere una linea di base prima dell'orario di ufficio, di nuovo durante l'uso intensivo, e poi di nuovo dopo ore. Questo significa che potrebbe essere presente una struttura di cartelle che sembra un po' simile alla fine:
  
![Grafica che propone una soluzione per organizzare i dati delle prestazioni in cartelle.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
È inoltre necessario scegliere una convenzione di denominazione per i file. Ecco alcuni esempi:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
Sono disponibili diversi modi per eseguire questa operazione, ma l'utilizzo del formato **\<dateTime\>\<what's happening in the test\>** è un buon punto di partenza. Essere diligenti in questo modo sarà di grande aiuto quando si tenta di risolvere i problemi in un secondo momento. Successivamente, potrai dire "ho scattato due tracce l'8 febbraio, una ha mostrato una buona prestazione e una cattiva, quindi possiamo confrontarle". Questo è estremamente utile per la risoluzione dei problemi. 
  
È necessario disporre di un metodo organizzato per mantenere le linee di base storiche. In questo esempio, i metodi semplici hanno prodotto tre output della riga di comando e i risultati sono stati raccolti come schermate, ma è possibile che vengano invece creati file di acquisizione di rete. Utilizzare il metodo più adatto per l'utente. Archiviare le linee di base cronologiche e fare riferimento a essi in punti in cui si notano modifiche del comportamento dei servizi online. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Perché raccogliere dati sulle prestazioni durante un progetto pilota?

Non c'è momento migliore per iniziare a eseguire le linee di base rispetto a quelle di un pilota del servizio Office 365. L'ufficio può avere migliaia di utenti, centinaia di migliaia o cinque, ma anche con un numero limitato di utenti, è possibile eseguire test per misurare le fluttuazioni delle prestazioni. Nel caso di un'azienda di grandi dimensioni, un campione rappresentativo di diverse centinaia di utenti che pilotano Office 365 può essere proiettato verso l'esterno a diverse migliaia, in modo da sapere dove potrebbero verificarsi problemi prima che si verifichino.
  
Nel caso di una società di piccole dimensioni, in cui l'accesso a bordo indica che tutti gli utenti passano contemporaneamente al servizio e non è presente alcun progetto pilota, mantenere le misure di prestazioni in modo che i dati vengano visualizzati da tutti coloro che potrebbero dover risolvere un'operazione di esecuzione anomala. Ad esempio, se si nota che tutto a un tratto è possibile aggirare l'edificio nel tempo necessario per caricare un grafico di medie dimensioni in cui si è utilizzato per eseguire rapidamente.
  
## <a name="how-to-collect-baselines"></a>Come raccogliere le linee di base

Per tutti i piani di risoluzione dei problemi è necessario identificare almeno queste operazioni:
  
- Il computer client che si sta utilizzando (il tipo di computer o dispositivo, un indirizzo IP e le azioni che hanno causato il problema)
    
- In cui il computer client si trova nel mondo (ad esempio, se l'utente è presente in una VPN per la rete, funziona in remoto o nell'Intranet aziendale)
    
- Il punto di uscita utilizzato dal computer client dalla rete (il punto in cui il traffico lascia l'azienda per un ISP o Internet)
    
 È possibile trovare il layout della rete dall'amministratore di rete. Se si è in una rete di piccole dimensioni, esaminare i dispositivi che si connettono a Internet e chiamare l'ISP se si dispone di domande relative al layout. Creare un elemento grafico del layout finale per il riferimento. 
  
Questa sezione è suddivisa in semplici strumenti e metodi della riga di comando e altre opzioni per gli strumenti avanzati. Per prima cosa, verranno trattati i metodi semplici. Tuttavia, se si ha un problema di prestazioni in questo momento, è consigliabile passare ai metodi avanzati e provare il piano di azione per la risoluzione dei problemi di prestazioni di esempio.
  
### <a name="simple-methods"></a>Metodi semplici

L'obiettivo di questi metodi semplici consiste nell'imparare a prendere, comprendere e archiviare correttamente le linee di base delle prestazioni semplici nel tempo, in modo da essere informati sulle prestazioni di Office 365. Di seguito è riportato il semplice diagramma semplice, come illustrato in precedenza:
  
![Rete di base con client, proxy e cloud e suggerimenti per gli strumenti PSPing, TraceTCP e le tracce di rete.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP è incluso in questa schermata perché è uno strumento utile per mostrare, in millisecondi, la durata della richiesta di elaborazione e il numero di hop di rete o di connessioni da un computer all'altro, che la richiesta richiede per raggiungere una destinazione. TraceTCP può anche fornire i nomi dei server utilizzati durante il luppolo, il che può essere utile per una soluzione di risoluzione dei problemi di Microsoft Office 365 in supporto. > i comandi di TraceTCP possono essere molto semplici, ad esempio: >  `tracetcp.exe outlook.office365.com:443`> ricordarsi di includere il numero di porta nel comando. > [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) è un download gratuito, ma si basa su WINCAP. WINCAP è uno strumento utilizzato e installato anche da Netmon. È inoltre possibile utilizzare Netmon nella sezione Advanced methods. 
  
 Se si dispone di più uffici, è necessario mantenere un set di dati da un client in ognuno di questi percorsi. Questo test misura la latenza, che, in questo caso, è un valore numerico che descrive la quantità di tempo tra un client che invia una richiesta a Office 365 e Office 365 che risponde alla richiesta. Il testing ha origine all'interno del dominio in un computer client e cerca di misurare un round trip dall'interno della rete, tramite un punto di uscita, tramite Internet a Office 365 e viceversa. 
  
Esistono alcuni modi per gestire il punto di uscita, in questo caso il server proxy. È possibile tracciare da 1 a 2 e quindi da 2 a 3 e quindi aggiungere i numeri in millisecondi per ottenere un totale finale al bordo della rete. In alternativa, è possibile configurare la connessione per ignorare il proxy per gli indirizzi di Office 365. In una rete più grande con un firewall, un proxy inverso o una combinazione di due, potrebbe essere necessario fare eccezioni sul server proxy che consentirà al traffico di passare per un numero elevato di URL. Per l'elenco degli endpoint utilizzati da Office 365, vedere [URL e intervalli di indirizzi IP di office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Se si dispone di un proxy di autenticazione, iniziare verificando le eccezioni per gli elementi seguenti:
  
- Porte 80 e 443
    
- TCP e HTTPs
    
- Connessioni in uscita a uno di questi URL:
    
- \*. microsoftonline.com
    
- \*. microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*. outlook.com
    
- \*. lync.com
    
- osub.microsoft.com
    
È necessario consentire a tutti gli utenti di accedere a questi indirizzi senza alcuna interferenza o autenticazione del proxy. In una rete più piccola, è necessario aggiungerli all'elenco di bypass del proxy nel Web browser. 
  
Per aggiungerli all'elenco di bypass del proxy in Internet Explorer, passare a **strumenti** \> **Internet Options** \> **Connections** \> **LAN Settings** \> **Advanced**. La scheda Avanzate è anche quella in cui è possibile trovare il server proxy e la porta del server proxy. Potrebbe essere necessario fare clic sulla casella di controllo **utilizza un server proxy per la LAN**, per accedere al pulsante **Avanzate** . Sarà necessario verificare che il **server proxy bypass per gli indirizzi locali** sia selezionato. Quando si fa clic su **Avanzate**, viene visualizzata una casella di testo in cui è possibile immettere eccezioni. Separare gli URL con caratteri jolly sopra elencati con punti e virgola, ad esempio:
  
\*. microsoftonline.com; \*. SharePoint.com
  
Dopo aver ignorato il proxy, è necessario essere in grado di utilizzare ping o PsPing direttamente su un URL di Office 365. Il passaggio successivo consiste nel testare il ping **Outlook.office365.com**. In alternativa, se si utilizza PsPing o un altro strumento che consentirà di fornire un numero di porta al comando, PsPing su **Portal.microsoftonline.com:443** per visualizzare il tempo medio di andata e ritorno in millisecondi. 
  
Il tempo di andata e ritorno, o RTT, è un valore numerico che misura il tempo necessario per inviare una richiesta HTTP a un server come outlook.office365.com e ottenere una risposta che riconosce che il server sa di averlo fatto. A volte viene visualizzato questo abbreviato come RTT. Questo dovrebbe essere un periodo di tempo relativamente breve.
  
È necessario utilizzare [PSPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) o un altro strumento che non utilizza pacchetti ICMP che sono bloccati da Office 365 per eseguire questo test. 
  
 **Come usare PsPing per ottenere una durata complessiva del tragitto di andata e ritorno in millisecondi direttamente da un URL di Office 365**
  
1. Eseguire un prompt dei comandi con privilegi elevati eseguendo la procedura seguente:
    
1. Fare clic su **Avvia**.
    
2. Nella casella **Inizia ricerca** Digitare cmd e quindi premere CTRL + MAIUSC + INVIO.
    
3. Se viene visualizzata la finestra di dialogo **Controllo account utente**, confermare che l'azione visualizzata è quella desiderata e scegliere **Continua**.
    
2. Passare alla cartella in cui è installato lo strumento (in questo caso PsPing) e testare gli URL di Office 365:
    
  - psping portal.office.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![Il comando PSPing sta per microsoft-my.sharepoint.com porta 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Assicurarsi di includere il numero di porta 443. Tenere presente che Office 365 funziona su un canale crittografato. Se si PsPing senza il numero di porta, la richiesta avrà esito negativo. Dopo aver effettuato il ping dell'elenco breve, cercare la durata media in millisecondi (MS). Questo è ciò che si desidera registrare.
  
![Grafico in cui viene illustrata un'illustrazione del client per il proxy PSPing con un tempo di andata e ritorno di 2,8 millisecondi.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Se non si ha familiarità con il bypass proxy e si preferisce eseguire operazioni dettagliate, è necessario innanzitutto individuare il nome del server proxy. In Internet Explorer vai a **strumenti** \> **Internet Options** \> **Connections** \> **Impostazioni LAN** \> **Avanzate**. La scheda **Avanzate** è la posizione in cui verrà visualizzato il server proxy elencato. Eseguire il ping del server proxy al prompt dei comandi completando questa attività: 
  
 **Per eseguire il ping del server proxy e ottenere un valore di andata e ritorno in millisecondi per la fase 1-2**
  
1. Eseguire un prompt dei comandi con privilegi elevati eseguendo la procedura seguente:
    
1. Fare clic su **Avvia**.
    
2. Nella casella **Inizia ricerca** Digitare cmd e quindi premere CTRL + MAIUSC + INVIO.
    
3. Se viene visualizzata la finestra di dialogo **Controllo account utente**, confermare che l'azione visualizzata è quella desiderata e scegliere **Continua**.
    
2. Digitare ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> e quindi premere INVIO. Se si dispone di PsPing o di un altro strumento installato, è possibile scegliere di utilizzare lo strumento. 
    
    Il comando può essere simile a uno di questi esempi: 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping ourproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy: 80
    
3. Quando la traccia interrompe l'invio di pacchetti di test, si otterrà un piccolo riepilogo che elenca una media, in millisecondi, e questo è il valore che si desidera. Scattare una schermata del prompt e salvarla utilizzando la convenzione di denominazione. A questo punto può anche essere utile compilare il diagramma con il valore.
    
È possibile che la mattina presto sia stata eseguita una traccia e che il client possa accedere rapidamente al proxy (o a qualsiasi altro server in uscita su Internet). In questo caso, i numeri possono essere simili al seguente:
  
![Grafico che indica il tempo di andata e ritorno da un client a un proxy di 2,8 millisecondi.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Se il computer client è uno dei pochi selezionati con accesso al server proxy (o di uscita), è possibile eseguire la tappa successiva del test, collegandosi in remoto a quel computer, eseguendo il prompt dei comandi per PsPing a un URL di Office 365. Se non si ha accesso al computer in uso, è possibile contattare le risorse di rete per ottenere assistenza con la gamba successiva e recuperare i numeri esatti in questo modo. Se non è possibile, prendere una PsPing con l'URL di Office 365 in questione e confrontarla con la PsPing o il tempo di ping sul server proxy. 
  
Ad esempio, se si dispone di 51,84 millisecondi dal client all'URL di Office 365 e si dispone di 2,8 millisecondi dal client al proxy (o punto di uscita), si dispone di 49,04 millisecondi dall'uscita a Office 365. Analogamente, se si dispone di un PsPing di 12,25 millisecondi dal client al proxy durante l'altezza del giorno e 62,01 millisecondi dal client all'URL di Office 365, il valore medio per l'uscita del proxy all'URL di Office 365 è 49,76 millisecondi.
  
![Grafico aggiuntivo che consente di visualizzare il ping in millisecondi da client a proxy accanto a client a Office 365 in modo che i valori possano essere sottratti.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
In termini di risoluzione dei problemi, è possibile trovare qualcosa di interessante solo da mantenere queste linee di base. Ad esempio, se si rileva che in genere sono presenti circa 59 40 millisecondi di latenza dal proxy o dal punto di uscita all'URL di Office 365, e avere un client per il proxy o l'uscita latenza del punto di circa 3 a 7 millisecondi (a seconda del traffico di rete che si sta vedendo in quel momento della giornata), quindi sarà sicuramente sapere che qualcosa è problematico se le ultime tre client di proxy o di uscita di base mostrano una latenza di 45 millisecondi.
  
### <a name="advanced-methods"></a>Metodi avanzati

Se si vuole davvero sapere cosa succede con le richieste Internet a Office 365, è necessario acquisire familiarità con le tracce di rete. Non importa quali strumenti si preferisce per queste tracce, HTTPWatch, Netmon, Message Analyzer, Wireshark, Fiddler, Developer dashboard Tool o qualsiasi altro farà fino a quando tale strumento può acquisire e filtrare il traffico di rete. In questa sezione viene illustrato che è utile eseguire più di uno di questi strumenti per ottenere un'immagine più completa del problema. Quando si esegue il testing, alcuni di questi strumenti agiscono anche come proxy a proprio piacimento. Gli strumenti utilizzati nell'articolo complementare, [piano per la risoluzione dei problemi relativi alle prestazioni per Office 365](performance-troubleshooting-plan.md), includono [NetMon 3,4](https://www.microsoft.com/download/details.aspx?id=4865), [HttpWatch](https://www.httpwatch.com/download/)o [Wireshark](https://www.wireshark.org/).
  
L'esecuzione di una previsione delle prestazioni è la parte semplice di questo metodo e molti dei passaggi sono gli stessi che si verificano quando si risolve un problema di prestazioni. I metodi più avanzati per la creazione di linee di base per le prestazioni richiedono l'esecuzione e l'archiviazione delle tracce di rete. La maggior parte degli esempi descritti in questo articolo utilizza SharePoint Online, ma è consigliabile sviluppare un elenco di azioni comuni nei servizi di Office 365 a cui si sottoscrive il test e il record. Di seguito è riportato un esempio di base:
  
- Elenco di base per SPO-* * passaggio 1: * * passare alla Home page del sito Web di SPO e eseguire una traccia di rete. Salvare la traccia. 
    
- Elenco di base per SPO- **Step 2:** ricerca di un termine (ad esempio il nome della società) tramite la ricerca nell'organizzazione e eseguire una traccia di rete. Salvare la traccia. 
    
- Elenco di base per il **passaggio 3:** caricare un file di grandi dimensioni in una raccolta documenti di SharePoint Online ed eseguire una traccia di rete. Salvare la traccia. 
    
- Elenco di base per SPO- **passaggio 4:** passare alla Home page del sito Web OneDrive ed eseguire una traccia di rete. Salvare la traccia. 
    
Questo elenco deve includere le più importanti azioni comuni eseguite dagli utenti in merito a SharePoint Online. Si noti che l'ultimo passaggio, per la traccia di OneDrive for business, si basa su un confronto tra il carico della Home page di SharePoint Online (spesso personalizzato dalle aziende) e la Home page di OneDrive for business, che raramente è personalizzata. Si tratta di un test molto semplice quando si tratta di un sito di SharePoint Online con caricamento lento. È possibile creare un record di questa differenza nel testing.
  
Se si è in un problema di prestazioni, molti dei passaggi sono gli stessi di quando si effettua una linea di base. Le tracce di rete diventano critiche, quindi verrà gestito  *come*  prendere le tracce importanti successive. 
  
Per risolvere un problema di prestazioni, è necessario prendere una traccia  *al momento in*  cui si verifica il problema delle prestazioni. È necessario disporre degli strumenti appropriati disponibili per raccogliere i registri ed è necessario un piano di azione, ovvero un elenco di azioni di risoluzione dei problemi da intraprendere per raccogliere le migliori informazioni possibili. La prima cosa da fare è registrare la data e l'ora del test in modo che i file possano essere salvati in una cartella che rispecchi la tempistica. Successivamente, limitare i passaggi del problema stessi. Questi sono i passaggi esatti che verranno utilizzati per il testing. Non dimenticare le nozioni di base: se il problema è solo con Outlook, verificare che il comportamento del problema si verifica in un solo servizio di Office 365. Per limitare l'ambito di questo problema, è possibile concentrarsi su un elemento che può essere risolto. 
  
## <a name="see-also"></a>Vedere anche

[Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

