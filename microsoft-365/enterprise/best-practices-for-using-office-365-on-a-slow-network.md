---
title: Procedure consigliate per l'Office 365 su una rete lenta
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: End User
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- MET150
- MET150
- MOP150
- MEW150
- BCS160
ms.assetid: fd16c8d2-4799-4c39-8fd7-045f06640166
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Questo articolo illustra le procedure consigliate che è possibile adottare per l'utilizzo di Office 365 in una rete lenta.
ms.openlocfilehash: d217ee8bb40898716844717e84db112f356f6672
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226024"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Procedure consigliate per l'Office 365 su una rete lenta

Non sarebbe bello se la connessione Internet fosse sempre veloce e mai in calo? Forse quel giorno verrà. Ma nel frattempo, ci sono cose pratiche che puoi fare per aggirare una rete sfacciante e comunque per fare il tuo lavoro quotidiano. Sebbene Office 365 sia un servizio basato su cloud, offre anche molti modi per lavorare con il contenuto offline e mantenere le modifiche sincronizzate senza problemi. Inoltre, a volte è più efficiente lavorare con il contenuto offline solo perché le applicazioni vengono eseguite più velocemente e l'interfaccia utente è più reattiva. Il punto è questo: Office 365 offre il meglio di entrambi i mondi. Ecco come sfruttare questo vantaggio.

