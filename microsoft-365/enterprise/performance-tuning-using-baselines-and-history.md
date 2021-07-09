---
title: Ottimizzazione delle prestazioni di Office 365 con le linee di base e la cronologia delle prestazioni
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 07/08/2021
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
description: Informazioni su come controllare la cronologia delle connessioni dei computer client per rilevare i problemi emergenti in anticipo.
ms.openlocfilehash: 460bde30a0b292569b045c339066df2860c50989
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341581"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Ottimizzazione delle prestazioni di Office 365 con le linee di base e la cronologia delle prestazioni

Esistono alcuni semplici modi per controllare le prestazioni di connessione tra Office 365 e l'azienda che consentono di stabilire una linea di base approssimativa della connettività. Conoscere la cronologia delle prestazioni delle connessioni dei computer client può aiutare a rilevare i problemi emergenti in anticipo, identificare e prevedere i problemi.
  
Se non sei abituato a lavorare su problemi di prestazioni, questo articolo è progettato per aiutarti a prendere in considerazione alcune domande comuni. Come si fa a sapere che il problema che si sta verificando è un problema di prestazioni e non un Office 365 di servizio? Come è possibile pianificare buone prestazioni a lungo termine? Come si può tenere d'occhio le prestazioni? Se il team o i client vedono prestazioni lente durante l'Office 365 e ti chiedi una di queste domande, continua a leggere.
  
> [!IMPORTANT]
> **Si è verificato un problema di prestazioni tra il client e Office 365 in questo momento?** Seguire i passaggi descritti nel piano di risoluzione dei problemi di prestazioni [per Office 365](performance-troubleshooting-plan.md). 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Informazioni da conoscere sulle prestazioni Office 365 prestazioni

Office 365 si trova all'interno di una rete Microsoft dedicata ad alta capacità monitorata dall'automazione e da persone reali. Parte della manutenzione del Office 365 cloud è l'ottimizzazione delle prestazioni e la snellizione, ove possibile. Dal momento che i client del cloud Office 365 devono connettersi attraverso Internet, c'è un impegno costante per ottimizzare le prestazioni anche Office 365 servizi.

I miglioramenti delle prestazioni non si arrestano mai realmente nel cloud, quindi nemmeno l'esperienza di mantenere il cloud integro e rapido. In caso di problemi di prestazioni che si connettono dalla posizione a Office 365, è consigliabile non iniziare o attendere un caso di supporto. È invece consigliabile iniziare a analizzare il problema dall'interno all'esterno. In altri modi, iniziare all'interno della rete e lavorare per Office 365. Prima di aprire un caso con il supporto, è possibile raccogliere dati ed eseguire azioni che esploreranno e risolveranno il problema.
  
> [!IMPORTANT]
> Tenere presente la pianificazione della capacità e i limiti in Office 365. Queste informazioni ti metteranno in testa alla curva quando cerchi di risolvere un problema di prestazioni. Ecco un collegamento alle descrizioni dei [Microsoft 365 e Office 365 servizio.](/office365/servicedescriptions/office-365-service-descriptions-technet-library) Si tratta di un hub centrale e tutti i servizi offerti da Office 365 hanno un collegamento che consente di accedere alle proprie descrizioni dei servizi da qui. Ciò significa che, se è necessario visualizzare i limiti standard per SharePoint Online, ad esempio, fare clic su [SharePoint Online Service Description](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description) e individuare la relativa sezione SharePoint Online [Limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits).
  
Assicurati di passare alla risoluzione dei problemi con la comprensione che le prestazioni sono una scala scorrevole. Non si tratta di ottenere un valore idealizzato e mantenerlo in modo permanente. Attività occasionali con larghezza di banda elevata, come l'on-boarding di un  numero elevato di utenti o l'esecuzione di migrazioni di dati di grandi dimensioni, saranno stressanti, quindi pianificare l'impatto sulle prestazioni. Dovresti avere un'idea approssimativa dei tuoi obiettivi di prestazioni, ma molte variabili giocano sulle prestazioni, quindi le prestazioni variano.
  
La risoluzione dei problemi di prestazioni non riguarda il rispetto di obiettivi specifici e il mantenimento di tali numeri a tempo indeterminato, ma il miglioramento delle attività esistenti, date tutte le variabili. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Ok, qual è l'aspetto di un problema di prestazioni?

