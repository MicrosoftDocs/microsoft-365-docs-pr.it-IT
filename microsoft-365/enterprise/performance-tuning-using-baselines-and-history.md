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
description: Informazioni su come controllare la cronologia delle connessioni dei computer client per individuare in anticipo i problemi emergenti.
ms.openlocfilehash: 2337b14542f894e9a62037b2f032632147e45e09
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691218"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Ottimizzazione delle prestazioni di Office 365 con le linee di base e la cronologia delle prestazioni

Esistono alcuni semplici modi per verificare le prestazioni della connessione tra Office 365 e l'azienda, che consentono di stabilire una linea di base approssimativa della connettività. Conoscere la cronologia delle prestazioni delle connessioni ai computer client consente di rilevare i problemi emergenti in anticipo, identificare e prevedere i problemi.
  
Se non si è abituati a lavorare su problemi di prestazioni, questo articolo è stato progettato per aiutare l'utente a prendere in considerazione alcune domande comuni, ad esempio come verificare se il problema che si verifica è un problema di prestazioni e non un incidente di servizio di Office 365? Come è possibile pianificare buone prestazioni a lungo termine? Come è possibile tenere sotto controllo le prestazioni? Se il team o i client vedono prestazioni lente durante l'uso di Office 365 e ci si chiede se si tratta di una di queste domande, leggere.
  
> [!IMPORTANT]
> **Si è verificato un problema di prestazioni tra il client e Office 365 in questo momento?** Seguire i passaggi descritti nel piano di risoluzione dei problemi [relativi alle prestazioni per Office 365.](performance-troubleshooting-plan.md) 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Informazioni da conoscere sulle prestazioni di Office 365

Office 365 si trova all'interno di una rete Microsoft dedicata ad alta capacità, costantemente monitorata non solo dall'automazione, ma anche da persone reali. Parte del ruolo della gestione del cloud di Office 365 è l'ottimizzazione delle prestazioni e la snellizione delle prestazioni laddove possibile. Poiché i client del cloud di Office 365 devono connettersi tramite Internet, esiste un impegno continuo per ottimizzare le prestazioni anche tra i servizi di Office 365. I miglioramenti delle prestazioni non si arrestano mai nel cloud e l'esperienza accumulata per mantenere il cloud integro e rapido. Se si verifica un problema di prestazioni durante la connessione dalla posizione a Office 365, è consigliabile non iniziare e attendere un caso di supporto. Al contrario, è consigliabile iniziare a analizzare il problema dall'interno all'esterno. In altri modi, iniziare all'interno della rete e accedere a Office 365. Prima di aprire un caso con il supporto di Office 365, è possibile raccogliere dati ed eseguire azioni che esploreranno e risolveranno il problema.
  