> [!TIP]
> Vuoi vedere quanto è lenta (o veloce) la connessione di rete? Prova il [test OOKLA Speed o](https://www.speedtest.net/) [l'app Network Speed Test.](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70)

## <a name="why-is-my-network-so-slow"></a>Perché la rete è così lenta?

Anche se non hai il controllo sulle prestazioni di rete, aiuta a capire cosa succede dietro le quinte. Internet è estremamente complesso, ma esistono alcuni concetti che consentono di comprendere meglio la situazione. Seguire le procedure consigliate in questo articolo può aiutare a risolvere i problemi di prestazioni e ridurre la frustrazione.

### <a name="major-factors-that-affect-network-performance"></a>Fattori principali che influiscono sulle prestazioni della rete

![Fattori relativi alle prestazioni di rete](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)

 **Larghezza di banda e latenza:** le due misure più importanti delle prestazioni di rete sono larghezza di banda e latenza:

- La larghezza di banda è la velocità effettiva misurata in bit al secondo. Più grande è meglio. La larghezza di banda è simile a una condotta d'acqua. Più grande è il tubo, più acqua è possibile "passare" attraverso di esso.

- La latenza è il tempo necessario per ottenere il contenuto da un server o un servizio al dispositivo ed è misurata in millisecondi. Più veloce è meglio. La latenza può essere causata da diversi fattori, tra cui una larghezza di banda bassa, una connessione scarsa o un tempo di trasmissione.

 **Problemi comuni:** oltre alla larghezza di banda e alla latenza, altri problemi influiscono sulle prestazioni della rete e spesso sono imprevedibili. Le prestazioni di rete possono variare in base all'ora del giorno o alla posizione fisica. La rete può diventare intasata quando si verificano determinati eventi che impetono l'uso di Internet, ad esempio una calamità naturale o un evento pubblico importante. Le dimensioni e la complessità della pagina caricata e il numero e le dimensioni dei file trasferiti hanno un impatto diretto sulle prestazioni. Una connessione WiFi può degradare temporaneamente: ad esempio, puoi eseguire il polling di una riunione di conferenze di grandi dimensioni di migliaia richiedendo a tutti di twittare contemporaneamente.

 **Considerazioni per una** rete satellite: una rete satellite è utile quando una rete terrestre non è fattibile, ad esempio il paese di ritorno, una nave da crociera o un'area scientifica remota. Queste reti si basano su satelliti posizionati in un orbito geosincrono a 22.000 miglia sopra l'equatore. Tuttavia, una trasmissione viaggia effettivamente per circa 90.000 miglia e quindi una rete satellite ha una latenza più lenta (500 ms o più) rispetto a una rete terrestre (da 20 a 50 ms). Nelle condizioni migliori, potresti non notare questa latenza, ma per il download di file di grandi dimensioni, lo streaming di video e la riproduzione di giochi, probabilmente lo farete. Un altro problema è la "dissolvenza della pioggia" in cui il tempo intenso, come temporali e bufere di neve, può interrompere temporaneamente la trasmissione satellitare.

## <a name="are-you-sure-its-the-network"></a>Sei sicuro che sia la rete?

Ogni volta che si verificano problemi di prestazioni, assicurati innanzitutto che il dispositivo non sia la causa principale del problema. È possibile eseguire due operazioni che potrebbero migliorare in modo significativo:

- Assicurati che il dispositivo sia in esecuzione e che non sia presente malware nel computer.

- Se possibile, acquistare più memoria. L'aggiunta di memoria è il modo più semplice e spesso più efficace per migliorare le prestazioni del dispositivo. È particolarmente utile quando si lavora con file e video di grandi dimensioni.

Per ulteriori informazioni, vedere [Windows Prestazioni](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) e manutenzione e Suggerimenti per migliorare le prestazioni [del PC in Windows 10](https://support.microsoft.com/help/4002019/windows-10-improve-pc-performance).

## <a name="best-practices-for-using-your-browser"></a>Procedure consigliate per l'utilizzo del browser

Il browser è il gateway per Office 365, quindi può influire sulle prestazioni, in particolare con il tempo necessario per caricare una pagina e la frequenza di round trip al servizio Office 365.

### <a name="browsers-in-general"></a>Browser in generale

Ecco alcuni suggerimenti per i browser in generale:

- Disabilitare i componenti aggiuntivi del browser che potrebbero influire sulle prestazioni o che non sono necessari.

- Aumentare le dimensioni della cache per i file temporanei Internet.

- Dopo aver effettuato l'accesso al tuo account aziendale o dell'istituto di istruzione, tieni aperta la finestra del browser per tutta la giornata. È possibile aprire altre schede e finestre senza eseguire di nuovo l'accesso. Se devi accedere a un altro account, usa Esplorazione privata.

- Dopo aver scaricato e aperto ogni pagina, tienile aperte usando le schede. È facile spostarsi tra le schede e usare la pagina in un secondo momento della giornata. Aggiornare una pagina solo se sono necessari i dati più recenti in tale pagina.

- Se l'apertura di una pagina sta prendendo troppo tempo, arrestare il download della pagina (premere ESC) e quindi aggiornare la pagina (premere F5).

- Quando possibile, ridurre i round trip a Office 365. Ad esempio, anziché eseguire il paging tra elenchi o raccolte, utilizzare la ricerca per individuare i file in una raccolta di grandi dimensioni e filtrare in un elenco per ottenere direttamente i risultati desiderati. In caso contrario, creare visualizzazioni che riducono al minimo il tempo di caricamento della pagina. Per ulteriori informazioni, vedere [Manage large lists and libraries in Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES).

- Se le prestazioni video sono scarse, potresti essere in grado di scaricare il video e guardarlo sul dispositivo. È possibile che sia disponibile un collegamento di download oppure che sia possibile fare clic con il pulsante destro del mouse sul collegamento video e scegliere **Salva destinazione con nome.**

### <a name="browser-specific"></a>Specifico del browser

Ecco alcuni suggerimenti per il browser specifico:

- **Internet Explorer:** eseguire l'aggiornamento a Internet Explorer versione 11 o successiva per miglioramenti sostanziali delle prestazioni rispetto alle versioni precedenti. Per ulteriori informazioni, vedere [Guida alla risoluzione dei problemi per Internet Explorer.](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365)
- **FireFox:** per ulteriori informazioni, vedere [Firefox è lento o smette di funzionare.](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging)
- **Safari:** per ulteriori informazioni, vedi [Apple - Safari.](https://www.apple.com/safari/)
- **Chrome:** per ulteriori informazioni, vedi [la Guida di Chrome.](https://support.google.com/chrome/?hl=en)

## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Procedure consigliate per l'Outlook e Outlook Web App

Leggere, scrivere e organizzare la posta elettronica è una parte importante della giornata di tutti. Sia Outlook che Outlook Web App (OWA) offrono supporto offline. L'uso di un'app di posta elettronica sullo smartphone è un'altra alternativa utile. Utilizzare le opzioni seguenti più adatte alle proprie esigenze:

- Eseguire l'aggiornamento alla versione più recente di Outlook per miglioramenti sostanziali delle prestazioni rispetto alle versioni precedenti.

- Outlook Web App consente di creare messaggi offline, contatti ed eventi del calendario che vengono caricati quando OWA è in grado di connettersi a Office 365. Per ulteriori informazioni sulla configurazione e l'utilizzo di OWA in modalità offline, vedere [Using Outlook Web App offline](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36).

- Outlook consente di lavorare in modalità cache, in cui si connette automaticamente quando possibile. È possibile scaricare Outlook'intera cassetta postale o solo una parte di essa. Per ulteriori informazioni, vedere [Attivare la modalità Exchange cache](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) e Lavorare offline in [Outlook](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

- Outlook offre anche una modalità offline. Per usare questo metodo, devi prima configurare la modalità cache in modo che le informazioni del tuo account vengono copiate nel computer. In modalità offline, Outlook tenterà di connettersi usando le impostazioni di invio e ricezione o quando la si imposta manualmente per il funzionamento online. Per ulteriori informazioni, vedere [Work offline to avoid data connection charges,](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282)Change send and receive settings when you work [offline](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)e Switch from working offline [to online.](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9)

- Se si dispone di uno smart phone, è possibile utilizzarlo per la ricerca di posta elettronica e calendario sulla rete dell'operatore telefonico.

> [!NOTE]
> Ecco alcune indicazioni su quando usare Outlook o OWA. Se lo spazio su disco non è un problema nel dispositivo, Outlook ha un set completo di funzionalità e potrebbe funzionare meglio per te. Se lo spazio su disco è un problema nel dispositivo, valuta la possibilità di usare un OWA che dispone di un sottoinsieme di funzionalità, ma che funziona meglio anche in una situazione online. Naturalmente, è possibile utilizzare entrambi perché funzionano bene insieme.

## <a name="best-practices-for-using-onedrive-for-business"></a>Procedure consigliate per l'OneDrive for Business

OneDrive for Business è progettato da zero per lavorare con i file online e offline. Dopo la configurazione, la sincronizzazione delle modifiche viene eseguita automaticamente e in modo affidabile ovunque e ogni volta che vengono apportate. Se la rete è lenta, è possibile utilizzare la versione offline dei file.

L OneDrive for Business app di sincronizzazione SharePoint online e Office 365 business oppure puoi [](https://support.microsoft.com/kb/2903984) scaricare gratuitamente l'app di OneDrive for Business sincronizzazione. Questa app è anche più veloce rispetto **all'uso dei** comandi Apri in Esplora risorse o **Upload** comandi. Per ulteriori informazioni, vedere [Set up your computer to sync your OneDrive for Business files in Office 365](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16).

Ecco alcune indicazioni aggiuntive per l'uso dell'app OneDrive for Business sincronizzazione:

- Se stai sincronizzando una raccolta di grandi dimensioni per la prima volta, avvia la sincronizzazione durante le ore non lavorative, ad esempio durante la notte.
- Puoi usare la funzionalità [Interrompi sincronizzazione](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) di una raccolta con OneDrive for Business'app per interrompere temporaneamente la sincronizzazione degli aggiornamenti. Tuttavia, utilizzare questa funzionalità per brevi periodi, ad esempio alcune ore alla volta, per evitare l'accodamento di un numero elevato di aggiornamenti e per ridurre al minimo il rischio di conflitti di unione se più persone lavorano sullo stesso documento.

## <a name="best-practices-for-using-onenote"></a>Procedure consigliate per l'OneNote

Ogni SharePoint del team dispone di un blocco appunti OneNote predefinito ed è possibile crearne facilmente uno personalizzato. OneNote è un ottimo modo per raccogliere informazioni aggiornate necessarie ogni giorno per eseguire le attività. Ad esempio, molti team usano OneNote come punto di raccolta per riunioni settimanali, note di progetto, idee, piani e relazioni sullo stato. È possibile organizzare in modo ordinato queste informazioni diverse utilizzando pagine, sezioni e schede.

La cosa più OneNote è che puoi accedere al contenuto praticamente da qualsiasi dispositivo, sia da un desktop, un portatile, un tablet o uno smart phone. E non è necessario preoccuparsi del salvataggio o della sincronizzazione perché OneNote l'utente.

Per ulteriori informazioni, vedere [Microsoft OneNote](https://office.microsoft.com/onenote).

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Procedure consigliate per l'Skype for Business e Lync Online

Di seguito sono riportate le linee guida generali per l'utilizzo di Skype for Business o Lync Online quando la rete è lenta:

- Utilizzare la messaggistica istantanea ogni volta che è possibile perché funziona bene su una rete lenta.

- Evitare di effettuare chiamate telefoniche tramite una rete privata virtuale (VPN) o connessioni RAS (Remote Access Service).

- Assicurati che il dispositivo audio sia approvato. Per ulteriori informazioni, vedere [Telefoni e dispositivi qualificati per Microsoft Lync.](/skypeforbusiness/lync-cert/ip-phones)

- Quando si PowerPoint in una presentazione online, ridurre le dimensioni e la complessità delle diapositive. Per ulteriori informazioni, vedere [Suggerimenti per migliorare le prestazioni della presentazione.](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949)

- Le prestazioni video dipendono molto dalle prestazioni della rete. Evita di usare video se la rete è lenta.

Per ulteriori informazioni, vedere Qualità audio o video scarsa [in Lync Online](https://support.microsoft.com/kb/2386655)o come risolvere i problemi di connessione in [Skype for Business](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771).

## <a name="best-practices-for-using-sharepoint-lists"></a>Procedure consigliate per l'utilizzo SharePoint elenchi

Utilizzare i dati degli elenchi offline per "eseguire lo scrubbing", analizzare o segnalare i dati è un ottimo modo per ridurre al minimo l'impatto di una rete lenta. È possibile leggere e scrivere la maggior parte degli elenchi da Microsoft Access 2019 e Microsoft Access 2016 collegandoli ad essi. È inoltre possibile esportare un elenco in un Excel Table, che crea una connessione dati unidirezione tra la tabella Excel e l'elenco. Informazioni su Come lavorare offline con tabelle collegate a SharePoint [elenchi.](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e)

Per ulteriori informazioni, vedere la sezione "Ulteriori informazioni sulla gestione di elenchi di grandi [dimensioni"](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784)in Manage large lists and libraries in Office 365 .

## <a name="best-practices-for-customizing-web-pages"></a>Procedure consigliate per la personalizzazione delle pagine Web

Quando si personalizza una pagina Web, si potrebbero inavvertitamente causare prestazioni scarse con la pagina. Un certo numero di fattori può avere un impatto, ad esempio la complessità e le dimensioni della pagina, il numero di web part aggiunte, il numero di elementi di elenchi o di raccolta inizialmente visualizzati e il modo in cui si codifica la pagina.

Per ulteriori informazioni, vedere [Tune SharePoint Online performance.](tune-sharepoint-online-performance.md)

## <a name="best-practices-for-using-project-online"></a>Procedure consigliate per l'utilizzo Project Online

Le linee guida seguenti consentono di migliorare le prestazioni di rete.

- Project Online e SharePoint Online richiedono la sincronizzazione, che può richiedere molto tempo. Se i team di progetto hanno un fatturato basso, disabilitare Project Sincronizzazione siti per migliorare le prestazioni Project pubblicare e Project pagine dettagli. Limitare la sincronizzazione di Active Directory a gruppi di risorse che devono effettivamente utilizzare il sistema e monitorare eventuali problemi di autorizzazione dopo la sincronizzazione di gruppi di grandi dimensioni.

- Se l'organizzazione utilizza siti di progetto, crearli su richiesta anziché automaticamente. Ciò velocizza la prima esperienza di pubblicazione ed evita la creazione di siti e contenuti non necessari.

- Project Le pagine di dettaglio (PDP) possono attivare un ricalcolo dell'intero progetto e avviare le azioni del flusso di lavoro, entrambe operazioni che richiedono un utilizzo intensivo delle prestazioni. Per evitare di attivare due processi di aggiornamento contemporaneamente nello stesso PDP, evitare di aggiornare i campi del calendario (Data inizio, Data fine, Data stato e Data corrente) e i campi non programmati (nome del progetto, descrizione e proprietario).

- Ridurre il numero di Web part e campi personalizzati visualizzati in ogni PDP. Creare un PDP dedicato con gli unici campi che richiedono l'aggiornamento per migliorare il carico e risparmiare tempo.

- Quando si utilizza OData per la creazione di report, limitare la quantità di dati su cui si esegue una query in fase di esecuzione utilizzando il filtro sul lato server.

Per ulteriori informazioni, vedere [Tune Project Online performance.](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)

## <a name="whats-the-best-way-to-report-problems"></a>Qual è il modo migliore per segnalare i problemi?

Microsoft migliora continuamente le prestazioni complessive di Office 365 monitorando la rete, misurando larghezza di banda e latenza, migliorando i tempi di caricamento delle pagine, riducendo l'I/O su disco, riprogettando le pagine per usare la strategia di download minima, aggiungendo hardware ai data center e aggiungendo altri data center. Per ulteriori informazioni sul controllo dello stato corrente e sulla segnalazione dei problemi, vedere Come verificare l'integrità Office 365 [servizio.](view-service-health.md)

## <a name="see-also"></a>Vedere anche

[Pianificazione della rete e ottimizzazione delle prestazioni per Office 365](network-planning-and-performance.md)

[Principi della connettività di rete di Office 365](microsoft-365-network-connectivity-principles.md)

[Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Domande frequenti sugli endpoint di Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