Prima di tutto, è necessario assicurarsi che ciò che si sta verificando sia effettivamente un problema di prestazioni e non un evento imprevisto del servizio. Un problema di prestazioni è diverso da un evento imprevisto del servizio in Office 365. Ecco come distinguerli.
  
Gli incidenti di servizio si verificano Office 365 problemi del servizio stesso. Potresti visualizzare icone rosse o gialle in **Integrità corrente** nella interfaccia di amministrazione di Microsoft 365. È possibile notare che le prestazioni nei computer client che si connettono a Office 365 sono lente. Ad esempio, se l'integrità corrente  segnala un'icona rossa e viene visualizzata l'opzione Analisi accanto a Exchange, è possibile ricevere anche chiamate da persone dell'organizzazione che si lamentano che le cassette postali client che usano Exchange Online sono lente. In tal caso, è ragionevole presupporre che le prestazioni Exchange Online siano una vittima di problemi del servizio.
  
![Il dashboard Office 365 integrità con tutti i carichi di lavoro in verde, ad Exchange, che mostra Servizio ripristinato.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
A questo punto, l'amministratore di Office 365  deve controllare Integrità corrente e quindi Visualizzare i dettagli e la **cronologia,** spesso, per mantenersi aggiornati sulla manutenzione del sistema. Il **dashboard di** integrità corrente è stato creato per aggiornare l'utente sulle modifiche e sui problemi del servizio. Le note e le spiegazioni scritte nella cronologia dell'integrità, dall'amministratore all'amministratore, sono utili per valutare e mantenere i dati pubblicati sul lavoro in corso.
  
![Un'immagine del dashboard Office 365 integrità dei dati che spiega che il servizio di Exchange Online è stato ripristinato e perché.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Un problema di prestazioni non è un evento imprevisto del servizio, anche se gli eventi imprevisti possono causare prestazioni lente. Un problema di prestazioni è simile al seguente:
  
- Si verifica un problema di prestazioni indipendentemente dall'integrità corrente dell'interfaccia **di** amministrazione per il servizio.
    
-  Un comportamento utilizzato per il flusso richiede molto tempo per essere completato o non viene mai completato.
    
- È anche possibile replicare il problema o sapere che si verifica se si esegue la serie di passaggi giusta.
    
-  Se il problema è intermittente, può essere ancora presente un modello. Ad esempio, si sa che entro le 10:00 saranno effettuate chiamate da utenti che non sempre possono accedere a Office 365. Le chiamate termineranno intorno a mezzogiorno.
    
Questo elenco probabilmente sembra familiare; forse troppo familiare. Una volta che si è a conoscenza che si tratta di un problema di prestazioni, la domanda diventa" "Cosa fare?" Il resto di questo articolo ti aiuta a determinare esattamente questo.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Come definire e testare il problema di prestazioni

I problemi di prestazioni spesso si verificano nel tempo, quindi può essere difficile definire il problema effettivo. Creare una buona dichiarazione di problema con una buona idea del contesto del problema e quindi è necessario ripetere i passaggi di test. Ecco alcuni esempi di istruzioni sui problemi che non forniscono informazioni sufficienti:
  
- Il passaggio dalla posta in arrivo al calendario era qualcosa che non notavo e ora è una pausa caffè. Puoi farlo agire come prima?
    
- Il caricamento dei file in SharePoint Online sta prendendo sempre tempo. Perché è lento nel pomeriggio, ma in qualsiasi altro momento è veloce? Non può essere semplicemente veloce?
    
Le affermazioni sul problema sopra poste in precedenza inserivano numerose sfide. In particolare, troppe ambiguità da gestire. Per esempio:
  
- Non è chiaro come il passaggio tra Posta in arrivo e Calendario abbia usato per agire sul portatile.
    
- Quando l'utente dice: "Non può essere semplicemente veloce", che cos'è "veloce"?
    
- Quanto tempo è "per sempre"? Sono trascorsi alcuni secondi? O molti minuti? Oppure l'utente potrebbe pranzare e l'azione finirebbe 10 minuti dopo il ritorno?
    
L'amministratore e lo strumento di  risoluzione dei problemi non possono essere a conoscenza dei dettagli del problema da istruzioni generali come queste. Ad esempio, non sanno quando il problema ha iniziato a verificarsi. Lo strumento di risoluzione dei problemi potrebbe non sapere se l'utente lavora da casa e vede solo un cambio lento mentre si è in rete. Oppure che l'utente esegue altre applicazioni con utilizzo intensivo della RAM nel client locale. Gli amministratori potrebbero non sapere se l'utente esegue un sistema operativo precedente o non ha eseguito aggiornamenti recenti.
  
Quando gli utenti segnalano un problema di prestazioni, sono disponibili molte informazioni da raccogliere. Per ottenere e registrare le informazioni si intitoli l'ambito del problema. Ecco un elenco di ambito di base che puoi usare per raccogliere informazioni sui problemi di prestazioni. Questo elenco non è esaustivo, ma è un punto di partenza:
  
- In quale data si è verificato il problema e a quale ora del giorno o della notte?
    
- Che tipo di computer client si usava e come si connette alla rete aziendale (VPN, cablata, wireless)?
    
- Si lavorava in remoto o si era in ufficio?
    
- Hai provato le stesse azioni in un altro computer e hai visto lo stesso comportamento?
    
- Illustrare i passaggi che stanno dando il problema in modo da poter scrivere le azioni da intraprendere.
    
- Quanto sono lente in secondi o minuti le prestazioni?
    
- Dove si trova il mondo?
    
Alcune di queste domande sono più ovvie di altre. La maggior parte di tutti capirà che uno strumento di risoluzione dei problemi richiede la procedura esatta per riprodurre il problema. Dopo tutto, in che altro modo è possibile registrare il problema e in che altro modo è possibile verificare se il problema è stato risolto? Meno ovvie sono le informazioni quali "Data e ora in cui è stato visualizzato il problema?" e "Dove si trova il mondo?", informazioni che possono essere utilizzate in tandem. A seconda di quando l'utente stava lavorando, alcune ore di differenza di tempo possono indicare che la manutenzione è già in corso su parti della rete aziendale. Se, ad esempio, l'azienda ha un'implementazione ibrida, come una ricerca SharePoint ibrida, che può eseguire query sugli indici di ricerca sia in SharePoint Online che in un'istanza di SharePoint Server 2013 locale, gli aggiornamenti potrebbero essere in corso nella farm locale. Se l'azienda è tutto nel cloud, la manutenzione del sistema può includere l'aggiunta o la rimozione di hardware di rete, la distribuzione di aggiornamenti a livello aziendale o l'apportare modifiche al DNS o a un'altra infrastruttura di base.
  
Quando si sta cercando di risolvere un problema di prestazioni, è un po' come una scena del delitto, è necessario essere precisi e osservanti per trarre conclusioni dalle prove. A tale scopo, è necessario ottenere una buona dichiarazione di problema raccogliendo prove. Deve includere il contesto del computer, il contesto dell'utente, l'inizio del problema e i passaggi esatti che hanno esposto il problema di prestazioni. Questa dichiarazione del problema deve essere e rimanere la pagina più in alto nelle note. Tornando all'istruzione del problema dopo aver utilizzato la risoluzione, è necessario eseguire i passaggi per verificare e dimostrare se le azioni intraprese hanno risolto il problema. Questo è fondamentale per sapere quando viene fatto il tuo lavoro.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Sai qual è l'aspetto delle prestazioni quando era buona?

Se sei sfortunato, nessuno lo sa. Nessuno aveva numeri. Ciò significa che nessuno può rispondere alla semplice domanda "Quanti secondi sono stati utilizzati per visualizzare una posta in arrivo in Office 365?", o "Quanto tempo è stato necessario quando i dirigenti hanno avuto una riunione di Lync Online?", uno scenario comune per molte società.
  
Ciò che manca qui è una previsione delle prestazioni.
  
Le linee di base forniscono un contesto per le prestazioni. È consigliabile prendere spesso una linea di base, a seconda delle esigenze dell'azienda. Se si è un'azienda di grandi dimensioni, il team operativo potrebbe già prendere le linee di base per l'ambiente locale. Ad esempio, se si patchno tutti i server Exchange il primo lunedì del mese e tutti i server SharePoint il terzo lunedì, il team operativo probabilmente dispone di un elenco di attività e scenari che viene eseguito dopo l'applicazione di patch, per dimostrare che le funzioni critiche sono operative. Ad esempio, aprire la cartella Posta in arrivo, fare clic su Invia/Ricevi e verificare che le cartelle siano aggiornate oppure, in SharePoint, esplorare la pagina principale del sito, andare nella pagina Ricerca organizzazione ed eseguire una ricerca che restituisca risultati.
  
Se le applicazioni sono in Office 365, alcune delle linee di base più fondamentali possono essere misurate in millisecondi da un computer client all'interno della rete, da un punto di uscita o dal punto in cui si esce dalla rete e si esce da Office 365. Ecco alcune utili linee di base che è possibile analizzare e registrare:
  
- Identificare i dispositivi tra il computer client e il punto di uscita, ad esempio il server proxy.
    
  - Devi conoscere i dispositivi in modo da avere il contesto (indirizzi IP, tipo di dispositivo e così via) per i problemi di prestazioni che si verificano.
    
  - I server proxy sono punti di uscita comuni, quindi puoi controllare il web browser per vedere quale server proxy è impostato per l'uso, se presente.
    
  - Esistono strumenti di terze parti in grado di individuare e mappare la rete, ma il modo più sicuro per conoscere i dispositivi è chiedere a un membro del team di rete.
    
- Identificare il provider di servizi Internet (ISP), annotarne le informazioni di contatto e chiedere a quanti circuiti è disponibile la larghezza di banda.
    
- All'interno dell'azienda, identificare le risorse per i dispositivi tra il client e il punto di uscita oppure identificare un contatto di emergenza con cui parlare di problemi di rete.
    
Ecco alcune linee di base che possono essere calcolate automaticamente da semplici test con strumenti:
  
- Tempo dal computer client al punto di uscita in millisecondi
    
- Tempo dal punto di uscita a Office 365 in millisecondi
    
- Percorso nel mondo del server che risolve gli URL per Office 365 durante l'esplorazione
    
- Velocità della risoluzione DNS dell'ISP in millisecondi, incoerenze nell'arrivo dei pacchetti (instabilità di rete), tempi di caricamento e download in millisecondi
    
Se non si ha familiarità con come eseguire questi passaggi, verranno fornite informazioni più dettagliate in questo articolo. 
  
## <a name="what-is-a-baseline"></a>Che cos'è una linea di base?

Si conoscerà l'impatto quando si verifica un problema, ma se non si conoscono i dati cronologici sulle prestazioni, non è possibile avere un contesto per quanto male potrebbe essere diventato e quando. Quindi, senza una linea di base, ti manca l'indizio chiave per risolvere il puzzle: l'immagine nella casella del puzzle. Nella risoluzione dei problemi di prestazioni è necessario un punto di *confronto.* Le semplici linee di base delle prestazioni non sono difficili da prendere. Il team operations può avere il compito di eseguire queste operazioni in base a una pianificazione. Si supponga ad esempio che la connessione sia simile alla seguente: 
  
![Un elemento grafico di rete di base che mostra client, proxy e Office 365 cloud.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Ciò significa che hai controllato con il team di rete e hai scoperto che lasci la tua azienda per Internet tramite un server proxy e che il proxy gestisce tutte le richieste inviate dal computer client al cloud. In questo caso, devi disegnare una versione semplificata della connessione in cui sono elencati tutti i dispositivi che intervengono. A questo punto, inserire gli strumenti che è possibile utilizzare per testare le prestazioni tra il client, il punto di uscita (dove si lascia la rete per Internet) e il cloud Office 365 locale.
  
![Rete di base con client, proxy e cloud e suggerimenti per gli strumenti PSPing, TraceTCP e tracce di rete.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
Le opzioni sono elencate **come Semplici** **e** Avanzate a causa della quantità di competenze necessarie per trovare i dati sulle prestazioni. Una traccia di rete richiederà molto tempo, rispetto all'esecuzione di strumenti da riga di comando come PsPing e TraceTCP. Questi due strumenti della riga di comando sono stati scelti perché non utilizzano pacchetti ICMP, che verranno bloccati da Office 365 e perché forniscono il tempo in millisecondi necessario per lasciare il computer client o il server proxy (se si dispone dell'accesso) e arrivare a Office 365. Ogni singolo hop da un computer all'altro finirà con un valore di tempo ed è ottimo per le linee di base. Come importante, questi strumenti da riga di comando consentono di aggiungere un numero di porta al comando, ciò è utile perché Office 365 comunica tramite la porta 443, ovvero la porta utilizzata da Secure Sockets Layer e Transport Layer Security (SSL e TLS). Tuttavia, altri strumenti di terze parti potrebbero essere soluzioni migliori per la propria situazione. Microsoft non supporta tutti questi strumenti, quindi se, per qualche motivo, non è possibile far funzionare PsPing e TraceTCP, passare a una traccia di rete con uno strumento come Netmon. 
  
È possibile prendere una previsione prima dell'orario di ufficio, di nuovo durante un uso intenso e quindi di nuovo dopo ore. Ciò significa che potresti avere una struttura di cartelle simile alla seguente alla fine:
  
![Grafica che propone una soluzione per organizzare i dati delle prestazioni in cartelle.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
È inoltre consigliabile scegliere una convenzione di denominazione per i file. Ecco alcuni esempi:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
Esistono molti modi diversi per eseguire questa operazione, ma l'uso del formato **\<dateTime\>\<what's happening in the test\>** è un buon punto di partenza. La diligenza in questo caso è molto utile quando si tenta di risolvere i problemi in un secondo momento. In seguito, potrai dire "Ho preso due tracce l'8 febbraio, una ha mostrato buone prestazioni e una ha mostrato risultati non ottimali, quindi possiamo confrontarle". Questo è estremamente utile per la risoluzione dei problemi. 
  
È necessario disporre di un modo organizzato per mantenere le previsioni cronologiche. In questo esempio, i metodi semplici generavano tre output della riga di comando e i risultati venivano raccolti come schermate, ma potresti avere invece file di acquisizione di rete. Usa il metodo più adatto a te. Archiviare le previsioni cronologiche e fare riferimento a tali dati nei punti in cui si notano modifiche nel comportamento dei servizi online. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Perché raccogliere dati sulle prestazioni durante un progetto pilota?

Non c'è tempo migliore per iniziare a creare linee di base rispetto a un progetto pilota del Office 365 servizio. L'ufficio può avere migliaia di utenti, centinaia di migliaia o cinque, ma anche con un numero limitato di utenti, è possibile eseguire test per misurare le fluttuazioni delle prestazioni. Nel caso di una società di grandi dimensioni, un campione rappresentativo di diverse centinaia di utenti che pilotano Office 365 può essere proiettato verso l'esterno a diverse migliaia in modo da sapere dove potrebbero verificarsi i problemi prima che si verificano.
  
Nel caso di una piccola azienda, in cui l'on-boarding significa che tutti gli utenti passano al servizio contemporaneamente e non esiste un progetto pilota, mantenere le misure delle prestazioni in modo da disporre di dati da mostrare a chiunque possa avere a che fare con la risoluzione dei problemi di un'operazione con prestazioni non ottimali. Ad esempio, se si nota che all'improvviso è possibile aggirare l'edificio nel tempo necessario per caricare un elemento grafico di medie dimensioni in cui si verificava molto rapidamente.
  
## <a name="how-to-collect-baselines"></a>Come raccogliere le linee di base

Per tutti i piani di risoluzione dei problemi è necessario identificare almeno questi elementi:
  
- Il computer client in uso (il tipo di computer o dispositivo, un indirizzo IP e le azioni che hanno causato il problema)
    
- Posizione in cui si trova il computer client nel mondo (ad esempio, se l'utente su una VPN si trova in rete, lavorando in remoto o nella rete Intranet aziendale)
    
- Il punto di uscita utilizzato dal computer client dalla rete (il punto in cui il traffico lascia l'azienda per un ISP o Internet)
    
 È possibile trovare il layout della rete dall'amministratore di rete. Se si è in una rete di piccole dimensioni, esaminare i dispositivi che si connettono a Internet e chiamare l'ISP in caso di domande sul layout. Crea un elemento grafico del layout finale per il riferimento. 
  
Questa sezione è suddivisa in semplici strumenti e metodi da riga di comando e opzioni degli strumenti più avanzate. Prima di tutto verranno descritti i metodi semplici. Tuttavia, se al momento si verifica un problema di prestazioni, è consigliabile passare a metodi avanzati e provare il piano di azione per la risoluzione dei problemi di prestazioni di esempio.
  
### <a name="simple-methods"></a>Metodi semplici

L'obiettivo di questi semplici metodi è imparare a prendere, comprendere e archiviare correttamente semplici previsioni delle prestazioni nel tempo in modo da essere informati sulle prestazioni Office 365 prestazioni. Ecco il diagramma molto semplice, come illustrato in precedenza:
  
![Rete di base con client, proxy e cloud e suggerimenti per gli strumenti PSPing, TraceTCP e tracce di rete.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP è incluso in questa schermata perché è uno strumento utile per visualizzare, in millisecondi, il tempo necessario per l'elaborazione di una richiesta e il numero di hop di rete o connessioni da un computer all'altro, necessari per raggiungere una destinazione. TraceTCP può anche assegnare i nomi dei server utilizzati durante gli hop, che può essere utile per uno Microsoft Office 365 risoluzione dei problemi in Supporto. > comandi TraceTCP possono essere molto semplici, ad esempio: >> ricordarsi di includere il numero  `tracetcp.exe outlook.office365.com:443` di porta nel comando. > [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) è un download gratuito, ma si basa su Wincap. Wincap è uno strumento utilizzato e installato anche da Netmon. Usiamo anche Netmon nella sezione dei metodi avanzati. 
  
 Se si dispone di più uffici, sarà necessario conservare un set di dati da un client anche in ognuna di queste posizioni. Questo test misura la latenza, che in questo caso è un valore numerico che descrive la quantità di tempo tra un client che invia una richiesta a Office 365 e Office 365 risponde alla richiesta. Il test ha origine all'interno del dominio in un computer client e cerca di misurare un percorso di andata e ritorno dall'interno della rete, attraverso un punto di uscita, attraverso Internet per Office 365 e ritorno. 
  
Esistono diversi modi per gestire il punto di uscita, in questo caso il server proxy. È possibile tracciare da 1 a 2 e quindi da 2 a 3 e quindi aggiungere i numeri in millisecondi per ottenere un totale finale al bordo della rete. In caso contrario, è possibile configurare la connessione in modo da ignorare il proxy per Office 365 indirizzi. In una rete più grande con un firewall, un proxy inverso o una combinazione di questi due, potrebbe essere necessario creare eccezioni sul server proxy che consentiranno il passaggio del traffico per molti URL. Per l'elenco degli endpoint usati da Office 365, vedere [Office 365 URL e intervalli di indirizzi IP.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) Se si dispone di un proxy di autenticazione, iniziare verificando le eccezioni per gli elementi seguenti:
  
- Porte 80 e 443
    
- TCP e HTTP
    
- Connessioni in uscita a uno di questi URL:
    
- \*.microsoftonline.com
    
- \*.microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*.outlook.com
    
- \*.lync.com
    
- osub.microsoft.com
    
A tutti gli utenti deve essere consentito accedere a questi indirizzi senza alcuna interferenza proxy o autenticazione. In una rete più piccola, è consigliabile aggiungerli all'elenco di bypass proxy nel Web browser. 
  
Per aggiungerli all'elenco di bypass proxy in Internet Explorer, vai **a** Strumenti \> **Opzioni Internet** \> **Connessioni** \> **Impostazioni LAN** \> **Avanzate**. Nella scheda Avanzate è inoltre possibile trovare il server proxy e la porta del server proxy. Potrebbe essere necessario fare clic sulla casella di controllo Usa un server proxy per la **rete LAN** per accedere al **pulsante** Avanzate. È necessario verificare che sia selezionata l'opzione **Ignora server proxy** per gli indirizzi locali. Dopo aver fatto **clic su Avanzate,** verrà visualizzata una casella di testo in cui è possibile immettere le eccezioni. Separare gli URL con caratteri jolly elencati in precedenza con punti e virgola, ad esempio:
  
\*.microsoftonline.com; \*.sharepoint.com
  
Dopo aver ignorato il proxy, dovresti essere in grado di usare ping o PsPing direttamente su un URL Office 365. Il passaggio successivo consisterà nel testare il ping **outlook.office365.com**. In caso contrario, se si utilizza PsPing o un altro strumento che consente di fornire un numero di porta al comando, PsPing su **portal.microsoftonline.com:443** per visualizzare il tempo medio di round trip in millisecondi. 
  
Il tempo di round trip, o RTT, è un valore numerico che misura il tempo necessario per inviare una richiesta HTTP a un server come outlook.office365.com e ottenere una risposta che riconosca che il server è a conoscenza dell'operazione. A volte vedrai questa abbreviazione come RTT. Dovrebbe trattarsi di un periodo di tempo relativamente breve.
  
È necessario utilizzare [PSPing](/sysinternals/downloads/psping) o un altro strumento che non utilizza pacchetti ICMP bloccati da Office 365 per eseguire questo test. 
  
 **Come usare PsPing per ottenere un tempo complessivo di round trip in millisecondi direttamente da un URL Office 365**
  
1. Eseguire un prompt dei comandi con privilegi elevati completando la procedura seguente:
    
1. Fare clic su **Avvia**.
    
2. Nella casella **Inizia ricerca** digitare cmd e quindi premere CTRL+MAIUSC+INVIO.
    
3. Se viene visualizzata la finestra di dialogo **Controllo account utente**, confermare che l'azione visualizzata è quella desiderata e scegliere **Continua**.
    
2. Passare alla cartella in cui è installato lo strumento (in questo caso PsPing) e testare Office 365 URL:
    
  - psping admin.microsoft.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![Il comando PSPing sta per microsoft-my.sharepoint.com porta 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Assicurarsi di includere il numero di porta 443. Ricorda che Office 365 funziona su un canale crittografato. Se psPing senza il numero di porta, la richiesta avrà esito negativo. Dopo aver evaso il ping dell'elenco breve, cercare Il tempo medio in millisecondi (ms). Questo è ciò che si desidera registrare.
  
![Immagine che mostra un'illustrazione di PSPing da client a proxy con un tempo di round trip di 2,8 millisecondi.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Se non si ha familiarità con il bypass proxy e si preferisce eseguire operazioni dettagliate, è innanzitutto necessario individuare il nome del server proxy. In Internet Explorer vai a **Strumenti** \> **Opzioni Internet** \> **Connessioni** \> **IMPOSTAZIONI LAN** \> **Avanzate**. La **scheda** Avanzate consente di visualizzare il server proxy elencato. Eseguire il ping del server proxy al prompt dei comandi completando questa attività: 
  
 **Per eseguire il ping del server proxy e ottenere un valore di round trip in millisecondi per la fase da 1 a 2**
  
1. Eseguire un prompt dei comandi con privilegi elevati completando la procedura seguente:
    
1. Fare clic su **Avvia**.
    
2. Nella casella **Inizia ricerca** digitare cmd e quindi premere CTRL+MAIUSC+INVIO.
    
3. Se viene visualizzata la finestra di dialogo **Controllo account utente**, confermare che l'azione visualizzata è quella desiderata e scegliere **Continua**.
    
2. Digitare ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> e quindi premere INVIO. Se hai installato PsPing o un altro strumento, puoi scegliere di usare lo strumento. 
    
    Il comando potrebbe essere simile a uno di questi esempi: 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping ourproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy:80
    
3. Quando la traccia smette di inviare pacchetti di test, si otterrà un breve riepilogo che elenca una media, in millisecondi, e questo è il valore che si sta cercando. Fai una cattura di schermata del prompt e salvala usando la convenzione di denominazione. A questo punto può anche essere utile compilare il diagramma con il valore.
    
Forse hai preso una traccia la mattina presto e il client può accedere rapidamente al proxy (o a qualsiasi server in uscita esce da Internet). In questo caso, i numeri potrebbero essere simili al seguente:
  
![Grafico che mostra il tempo di round trip da un client a un proxy di 2,8 millisecondi.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Se il computer client è uno dei pochi selezionati con accesso al server proxy (o in uscita), è possibile eseguire la fase successiva del test connettendosi in remoto a tale computer, eseguendo il prompt dei comandi a PsPing a un URL di Office 365 da lì. Se non si dispone dell'accesso a tale computer, è possibile contattare le risorse di rete per assistenza con la prossima fase e ottenere numeri esatti in questo modo. Se ciò non è possibile, eseguire psPing rispetto all'URL Office 365 in questione e confrontarlo con l'ora PsPing o Ping con il server proxy. 
  
Ad esempio, se hai 51,84 millisecondi dal client all'URL di Office 365 e hai 2,8 millisecondi dal client al proxy (o punto di uscita), hai 49,04 millisecondi dall'uscita a Office 365. Analogamente, se si dispone di un valore PsPing di 12,25 millisecondi dal client al proxy durante l'altezza del giorno e di 62,01 millisecondi dal client all'URL Office 365, il valore medio per l'uscita del proxy all'URL di Office 365 è 49,76 millisecondi.
  
![Grafico aggiuntivo che mostra il ping in millisecondi dal client al proxy accanto al client Office 365 in modo che i valori possano essere sottratti.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
In termini di risoluzione dei problemi, potresti trovare qualcosa di interessante solo dal mantenere queste linee di base. Ad esempio, se in genere si dispone di circa 40-59 millisecondi di latenza dal proxy o in uscita all'URL di Office 365 e si dispone di un client per eseguire il proxy o la latenza del punto di uscita di circa 3-7 millisecondi (a seconda della quantità di traffico di rete che si sta visualizzando durante l'ora del giorno), si saprà sicuramente che qualcosa è problematico se gli ultimi tre client per eseguire il proxy o l'uscita delle linee di base mostrano una latenza di 45 millisecondi.
  
### <a name="advanced-methods"></a>Metodi avanzati

Se si vuole realmente sapere cosa accade con le richieste Internet per Office 365, è necessario acquisire familiarità con le tracce di rete. Non importa quali strumenti preferisci per queste tracce, HTTPWatch, Netmon, Message Analyzer, Wireshark, Fiddler, strumento Developer Dashboard o qualsiasi altro strumento farà tutto il tempo che lo strumento può acquisire e filtrare il traffico di rete. Vedrai in questa sezione che è utile eseguire più di uno di questi strumenti per ottenere un quadro più completo del problema. Durante i test, alcuni di questi strumenti agiscono anche come proxy a loro volta. Gli strumenti utilizzati nell'articolo [complementare,](performance-troubleshooting-plan.md)Piano di risoluzione dei problemi di prestazioni per Office 365 , includono [Netmon 3.4,](https://www.microsoft.com/download/details.aspx?id=4865) [HTTPWatch](https://www.httpwatch.com/download/)o [WireShark.](https://www.wireshark.org/)
  
L'esecuzione di una previsione delle prestazioni è la parte semplice di questo metodo e molti dei passaggi sono gli stessi di quando si risolve un problema di prestazioni. I metodi più avanzati per creare linee di base per le prestazioni richiedono di prendere e archiviare le tracce di rete. La maggior parte degli esempi in questo articolo utilizza SharePoint Online, ma è consigliabile sviluppare un elenco di azioni comuni tra i servizi Office 365 a cui si sottoscrive il test e la registrazione. Ecco un esempio di base:
  
- Elenco di base per SPO - ** Passaggio 1: ** Esplorare la home page del sito Web di SpO ed eseguire una traccia di rete. Salvare la traccia. 
    
- Elenco di base per SpO - **Passaggio 2:** cercare un termine (ad esempio il nome della società) tramite Enterprise Ricerca ed eseguire una traccia di rete. Salvare la traccia. 
    
- Elenco di base per SpO - **Passaggio 3:** Upload un file di grandi dimensioni in una raccolta documenti di SharePoint Online ed eseguire una traccia di rete. Salvare la traccia. 
    
- Elenco di base per SpO - **Passaggio 4:** esplorare la home page del sito Web di OneDrive ed eseguire una traccia di rete. Salvare la traccia. 
    
Questo elenco deve includere le azioni comuni più importanti intraprese dagli utenti SharePoint Online. Si noti che l'ultimo passaggio, per risalire a OneDrive for Business, genera un confronto tra il carico della home page di SharePoint Online (spesso personalizzata dalle aziende) e la home page di OneDrive for Business, che raramente viene personalizzata. Si tratta di un test molto semplice quando si tratta di un sito SharePoint online a caricamento lento. È possibile creare un record di questa differenza nei test.
  
Se si è nel bel mezzo di un problema di prestazioni, molti dei passaggi sono gli stessi di quando si prende una linea di base. Le tracce di rete diventano critiche, quindi  *gestiremo*  come prendere le tracce importanti. 
  
Per risolvere un problema di  *prestazioni,*  in questo momento è necessario prendere una traccia nel momento in cui si verifica il problema di prestazioni. È necessario disporre degli strumenti adeguati per raccogliere i registri e di un piano d'azione, cio? un elenco delle azioni di risoluzione dei problemi da eseguire per raccogliere le informazioni migliori che è possibile. La prima operazione da eseguire è registrare la data e l'ora del test in modo che i file possano essere salvati in una cartella che rifletta l'intervallo. Successivamente, circoscrivere i passaggi del problema. Questi sono i passaggi esatti che verranno utilizzati per i test. Non dimenticare le nozioni di base: se il problema riguarda solo Outlook, assicurati di registrare che il comportamento del problema si verifica in un solo Office 365 servizio. Restringere l'ambito di questo problema ti aiuterà a concentrarti su qualcosa che puoi risolvere. 
  
## <a name="see-also"></a>Vedere anche

[Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)