> [!IMPORTANT]
> Tenere presente la pianificazione della capacità e i limiti in Office 365. Queste informazioni ti permetteranno di anticipare la curva quando cerchi di risolvere un problema di prestazioni. Ecco un collegamento alle descrizioni dei servizi [di Microsoft 365 e Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library) Si tratta di un hub centrale e tutti i servizi offerti da Office 365 dispongono di un collegamento che consente di accedere alle proprie descrizioni dei servizi da qui. Ciò significa che, se è necessario visualizzare i limiti standard per SharePoint Online, ad esempio, fare clic su Descrizione servizio [SharePoint Online](https://technet.microsoft.com/library/sharepoint-online-service-description.aspx) e individuare la relativa sezione [Limiti di SharePoint Online.](https://go.microsoft.com/fwlink/p/?LinkID=856113) 
  
Assicurarsi di passare alla risoluzione dei problemi con la consapevolezza che le prestazioni sono una scala scorrevole, non si tratta di raggiungere un valore idealizzato e mantenerlo in modo permanente (se si ritiene che sia così, occasionalmente attività con larghezza di banda elevata come l'on-boarding di un numero elevato di utenti o l'esecuzione di migrazioni di dati di grandi dimensioni saranno molto stressanti, quindi pianificare l'impatto sulle prestazioni). Puoi e dovresti avere un'idea approssimativa dei target di prestazioni, ma molte variabili giocano sulle prestazioni, pertanto le prestazioni variano. Questa è la natura delle prestazioni. 
  
La risoluzione dei problemi relativi alle prestazioni non si tratta di raggiungere obiettivi specifici e di mantenere tali numeri a tempo indeterminato, ma di migliorare le attività esistenti, date tutte le variabili. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Ok, che aspetto ha un problema di prestazioni?

Prima di tutto, è necessario verificare che ciò che si sta verificando sia effettivamente un problema di prestazioni e non un incidente di servizio. Un problema di prestazioni è diverso da un incidente di servizio in Office 365. Ecco come distinguerli.
  
Se si verificano problemi con il servizio Office 365, si tratta di un incidente di servizio. Nell'interfaccia di amministrazione di Microsoft 365 verranno visualizzate icone rosse o gialle **in** Integrità corrente. È inoltre possibile notare un rallentamento delle prestazioni nei computer client che si connettono a Office 365. Ad esempio, se l'integrità corrente  segnala un'icona rossa e viene visualizzata l'analisi accanto a Exchange, è possibile che si ricevano anche alcune chiamate da parte di persone dell'organizzazione che si lamentano del fatto che le cassette postali client che utilizzano Exchange Online hanno prestazioni non migliori. In tal caso, è ragionevole presumere che le prestazioni di Exchange Online siano diventate una vittima di problemi all'interno del servizio. 
  
![Dashboard sull'integrità di Office 365 con tutti i carichi di lavoro in verde, ad eccezione di Exchange, che mostra Il servizio ripristinato.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
A questo punto, l'amministratore di Office 365 deve controllare l'integrità corrente e quindi visualizzare i dettagli e la **cronologia,** spesso, per mantenersi aggiornati sulle attività di manutenzione eseguite nel sistema.  Il **dashboard sull'integrità** corrente è stato creato per aggiornare l'utente in caso di modifiche e problemi nel servizio. Le note e le spiegazioni scritte nella cronologia dell'integrità, da amministratore ad amministratore, sono utili per valutare l'impatto e per mantenerti pubblicato sul lavoro in corso. 
  
![Immagine del dashboard sull'integrità di Office 365 che spiega che il servizio Exchange Online è stato ripristinato e perché.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Un problema di prestazioni non è un evento imprevisto del servizio, anche se gli incidenti possono causare un rallentamento delle prestazioni. Un problema di prestazioni è simile al seguente:
  
- Si verifica un problema di prestazioni indipendentemente da quale interfaccia di amministrazione **viene segnalata** l'integrità corrente per il servizio. 
    
-  Un comportamento che in un tempo era relativamente semplice richiede molto tempo per essere completato o non viene mai completato. 
    
- È anche possibile replicare il problema o, almeno, sapere che accadrà se si esegue la serie di passaggi giusta.
    
-  Se il problema è intermittente, esiste ancora un modello, ad esempio, si sa che entro le 10.00 si riceveranno chiamate da utenti che non possono accedere in modo affidabile a Office 365 e che le chiamate verranno perse verso le 12.00. 
    
Probabilmente sembra familiare; forse troppo familiare. Una volta che sai che si tratta di un problema di prestazioni, la domanda diventa "Cosa fare dopo?" Il resto di questo articolo consente di determinare esattamente questo.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Come definire e testare il problema di prestazioni

I problemi di prestazioni spesso emergono nel tempo, quindi può essere difficile definire il problema effettivo. È necessario creare una buona dichiarazione del problema e una buona idea del contesto del problema e quindi è necessario ripetere passaggi di test per ottenere risultati. In caso contrario, senza alcun errore, potresti perderti. Perché? Ecco alcuni esempi di istruzioni sui problemi che non forniscono informazioni sufficienti:
  
- Il passaggio dalla posta in arrivo al calendario era qualcosa che non notavo e ora è una pausa caffè. Puoi fare in modo che funzioni come prima?
    
- Il caricamento dei file in SharePoint Online sta prendendo sempre tempo. Perché è lento nel pomeriggi, ma in qualsiasi altro momento è veloce? Non può essere semplicemente veloce?
    
Le affermazioni del problema sopra poste in precedenza ponevano numerose sfide. In particolare, esistono molte ambiguità da gestire. Per esempio:
  
- Non è chiaro come il passaggio tra Posta in arrivo e Calendario abbia usato per agire sul portatile.
    
- Quando l'utente dice "Non può essere semplicemente veloce", che cos'è "veloce"?
    
- Quanto tempo è "per sempre"? Si tratta di alcuni secondi o minuti oppure l'utente potrebbe andare a pranzo e finirebbe dieci minuti dopo il ritorno dell'utente?
    
Tutto ciò è senza considerare che l'amministratore e lo strumento di risoluzione dei problemi non possono essere a conoscenza di molti dettagli da dichiarazioni di problemi come queste. Ad esempio, quando il problema ha iniziato a verificarsi; Che l'utente lavori da casa e vede solo il passaggio lento in una rete domestica; Che l'utente deve eseguire diverse altre applicazioni con utilizzo intensivo della RAM nel client locale oppure che l'utente esegue un sistema operativo precedente o non ha eseguito aggiornamenti recenti.
  
Quando gli utenti segnalano un problema di prestazioni, sono disponibili molte informazioni da raccogliere. La raccolta di queste informazioni fa parte di un processo denominato ambito del problema o analisi. Di seguito è riportato un elenco di ambito di base che è possibile utilizzare per raccogliere informazioni sul problema di prestazioni. Questo elenco non è esaustivo, ma è un punto in cui iniziare una delle seguenti attività: 
  
- In quale data si è verificato il problema e in quale ora del giorno o della notte?
    
- Che tipo di computer client si usava e come si connette alla rete aziendale (VPN, cablata, wireless)?
    
- Si lavorava in remoto o si era in ufficio?
    
- Hai provato le stesse azioni in un altro computer e hai visualizzato lo stesso comportamento?
    
- Illustra i passaggi che ti danno problemi in modo da poter scrivere le azioni da intraprendere.
    
- Quanto sono lente in secondi o minuti le prestazioni?
    
- Dove si trova il mondo?
    
Alcune di queste domande sono più ovvie di altre. La maggior parte di tutti capirà che uno strumento di risoluzione dei problemi richiede i passaggi esatti per riprodurre il problema. Dopo tutto, in che altro modo è possibile registrare il problema e in che altro modo è possibile verificare se il problema è stato risolto? Meno ovvie sono informazioni come "Quale data e ora hai visto il problema?", e "Dove ti trovi nel mondo?", informazioni che possono essere usate insieme. A seconda di quando l'utente stava lavorando, alcune ore di differenza di tempo potrebbero indicare che la manutenzione è già in corso su parti della rete aziendale. Se, ad esempio, l'azienda dispone di un'implementazione ibrida, come una ricerca ibrida di SharePoint, che può eseguire query sugli indici di ricerca sia in SharePoint Online che in un'istanza di SharePoint Server 2013 locale, gli aggiornamenti potrebbero essere in corso nella farm locale. Se l'azienda è tutto nel cloud, la manutenzione del sistema può includere l'aggiunta o la rimozione di hardware di rete, l'implementazione di aggiornamenti a livello aziendale o l'esecuzione di modifiche al DNS o a un'altra infrastruttura di base.
  
Quando si sta cercando di risolvere un problema di prestazioni, è un po' come una scena del delitto, è necessario essere precisi e osservanti per trarre conclusioni dalle prove. A tale scopo, è necessario ottenere una buona dichiarazione del problema raccogliendo le prove. Deve includere il contesto del computer, il contesto dell'utente, l'inizio del problema e i passaggi esatti che hanno esposto il problema di prestazioni. Questa dichiarazione del problema deve essere e rimanere la pagina più in alto nelle note. Tornando all'istruzione del problema dopo aver risolto il problema, è necessario eseguire i passaggi per verificare e dimostrare se le azioni intraprese hanno risolto il problema. Questo è fondamentale per sapere quando viene svolto il tuo lavoro.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Si conosce l'aspetto delle prestazioni quando le prestazioni sono buone?

Se non sei un'inforcabile, nessuno lo sa. Nessuno aveva numeri. Ciò significa che nessuno può rispondere alla semplice domanda "Quanti secondi sono stati utilizzati per visualizzare una cartella Posta in arrivo in Office 365?" o "Quanto tempo è stato necessario quando i dirigenti hanno avuto una riunione in Lync Online?", che è uno scenario comune per molte aziende.
  
Ciò che manca qui è una linea di base per le prestazioni.
  
Le linee di base forniscono un contesto per le prestazioni. È consigliabile prendere spesso una linea di base, a seconda delle esigenze dell'azienda. Se si è un'azienda di grandi dimensioni, il team operativo potrebbe già prendere le linee di base per l'ambiente locale. Ad esempio, se si esegue la patch di tutti i server Exchange il primo lunedì del mese e di tutti i server di SharePoint il terzo lunedì, è probabile che il team operativo abbia un elenco di attività e scenari eseguiti dopo l'applicazione di patch, per dimostrare che le funzioni critiche sono operative. Ad esempio, aprendo la cartella Posta in arrivo, facendo clic su Invia/Ricevi e verificando l'aggiornamento delle cartelle oppure, in SharePoint, esplorando la pagina principale del sito, andando nella pagina Ricerca organizzazione ed eseguendo una ricerca che restituisca risultati.
  
Se le applicazioni si trova in Office 365, alcune delle linee di base più fondamentali possono essere misurate in millisecondi da un computer client all'interno della rete, da un punto di uscita o dal punto in cui si esce dalla rete e si esce da Office 365. Ecco alcune linee di base utili che è possibile analizzare e registrare:
  
- Identificare i dispositivi tra il computer client e il punto di uscita, ad esempio il server proxy.
    
  - Devi conoscere i dispositivi in modo da avere il contesto (indirizzi IP, tipo di dispositivo, ecc.) per i problemi di prestazioni che si verificano.
    
  - I server proxy sono punti di uscita comuni, quindi puoi controllare il web browser per vedere quale server proxy è impostato per l'uso, se presente.
    
  - Esistono strumenti di terze parti in grado di individuare e mappare la rete, ma il modo più sicuro per conoscere i dispositivi è chiedere a un membro del team di rete.
    
- Identificare il provider di servizi Internet (ISP), annotarne le informazioni di contatto e chiedere al numero di circuiti la larghezza di banda disponibile.
    
- All'interno dell'azienda, identificare le risorse per i dispositivi tra il client e il punto di uscita oppure identificare un contatto di emergenza con cui parlare di problemi di rete.
    
Ecco alcune linee di base che possono essere calcolate automaticamente da semplici test con strumenti:
  
- Tempo dal computer client al punto di uscita in millisecondi
    
- Tempo dal punto di uscita a Office 365 in millisecondi
    
- Posizione nel mondo del server che risolve gli URL per Office 365 quando si sfoglia
    
- Velocità della risoluzione DNS dell'ISP in millisecondi, incoerenze nell'arrivo dei pacchetti (instabilità di rete), tempi di caricamento e download in millisecondi
    
Se non si ha familiarità con la procedura, verranno fornite informazioni più dettagliate in questo articolo. 
  
## <a name="what-is-a-baseline"></a>Che cos'è una linea di base?

Si conoscerà l'impatto quando si verificano problemi, ma se non si conoscono i dati cronologici sulle prestazioni, non è possibile avere un contesto per quanto male potrebbe essere diventato e quando. Quindi, senza una linea di base, ti manca l'indicazione chiave per risolvere il puzzle: l'immagine nella casella del puzzle. Per la risoluzione dei problemi relativi alle prestazioni, è necessario un punto di *confronto.* Le semplici linee di base delle prestazioni non sono difficili da prendere. Il team operativo può avere il compito di eseguire queste operazioni in base a una pianificazione. Si supponga, ad esempio, che la connessione sia simile alla seguente: 
  
![Un grafico di rete di base che mostra client, proxy e cloud di Office 365.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Ciò significa che hai controllato con il team di rete e hai scoperto che lasci la tua azienda per Internet tramite un server proxy e che il proxy gestisce tutte le richieste inviate dal computer client al cloud. In questo caso, devi disegnare una versione semplificata della connessione in cui sono elencati tutti i dispositivi che intervengono. A questo punto, inserire gli strumenti che è possibile utilizzare per testare le prestazioni tra il client, il punto di uscita (dove si lascia la rete per Internet) e il cloud di Office 365.
  
![Rete di base con client, proxy e cloud e suggerimenti per gli strumenti PSPing, TraceTCP e tracce di rete.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
Le opzioni sono elencate **come Semplici** **e** Avanzate a causa della quantità di competenze necessarie per trovare i dati sulle prestazioni. Una traccia di rete richiederà molto tempo, rispetto all'esecuzione di strumenti da riga di comando come PsPing e TraceTCP. Questi due strumenti della riga di comando sono stati scelti perché non utilizzano pacchetti ICMP, che verranno bloccati da Office 365, e perché forniscono il tempo in millisecondi necessario per lasciare il computer client o il server proxy (se si dispone dell'accesso) e arrivare a Office 365. Ogni singolo passaggio da un computer a un altro finirà con un valore di tempo ed è ideale per le linee di base. Come importante, questi strumenti della riga di comando consentono di aggiungere un numero di porta al comando, ciò è utile perché Office 365 comunica sulla porta 443, ovvero la porta utilizzata da Secure Sockets Layer e Transport Layer Security (SSL e TLS). Tuttavia, altri strumenti di terze parti potrebbero essere soluzioni migliori per la propria situazione. Microsoft non supporta tutti questi strumenti, quindi se, per qualche motivo, non è possibile far funzionare PsPing e TraceTCP, passare a una traccia di rete con uno strumento come Netmon. 
  
È possibile prendere una previsione prima dell'orario di ufficio, di nuovo durante un utilizzo intenso e quindi di nuovo dopo l'orario di ufficio. Questo significa che potresti avere una struttura di cartelle un po' simile alla seguente alla fine:
  
![Grafica che propone una soluzione per organizzare i dati delle prestazioni in cartelle.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
È inoltre consigliabile selezionare una convenzione di denominazione per i file. Ecco alcuni esempi:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
Esistono molti modi diversi per eseguire questa operazione, ma l'uso del formato **\<dateTime\>\<what's happening in the test\>** è un buon punto di partenza. La diligenza su questo argomento è molto utile quando si tenta di risolvere i problemi in un secondo momento. In seguito, sarà possibile dire "L'8 febbraio ho preso due tracce, una ha mostrato buone prestazioni e una ha mostrato risultati non ottimali, quindi possiamo confrontarle". Ciò è estremamente utile per la risoluzione dei problemi. 
  
È necessario disporre di un modo organizzato per mantenere le baseline cronologiche. In questo esempio, i semplici metodi generavano tre output della riga di comando e i risultati sono stati raccolti come screenshot, ma potresti avere invece file di acquisizione di rete. Usa il metodo più adatto per te. Archiviare le baseline cronologiche e fare riferimento a tali elementi nei punti in cui si notano cambiamenti nel comportamento dei servizi online. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Perché raccogliere dati sulle prestazioni durante un progetto pilota?

Non c'è tempo migliore per iniziare a creare linee di base rispetto a una distribuzione pilota del servizio Office 365. L'ufficio può avere migliaia di utenti, centinaia di migliaia o cinque, ma anche con un numero limitato di utenti, è possibile eseguire test per misurare le fluttuazioni delle prestazioni. Nel caso di una società di grandi dimensioni, un campione rappresentativo di diverse centinaia di utenti che hanno pilotato Office 365 può essere proiettato verso l'esterno a diverse migliaia, in modo da sapere dove potrebbero verificarsi i problemi prima che si verificano.
  
Nel caso di una piccola azienda, in cui l'on-boarding significa che tutti gli utenti passano al servizio contemporaneamente e non è disponibile alcuna soluzione pilota, mantenere le misure delle prestazioni in modo da disporre di dati da mostrare a chiunque possa avere la richiesta di risolvere i problemi di un'operazione con prestazioni non ottimali. Ad esempio, se si nota che all'improvviso è possibile spostarsi all'interno dell'edificio nel tempo necessario per caricare un elemento grafico di medie dimensioni in cui si verificava molto rapidamente.
  
## <a name="how-to-collect-baselines"></a>Come raccogliere le linee di base

Per tutti i piani di risoluzione dei problemi, è necessario identificare almeno questi elementi:
  
- Il computer client in uso (il tipo di computer o dispositivo, un indirizzo IP e le azioni che hanno causato il problema)
    
- Posizione in cui si trova il computer client nel mondo (ad esempio, se l'utente si trova in una rete VPN, lavora in remoto o nella rete Intranet aziendale)
    
- Il punto di uscita utilizzato dal computer client dalla rete (il punto in cui il traffico lascia l'azienda per un ISP o Internet)
    
 È possibile trovare il layout della rete dall'amministratore di rete. Se si è in una rete di piccole dimensioni, esaminare i dispositivi che si connettono a Internet e chiamare l'ISP in caso di domande sul layout. Crea un elemento grafico del layout finale per il riferimento. 
  
Questa sezione è suddivisa in semplici strumenti e metodi della riga di comando e opzioni degli strumenti più avanzate. Verranno descritti prima i metodi semplici. Tuttavia, se al momento si verifica un problema di prestazioni, è consigliabile passare a metodi avanzati e provare il piano di azione per la risoluzione dei problemi di prestazioni di esempio.
  
### <a name="simple-methods"></a>Metodi semplici

L'obiettivo di questi semplici metodi è quello di imparare a prendere, comprendere e archiviare correttamente semplici baseline delle prestazioni nel tempo in modo da essere informati sulle prestazioni di Office 365. Ecco il diagramma molto semplice per semplici, come hai visto prima:
  
![Rete di base con client, proxy e cloud e suggerimenti per gli strumenti PSPing, TraceTCP e tracce di rete.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP è incluso in questa cattura di schermata perché è uno strumento utile per visualizzare, in millisecondi, il tempo necessario per elaborare una richiesta e il numero di hop di rete o connessioni da un computer all'altro, che la richiesta richiede per raggiungere una destinazione. TraceTCP può anche fornire i nomi dei server utilizzati durante gli hop, che possono essere utili per uno strumento di risoluzione dei problemi di Microsoft Office 365 nel supporto. > comandi TraceTCP possono essere molto semplici, ad esempio: >> ricordarsi di includere il numero di porta  `tracetcp.exe outlook.office365.com:443` nel comando. > [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) è un download gratuito, ma si basa su Wincap. Wincap è uno strumento utilizzato e installato anche da Netmon. Usiamo anche Netmon nella sezione dei metodi avanzati. 
  
 Se si dispone di più uffici, sarà necessario conservare un set di dati da un client anche in ognuna di queste posizioni. Questo test misura la latenza, che, in questo caso, è un valore numerico che descrive la quantità di tempo tra un client che invia una richiesta a Office 365 e Office 365 che risponde alla richiesta. Il test ha origine all'interno del dominio in un computer client e cerca di misurare un round trip dall'interno della rete, da un punto di uscita, da Internet a Office 365 e così via. 
  
Esistono alcuni modi per gestire il punto di uscita, in questo caso il server proxy. Puoi tracciare da 1 a 2 e quindi da 2 a 3 e quindi aggiungere i numeri in millisecondi per ottenere un totale finale al perimetro della rete. In caso contrario, è possibile configurare la connessione per ignorare il proxy per gli indirizzi di Office 365. In una rete più grande con un firewall, un proxy inverso o una combinazione di queste due, potrebbe essere necessario creare eccezioni nel server proxy che consentiranno il passaggio del traffico per molti URL. Per l'elenco degli endpoint usati da Office 365, vedere URL e intervalli di indirizzi [IP di Office 365.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) Se si dispone di un proxy di autenticazione, iniziare verificando le eccezioni per gli elementi seguenti:
  
- Porte 80 e 443
    
- TCP e HTTP
    
- Connessioni in uscita verso uno qualsiasi di questi URL:
    
- \*.microsoftonline.com
    
- \*.microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*.outlook.com
    
- \*.lync.com
    
- osub.microsoft.com
    
A tutti gli utenti deve essere consentito accedere a questi indirizzi senza alcuna interferenza proxy o autenticazione. In una rete più piccola, devi aggiungerli all'elenco di bypass proxy nel web browser. 
  
Per aggiungerli all'elenco di bypass proxy in Internet Explorer, passare **a** Strumenti \> **Opzioni Internet** \> **Connessioni** \> **LAN impostazioni** \> **avanzate.** La scheda avanzata è anche dove troverai il server proxy e la porta del server proxy. Potrebbe essere necessario fare clic sulla casella di controllo Usa un server proxy per la **rete LAN** per accedere al **pulsante** Avanzate. È necessario verificare che sia selezionata l'opzione **Ignora server proxy** per gli indirizzi locali. Dopo aver fatto **clic su Avanzate,** verrà visualizzata una casella di testo in cui è possibile immettere le eccezioni. Separare gli URL con caratteri jolly elencati in precedenza con un punto e virgola, ad esempio:
  
\*.microsoftonline.com; \*.sharepoint.com
  
Dopo aver ignorato il proxy, dovrebbe essere possibile usare il ping o PsPing direttamente su un URL di Office 365. Il passaggio successivo consisterà nel testare il ping **outlook.office365.com**. In caso contrario, se si usa PsPing o un altro strumento che consente di specificare un numero di porta per il comando, PsPing su **portal.microsoftonline.com:443** per visualizzare il tempo medio di round trip in millisecondi. 
  
Il tempo di andata e ritorno, o RTT, è un valore numerico che misura il tempo necessario per inviare una richiesta HTTP a un server come outlook.office365.com e ottenere una risposta che riconosca che il server è a conoscenza dell'operazione. A volte questa opzione è abbreviata come RTT. Dovrebbe trattarsi di un periodo di tempo relativamente breve.
  
Per eseguire questo test, è necessario utilizzare [PSPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) o un altro strumento che non utilizza pacchetti ICMP bloccati da Office 365. 
  
 **Come usare PsPing per ottenere un tempo di andata e ritorno complessivo in millisecondi direttamente da un URL di Office 365**
  
1. Eseguire un prompt dei comandi con privilegi elevati completando la procedura seguente:
    
1. Fare clic su **Avvia**.
    
2. Nella casella **Inizia ricerca** digitare cmd e quindi premere CTRL+MAIUSC+INVIO.
    
3. Se viene visualizzata la finestra di dialogo **Controllo account utente**, confermare che l'azione visualizzata è quella desiderata e scegliere **Continua**.
    
2. Passare alla cartella in cui è installato lo strumento (in questo caso PsPing) e testare questi URL di Office 365:
    
  - psping portal.office.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![Il comando PSPing che sta per microsoft-my.sharepoint.com porta 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Assicurarsi di includere il numero di porta 443. Tenere presente che Office 365 funziona su un canale crittografato. Se psPing senza il numero di porta, la richiesta avrà esito negativo. Dopo aver evaso il ping dell'elenco breve, cercare il tempo medio in millisecondi (ms). Questo è ciò che si desidera registrare.
  
![Immagine che mostra un'illustrazione di PSPing da client a proxy con un tempo di round trip di 2,8 millisecondi.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Se non hai familiarità con il bypass proxy e preferisci eseguire operazioni dettagliate, devi prima trovare il nome del server proxy. In Internet Explorer passare a **Strumenti** \> **Opzioni Internet** \> **Connessioni** \> **IMPOSTAZIONI LAN** \> **Avanzate.** Nella **scheda Avanzate** viene visualizzato il server proxy elencato. Eseguire il ping del server proxy al prompt dei comandi completando questa attività: 
  
 **Per eseguire il ping del server proxy e ottenere un valore di round trip in millisecondi per la fase 1-2**
  
1. Eseguire un prompt dei comandi con privilegi elevati completando la procedura seguente:
    
1. Fare clic su **Avvia**.
    
2. Nella casella **Inizia ricerca** digitare cmd e quindi premere CTRL+MAIUSC+INVIO.
    
3. Se viene visualizzata la finestra di dialogo **Controllo account utente**, confermare che l'azione visualizzata è quella desiderata e scegliere **Continua**.
    
2. Digitare ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> e quindi premere INVIO. Se hai installato PsPing o un altro strumento, puoi scegliere di usare lo strumento. 
    
    Il comando può essere simile a uno di questi esempi: 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping ourproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy:80
    
3. Quando la traccia smette di inviare pacchetti di test, si otterrà un piccolo riepilogo che elenca una media, in millisecondi, e questo è il valore che si desidera ottenere. Fai una cattura di schermata del prompt e salvala usando la convenzione di denominazione. A questo punto può essere utile anche compilare il diagramma con il valore.
    
Forse è stata tracciata la mattina presto e il client può accedere rapidamente al proxy (o a qualsiasi altro server in uscita da Internet). In questo caso, i numeri potrebbero essere simili al seguente:
  
![Immagine che mostra il tempo di andata e ritorno da un client a un proxy di 2,8 millisecondi.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Se il computer client è uno dei pochi selezionati con accesso al server proxy (o in uscita), è possibile eseguire la fase successiva del test connettendosi in remoto a tale computer, eseguendo il prompt dei comandi per PsPing a un URL di Office 365 da qui. Se non si ha accesso a tale computer, è possibile contattare le risorse di rete per assistenza con la prossima fase e ottenere numeri esatti in questo modo. Se non è possibile, eseguire un psping sull'URL di Office 365 in questione e confrontarlo con il tempo PsPing o Ping rispetto al server proxy. 
  
Ad esempio, se si hanno 51,84 millisecondi dal client all'URL di Office 365 e si hanno 2,8 millisecondi dal client al proxy (o punto di uscita), si hanno 49,04 millisecondi dall'uscita a Office 365. Analogamente, se si dispone di un psPing di 12,25 millisecondi dal client al proxy durante l'altezza del giorno e di 62,01 millisecondi dal client all'URL di Office 365, il valore medio per l'uscita del proxy all'URL di Office 365 è 49,76 millisecondi.
  
![Grafico aggiuntivo che mostra il ping in millisecondi dal client al proxy accanto al client a Office 365 in modo che i valori possano essere sottratti.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
Per quanto riguarda la risoluzione dei problemi, potresti trovare qualcosa di interessante solo nel mantenere queste linee di base. Ad esempio, Se in genere si hanno da 40 a 59 millisecondi di latenza dal proxy o dal punto di uscita all'URL di Office 365 e si dispone di un client per eseguire il proxy o la latenza del punto di uscita di circa 3-7 millisecondi (a seconda della quantità di traffico di rete che si sta visualizzando durante l'ora del giorno), si saprà sicuramente che qualcosa è problematico se gli ultimi tre client per eseguire il proxy o l'uscita dalle linee di base mostrano una latenza di 45 millisecondi.
  
### <a name="advanced-methods"></a>Metodi avanzati

Se si vuole sapere cosa accade con le richieste Internet a Office 365, è necessario acquisire familiarità con le tracce di rete. Non importa quali strumenti preferisci per queste tracce, HTTPWatch, Netmon, Message Analyzer, Wireshark, Fiddler, Developer Dashboard tool o qualsiasi altro strumento farà tutto il tempo che lo strumento può acquisire e filtrare il traffico di rete. You'll see in this section that it's beneficial to run more than one of these tools to get a more complete picture of the problem. Durante i test, alcuni di questi strumenti fungono anche da proxy in proprio diritto. Gli strumenti utilizzati nell'articolo complementare, Piano di risoluzione dei problemi relativi alle prestazioni per [Office 365,](performance-troubleshooting-plan.md)includono [Netmon 3.4,](https://www.microsoft.com/download/details.aspx?id=4865) [HTTPWatch](https://www.httpwatch.com/download/)o [WireShark.](https://www.wireshark.org/)
  
L'esecuzione di una previsione delle prestazioni è la parte semplice di questo metodo e molti dei passaggi sono gli stessi di quando si risolve un problema di prestazioni. I metodi più avanzati per la creazione di linee di base per le prestazioni richiedono l'utilizzo e l'archiviazione delle tracce di rete. La maggior parte degli esempi in questo articolo usa SharePoint Online, ma è consigliabile sviluppare un elenco di azioni comuni tra i servizi di Office 365 a cui si sottoscrive il test e la registrazione. Ecco un esempio di base:
  
- Elenco di base per SpO - ** Passaggio 1: ** Esplorare la home page del sito Web di SpO ed eseguire una traccia di rete. Salvare la traccia. 
    
- Elenco di base per SpO - **Passaggio 2:** cercare un termine ,ad esempio il nome della società, tramite Ricerca contenuti organizzazione ed eseguire una traccia di rete. Salvare la traccia. 
    
- Elenco di base per SharePoint Online - **Passaggio 3:** Caricare un file di grandi dimensioni in una raccolta documenti di SharePoint Online ed eseguire una traccia di rete. Salvare la traccia. 
    
- Elenco di base per SpO - **Passaggio 4:** Esplorare la home page del sito Web di OneDrive ed eseguire una traccia di rete. Salvare la traccia. 
    
Questo elenco deve includere le azioni comuni più importanti eseguite dagli utenti in SharePoint Online. Si noti che l'ultimo passaggio, per tenere traccia di OneDrive for Business, crea un confronto tra il carico della home page di SharePoint Online (spesso personalizzata dalle aziende) e la home page di OneDrive for Business, raramente personalizzata. Si tratta di un test molto semplice quando si tratta di un sito di SharePoint Online con caricamento lento. È possibile creare un record di questa differenza nei test.
  
Se ci si sta occupando di un problema di prestazioni, molti dei passaggi sono gli stessi di quando si prende una linea di base. Le tracce di rete diventano fondamentali, quindi  *gestiremo*  come prendere le tracce importanti successivamente. 
  
Per risolvere un problema di  *prestazioni,*  al momento è necessario prendere una traccia nel momento in cui si verifica il problema di prestazioni. È necessario disporre degli strumenti adeguati per raccogliere i registri ed è necessario un piano d'azione, cio? un elenco di azioni per la risoluzione dei problemi da eseguire per raccogliere le informazioni migliori che è possibile eseguire. La prima operazione da eseguire è registrare la data e l'ora del test in modo che i file possano essere salvati in una cartella che rifletta l'intervallo di tempo. Successivamente, restringersi ai passaggi del problema. Questi sono i passaggi esatti che userai per i test. Non dimenticare le nozioni di base: se il problema riguarda solo Outlook, assicurarsi di registrare che il comportamento del problema si verifica in un solo servizio di Office 365. Restringere l'ambito di questo problema ti aiuterà a concentrarti su qualcosa che puoi risolvere. 
  
## <a name="see-also"></a>Vedere anche

[Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

