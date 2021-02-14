---
title: Procedure consigliate per l'uso di Office 365 in una rete lenta
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
description: Questo articolo illustra le procedure consigliate che è possibile adottare per l'uso di Office 365 in una rete lenta.
ms.openlocfilehash: a0a15191fa0240f24cecc5e595de9a259cacc9f9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691364"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Procedure consigliate per l'uso di Office 365 in una rete lenta

Non sarebbe bello se la connessione Internet fosse sempre veloce e mai in basso? Forse quel giorno verrà. Nel frattempo, tuttavia, ci sono cose pratiche che puoi fare per aggirare una rete sballante e comunque eseguire il tuo lavoro quotidiano. Anche se Office 365 è un servizio basato sul cloud, offre anche molti modi per lavorare con i contenuti offline e per mantenere le modifiche sincronizzate senza problemi. Inoltre, a volte è più efficiente lavorare con il contenuto offline solo perché le applicazioni vengono eseguite più velocemente e l'interfaccia utente è più reattiva. Il punto è questo: Office 365 offre il meglio di entrambi i tipi di mondo. Ecco come sfruttare questo vantaggio. 
  
> [!TIP]
> Vuoi vedere quanto è lenta (o veloce) la connessione di rete? Prova il [test OOKLA Speed o](https://www.speedtest.net/) [l'app Network Speed Test.](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70) 

## <a name="why-is-my-network-so-slow"></a>Perché la rete è così lenta?

Anche se non hai il controllo sulle prestazioni di rete, ti aiuta a capire cosa succede dietro le quinte. Internet è estremamente complesso, ma esistono alcuni concetti che consentono di comprendere meglio la situazione. Seguendo le procedure consigliate in questo articolo è possibile risolvere i problemi di prestazioni e ridurre la frustrazione.
  
**Fattori principali che influiscono sulle prestazioni della rete**

![Fattori relativi alle prestazioni di rete](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)
  
 **Larghezza di banda e latenza** Le due misure più importanti delle prestazioni di rete sono larghezza di banda e latenza: 
  
- La larghezza di banda è la velocità effettiva misurata in bit al secondo. Più grande è meglio. La larghezza di banda è simile a un canale d'acqua. Più grande è il pip, maggiore è il numero di acqua che è possibile "inserire".

- La latenza è il tempo necessario per ottenere il contenuto da un server o un servizio al dispositivo ed è misurata in millisecondi. Più veloce è meglio. La latenza può essere causata da diversi fattori, tra cui larghezza di banda ridotta, connessione sparse o tempo di trasmissione.

 **Problemi comuni** Oltre alla larghezza di banda e alla latenza, altri problemi hanno un impatto sulle prestazioni della rete e spesso sono imprevedibili. Le prestazioni di rete possono variare in base all'ora del giorno o alla posizione fisica. La rete può diventare intasata quando si verificano determinati eventi che impennano l'uso di Internet, ad esempio una calamità naturale o un evento pubblico importante. Le dimensioni e la complessità della pagina caricata e il numero e le dimensioni dei file trasferiti hanno un impatto diretto sulle prestazioni. Una connessione WiFi può peggiorare temporaneamente: ad esempio, puoi eseguire il polling di una grande riunione di conferenze di migliaia richiedendo a tutti di tingere contemporaneamente. 
  
 **Considerazioni per una rete satellite** Una rete satellite è utile quando non è possibile utilizzare una rete locale, ad esempio il paese di ritorno, una nave da spedizione o un'area scientifica remota. Queste reti si basano su satelliti posizionati in un orbit geosynchronous a 22.000 miglia sopra l'equatore. Tuttavia, una trasmissione viaggia effettivamente per circa 90.000 miglia e quindi una rete satellite ha una latenza più lenta (500 ms o più) rispetto a una rete magnetica (da 20 a 50 ms). In condizioni ottimali, potresti non notare questa latenza, ma per scaricare file di grandi dimensioni, streaming video e giochi, probabilmente lo sarà. Un altro problema è la "dissolvenza della pioggia" in cui il meteo intenso, come tempeste di temporali e tempeste di temporali, può interrompere temporaneamente la trasmissione satellitare.
  
## <a name="are-you-sure-its-the-network"></a>Sei sicuro che sia la rete?

Ogni volta che si verificano problemi di prestazioni, assicurati innanzitutto che il dispositivo non sia la causa principale del problema. Esistono due operazioni che è possibile eseguire per migliorare in modo significativo:
  
- Verificare che il dispositivo sia in esecuzione e che non vi sia malware nel computer.

- Se possibile, acquistare più memoria. L'aggiunta di memoria è il modo più semplice e spesso più efficace per migliorare le prestazioni del dispositivo. È particolarmente utile quando si lavora con file e video di grandi dimensioni.

Per altre informazioni, vedi Prestazioni e manutenzione [di Windows e](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) Suggerimenti per migliorare le prestazioni del PC in Windows [10.](https://support.microsoft.com/en-za/help/4002019/windows-10-improve-pc-performance)

## <a name="best-practices-for-using-your-browser"></a>Procedure consigliate per l'uso del browser

Il browser è il gateway di Office 365, quindi può avere un impatto sulle prestazioni, in particolare con il tempo necessario per caricare una pagina e la frequenza di round trip al servizio Office 365.
  
 **Browser in generale**
  
Ecco alcuni suggerimenti per i browser in generale:
  
- Disabilitare i componenti aggiuntivi del browser che potrebbero influire sulle prestazioni o che non sono effettivamente necessari.

- Aumentare le dimensioni della cache per i file temporanei Internet.

- Dopo aver eseguito l'accesso al tuo account aziendale o dell'istituto di istruzione, mantieni aperta la finestra del browser per tutta la giornata. Puoi aprire altre schede e finestre senza accedere di nuovo. Se devi accedere a un altro account, usa Esplorazione privata. 

- Dopo aver scaricato e aperto ogni pagina, tienile aperte usando le schede. È facile spostarsi tra le schede e usare la pagina più avanti nella giornata. Aggiornare una pagina solo se sono necessari i dati più recenti in tale pagina.

- Se l'apertura di una pagina sta prendendo troppo tempo, interrompere il download della pagina (premere ESC) e quindi aggiornare la pagina (premere F5). 

-  Quando possibile, ridurre i round trip a Office 365. Ad esempio, anziché scorrere elenchi o raccolte, utilizzare la ricerca per individuare i file in una raccolta di grandi dimensioni e filtrare in un elenco per ottenere direttamente i risultati desiderati. In caso contrario, creare visualizzazioni che riducono al minimo i tempi di caricamento delle pagine. Per ulteriori informazioni, vedere [Gestire elenchi e raccolte di grandi dimensioni in Office 365.](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES)

- Se le prestazioni video sono scarse, potresti essere in grado di scaricare il video e guardarlo sul dispositivo. È possibile che sia disponibile un collegamento per il download oppure che sia possibile fare clic con il pulsante destro del mouse sul collegamento video e scegliere **Salva destinazione con nome.**

 **Specifico del browser**
  
Ecco alcuni suggerimenti per il browser specifico:
  
- **Internet Explorer** Eseguire l'aggiornamento a Internet Explorer versione 11 o successiva per miglioramenti sostanziali delle prestazioni rispetto alle versioni precedenti. Per altre informazioni, vedi la [guida alla risoluzione dei problemi per Internet Explorer.](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365)

- **FireFox** Per ulteriori informazioni, vedere [Firefox è lento o smette di funzionare.](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging)

- **Safari** Per ulteriori informazioni, vedere [Apple - Safari.](https://www.apple.com/safari/)

- **Chrome** Per ulteriori informazioni, vedere la [Guida di Chrome.](https://support.google.com/chrome/?hl=en)
  
## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Procedure consigliate per l'utilizzo di Outlook e Outlook Web App

Leggere, scrivere e organizzare la posta elettronica è una parte importante della giornata di tutti. Sia Outlook che Outlook Web App (OWA) offrono supporto offline. L'uso di un'app di posta elettronica sullo smartphone è un'altra alternativa utile. Utilizzare le opzioni seguenti più adatte alle proprie esigenze:
  
- Eseguire l'aggiornamento all'ultima versione di Outlook per miglioramenti sostanziali delle prestazioni rispetto alle versioni precedenti. 

-  Outlook Web App consente di creare messaggi offline, contatti ed eventi del calendario che vengono caricati quando OWA è in grado di connettersi a Office 365. Per ulteriori informazioni sull'impostazione e l'utilizzo OWA in modalità offline, vedere [Utilizzo di Outlook Web App offline.](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36)

- Outlook consente di lavorare in modalità cache, in cui si connette automaticamente quando possibile. È possibile fare in modo che Outlook scarii l'intera cassetta postale o solo una parte di essa. Per ulteriori informazioni, vedere [Attivare la modalità cache e](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) Lavorare offline in [Outlook.](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633)

- Outlook offre anche una modalità offline. Per usare questo metodo, devi prima configurare la modalità cache in modo che le informazioni del tuo account vengono copiate nel computer. In modalità offline, Outlook tenterà di connettersi utilizzando le impostazioni di invio e ricezione o quando viene impostato manualmente per il funzionamento online. Per ulteriori informazioni, vedere Lavorare [offline](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282)per evitare costi di connessione dati, Modificare le impostazioni di invio e ricezione quando si lavora [offline](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)e Passare da [offline a online.](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9)

- Se si dispone di uno smartphone, è possibile utilizzarlo per la ricerca della posta elettronica e del calendario sulla rete del gestore telefonico.

> [!NOTE]
> Ecco alcune indicazioni su quando usare Outlook o OWA. Se lo spazio su disco non è un problema nel dispositivo, Outlook dispone di un set completo di funzionalità e potrebbe funzionare al meglio. Se lo spazio su disco è un problema nel dispositivo, valuta la possibilità di usare un OWA con un sottoinsieme di funzionalità, ma che funziona meglio anche in una situazione online. Naturalmente, è possibile utilizzarli perché funzionano bene insieme.
  
## <a name="best-practices-for-using-onedrive-for-business"></a>Procedure consigliate per l'utilizzo di OneDrive for Business

OneDrive for Business è progettato da zero per lavorare con i file online e offline. Dopo la configurazione, la sincronizzazione delle modifiche viene eseguita automaticamente e in modo affidabile ovunque e ogni volta che vengono apportate. Se la rete è lenta, è possibile utilizzare la versione offline dei file.
  
L'app di sincronizzazione di OneDrive for Business include un abbonamento a SharePoint Online e Office 365 Business oppure è possibile [scaricare](https://support.microsoft.com/kb/2903984) l'app di sincronizzazione di OneDrive for Business gratuitamente. Questa app è anche più veloce rispetto **all'uso dei comandi Apri in Esplora** risorse o **Carica.** Per ulteriori informazioni, vedere Configurare il computer per sincronizzare i file di [OneDrive for Business in Office 365.](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16)
  
Ecco alcune indicazioni aggiuntive per l'uso dell'app di sincronizzazione di OneDrive for Business:
  
- Se stai sincronizzando una raccolta di grandi dimensioni per la prima volta, avvia la sincronizzazione in orari non lavorativi, ad esempio durante la notte.

- È possibile utilizzare la funzionalità [Interrompi sincronizzazione di una raccolta con l'app OneDrive for Business](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) per interrompere temporaneamente la sincronizzazione degli aggiornamenti. Utilizzare tuttavia questa funzionalità per brevi periodi, ad esempio alcune ore alla volta, per evitare l'accodamento di un numero elevato di aggiornamenti e per ridurre al minimo il rischio di conflitti di unione se più persone lavorano sullo stesso documento.
  
## <a name="best-practices-for-using-onenote"></a>Procedure consigliate per l'utilizzo di OneNote

Ogni sito del team di SharePoint dispone di un blocco appunti di OneNote incorporato ed è possibile crearne uno personalizzato facilmente. OneNote è un ottimo modo per raccogliere informazioni aggiornate che sono necessarie ogni giorno per eseguire le attività. Ad esempio, molti team usano OneNote come punto di raccolta per riunioni settimanali, note di progetto, idee, piani e relazioni sullo stato. Puoi organizzare in modo ordinato queste diverse informazioni usando pagine, sezioni e schede.
  
Il vantaggio di OneNote è che è possibile accedere al contenuto praticamente da qualsiasi dispositivo, da un desktop, un portatile, un tablet o uno smartphone. E non è necessario preoccuparsi di salvare o sincronizzare perché OneNote lo fa per te.
  
Per ulteriori informazioni, vedere [Microsoft OneNote.](https://office.microsoft.com/onenote)

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Procedure consigliate per l'utilizzo di Skype for Business e Lync Online

Di seguito sono riportate le linee guida generali per l'utilizzo di Skype for Business o Lync Online quando la rete è lenta:

- Utilizzare la messaggistica istantanea ogni volta che è possibile perché funziona bene su una rete lenta.

- Evitare di effettuare chiamate telefoniche tramite una rete privata virtuale (VPN) o connessioni RAS (Remote Access Service).

- Assicurati che il dispositivo audio sia approvato. Per ulteriori informazioni, vedere [Telefoni e dispositivi qualificati per Microsoft Lync.](https://docs.microsoft.com/skypeforbusiness/lync-cert/ip-phones)

- Quando si utilizza PowerPoint in una presentazione online, ridurre le dimensioni e la complessità delle diapositive. Per ulteriori informazioni, vedere [Suggerimenti per migliorare le prestazioni della presentazione.](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949)

- Le prestazioni video dipendono molto dalle prestazioni di rete. Evitare di usare video se la rete è lenta.

Per ulteriori informazioni, vedere Qualità audio o [video scadente in Lync Online](https://support.microsoft.com/kb/2386655)o come risolvere i problemi di connessione in Skype for [Business.](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771)
  
## <a name="best-practices-for-using-sharepoint-lists"></a>Procedure consigliate per l'utilizzo degli elenchi di SharePoint

Lavorare con i dati degli elenchi offline per eseguire lo "scrub", analizzare o segnalare i dati è un ottimo modo per ridurre al minimo l'impatto di una rete lenta. È possibile leggere e scrivere la maggior parte degli elenchi di Microsoft Access 2019 e Microsoft Access 2016 collegandoli ad essi. È inoltre possibile esportare un elenco in una tabella di Excel, in modo da creare una connessione dati unidiredire utente tra la tabella di Excel e l'elenco. Informazioni su come [lavorare offline con tabelle collegate a elenchi di SharePoint.](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e)
  
Per ulteriori informazioni, vedere la sezione "Ulteriori informazioni sulla gestione di elenchi di grandi dimensioni" in Gestire elenchi e raccolte di grandi dimensioni [in Office 365.](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784)
  
## <a name="best-practices-for-customizing-web-pages"></a>Procedure consigliate per la personalizzazione delle pagine Web

Quando si personalizza una pagina Web, è possibile che si possano inavvertitamente causare prestazioni scarse con la pagina. Un certo numero di fattori può avere un impatto, ad esempio la complessità e le dimensioni della pagina, il numero di web part aggiunte, il numero di elementi di elenchi o di raccolta inizialmente visualizzati e il modo in cui codificare la pagina.
  
Per ulteriori informazioni, vedere [Ottimizzare le prestazioni di SharePoint Online.](tune-sharepoint-online-performance.md)
  
## <a name="best-practices-for-using-project-online"></a>Procedure consigliate per l'utilizzo di Project Online

Le linee guida seguenti consentono di migliorare le prestazioni di rete.
  
- Project Online e SharePoint Online richiedono la sincronizzazione, che può richiedere molto tempo. Se il fatturato dei team di progetto è ridotto, disabilitare Sincronizzazione siti di progetto per migliorare le prestazioni di pubblicazione e pagine dettagli progetto. Limitare la sincronizzazione di Active Directory ai gruppi di risorse che effettivamente devono utilizzare il sistema e monitorare eventuali problemi di autorizzazione dopo la sincronizzazione di gruppi di grandi dimensioni.

- Se l'organizzazione utilizza siti di progetto, crearli su richiesta anziché automaticamente. Ciò velocizza la prima esperienza di pubblicazione ed evita la creazione di siti e contenuto non necessari.

- Le pagine dettagli progetto (PDP) possono attivare un ricalcolo dell'intero progetto e avviare le azioni del flusso di lavoro, entrambe operazioni che richiedono un utilizzo intensivo delle prestazioni. Per evitare di attivare due processi di aggiornamento contemporaneamente nello stesso PDP, evitare di aggiornare i campi del calendario (Data di inizio, Data di fine, Data stato e Data corrente) e i campi non programmati (nome, descrizione e proprietario del progetto).

- Ridurre il numero di Web part e personalizzati visualizzati in ogni PDP. Creare un PDP dedicato con gli unici campi che richiedono l'aggiornamento per migliorare il carico e risparmiare tempo.

- Quando si utilizza OData per la creazione di report, limitare la quantità di dati su cui si esegue una query in fase di esecuzione utilizzando il filtro sul lato server.

Per ulteriori informazioni, vedere [Ottimizzare le prestazioni di Project Online.](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)
  
## <a name="whats-the-best-way-to-report-problems"></a>Qual è il modo migliore per segnalare i problemi?

Microsoft migliora continuamente le prestazioni complessive di Office 365 monitorando la rete, misurando larghezza di banda e latenza, migliorando i tempi di caricamento delle pagine, riducendo l'I/O su disco, riprogettare le pagine per usare la strategia di download minima, aggiungere hardware ai data center e aggiungere altri data center. Per ulteriori informazioni sul controllo dello stato corrente e sulla segnalazione dei problemi, vedere Come verificare l'integrità dei servizi di [Office 365.](view-service-health.md)
  
## <a name="see-also"></a>Vedere anche

[Pianificazione della rete e ottimizzazione delle prestazioni per Office 365](network-planning-and-performance.md)
  
[Principi della connettività di rete di Office 365](microsoft-365-network-connectivity-principles.md)
  
[Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Domande frequenti sugli endpoint di Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
 
