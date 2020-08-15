---
title: Procedure consigliate per l'utilizzo di Office 365 in una rete lenta
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
description: In questo articolo vengono illustrate le procedure consigliate che è possibile adottare per l'utilizzo di Office 365 in una rete lenta.
ms.openlocfilehash: a0a15191fa0240f24cecc5e595de9a259cacc9f9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691364"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Procedure consigliate per l'utilizzo di Office 365 in una rete lenta

Non sarebbe bello se la connessione Internet fosse sempre veloce e mai inattiva? Forse quel giorno verrà. Nel frattempo, tuttavia, esistono operazioni pratiche che è possibile eseguire per aggirare una rete esitante e continuare a svolgere il proprio lavoro quotidiano. Anche se Office 365 è un servizio basato su cloud, fornisce anche molti modi per gestire i contenuti in modalità non in linea e mantenere sincronizzate le modifiche senza problemi. Inoltre, a volte è più efficiente lavorare con il contenuto offline solo perché le applicazioni vengono eseguite più velocemente e l'interfaccia utente è più reattiva. Il punto è questo: Office 365 offre il meglio di entrambi i mondi. Ecco come approfittarne. 
  
> [!TIP]
> Vuoi vedere come lenta (o veloce) la connessione di rete è? Provare il [ OOKLA Speed Test ](https://www.speedtest.net/) o l' [app Speed Test di rete](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70). 

## <a name="why-is-my-network-so-slow"></a>Perché la rete è così lenta?

Anche se non si ha il controllo sulle prestazioni di rete, è utile capire cosa succede dietro le quinte. La connessione Internet è estremamente complessa, ma esistono alcuni concetti che consentono di comprendere meglio la situazione. Seguire le procedure consigliate in questo articolo consente di risolvere i problemi di prestazioni della soluzione e ridurre la frustrazione.
  
**Fattori principali che influiscono sulle prestazioni della rete**

![Fattori relativi alle prestazioni di rete](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)
  
 **Larghezza di banda e latenza** Le due misure più importanti relative alle prestazioni di rete sono la larghezza di banda e la latenza: 
  
- La larghezza di banda è il tasso di velocità effettiva misurato in bit al secondo. Maggiore è la migliore. La larghezza di banda è come un tubo di acqua. Maggiore è il tubo, maggiore è l'acqua che è possibile "inserire".

- Latenza è il tempo necessario per il contenuto da un server o da un servizio al dispositivo e misurato in millisecondi. La velocità è migliore. La latenza può essere causata da una serie di fattori, tra cui la larghezza di banda bassa, una connessione di tipo sparse o la trasmissione.

 **Problemi comuni** Oltre alla larghezza di banda e alla latenza, altri problemi hanno un impatto sulle prestazioni della rete e spesso sono imprevedibili. Le prestazioni di rete possono variare in base all'ora del giorno o alla posizione fisica. La rete può intasarsi quando si verificano determinati eventi che determinano l'utilizzo di Internet, ad esempio un'emergenza naturale o un evento pubblico importante. Le dimensioni e la complessità della pagina caricata e il numero e le dimensioni dei file trasferiti hanno un impatto diretto sulle prestazioni. Una connessione Wi-Fi può temporaneamente peggiorare: ad esempio, è possibile eseguire il polling di una riunione di riunioni di grandi dimensioni richiedendo tutti i Tweet contemporaneamente. 
  
 **Considerazioni relative a una rete satellitare** Una rete satellitare è utile quando non è possibile una rete terrestre, ad esempio il paese di origine, una nave da crociera o un'area scientifica remota. Queste reti si basano su satelliti posizionati in un'orbita geostazionaria 22.000 miglia sopra l'equatore. Tuttavia, una trasmissione effettivamente percorre circa 90.000 miglia e quindi una rete satellitare ha una latenza più lenta (500 ms o più) di una rete terrestre (da 20 a 50ms). In condizioni ottimali, non è possibile notare questa latenza, ma per scaricare file di grandi dimensioni, video in streaming e giochi, è probabile che lo sarà. Un altro problema è "pioggia sbiadita", in cui il tempo atmosferico, come temporali e bufere di neve, può interrompere temporaneamente la trasmissione satellitare.
  
## <a name="are-you-sure-its-the-network"></a>Sei sicuro che sia la rete?

Ogni volta che si verificano problemi di prestazioni, verificare innanzitutto che il dispositivo non sia la causa principale del problema. È possibile eseguire due operazioni che possono apportare un notevole miglioramento:
  
- Verificare che il dispositivo sia in esecuzione correttamente e che non vi siano malware nel computer in uso.

- Se possibile, acquistare più memoria. L'aggiunta di memoria è il modo più semplice e spesso più efficace per migliorare le prestazioni del dispositivo. È particolarmente utile quando si utilizzano file e video di grandi dimensioni.

Per ulteriori informazioni, vedere [ prestazioni e manutenzione di Windows ](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) e [Suggerimenti per migliorare le prestazioni del PC in Windows 10](https://support.microsoft.com/en-za/help/4002019/windows-10-improve-pc-performance).

## <a name="best-practices-for-using-your-browser"></a>Procedure consigliate per l'utilizzo del browser

Il browser è il gateway per Office 365, in modo che possa avere un impatto sulle prestazioni, soprattutto con il tempo necessario per caricare una pagina e la frequenza di andata e ritorno al servizio Office 365.
  
 **Browser in generale**
  
Di seguito sono riportate alcune proposte per i browser in generale:
  
- Disabilitare i componenti aggiuntivi del browser che potrebbero influire sulle prestazioni o che non sono necessari.

- Aumentare le dimensioni della cache per i file temporanei di Internet.

- Dopo aver effettuato l'accesso all'account aziendale o dell'Istituto di istruzione, tenere aperta la finestra del browser per tutto il giorno. È possibile aprire altre schede e finestre senza accedere di nuovo. Se è necessario accedere a un altro account, utilizzare l'esplorazione privata. 

- Dopo aver scaricato e aperto ogni pagina, aprirla utilizzando tabulazioni. È facile spostarsi tra le schede e usare la pagina nel corso della giornata. Consente di aggiornare una pagina solo se sono necessari i dati più recenti in tale pagina.

- Se una pagina richiede troppo tempo per l'apertura, interrompere il download della pagina (premere ESC) e quindi aggiornare la pagina (premere F5). 

-  Quando possibile, ridurre i viaggi di andata e ritorno a Office 365. Ad esempio, anziché eseguire il paging tramite elenchi o raccolte, utilizzare Search per individuare i file in una raccolta di grandi dimensioni e filtrare i dati in un elenco per ottenere direttamente i risultati desiderati. In alternativa, creare visualizzazioni che riducono al minimo il tempo di caricamento delle pagine. Per ulteriori informazioni, vedere [gestire elenchi e raccolte di grandi dimensioni in Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES).

- Se le prestazioni video sono scarse, potrebbe essere possibile scaricare il video e guardarlo sul dispositivo. Potrebbe essere disponibile un collegamento per il download oppure è possibile fare clic con il pulsante destro del mouse sul collegamento video e scegliere **Salva oggetto con nome**.

 **Specifico del browser**
  
Di seguito sono riportate alcune proposte per il browser specifico:
  
- **Internet Explorer** Eseguire l'aggiornamento a Internet Explorer versione 11 o successive per migliorare le prestazioni sostanziali rispetto alle versioni precedenti. Per ulteriori informazioni, vedere [Guida alla risoluzione dei problemi per Internet Explorer](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365).

- **Firefox** Per ulteriori informazioni, vedere [Firefox è lento o smette di funzionare](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging).

- **Safari** Per ulteriori informazioni, vedere [Apple-Safari](https://www.apple.com/safari/).

- **Chrome** Per ulteriori informazioni, vedere [Guida di Chrome](https://support.google.com/chrome/?hl=en).
  
## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Procedure consigliate per l'utilizzo di Outlook e Outlook Web App

La lettura, la scrittura e l'organizzazione della posta elettronica è una parte importante della giornata di tutti. Outlook e Outlook Web App (OWA) offrono supporto offline. L'utilizzo di un'app di posta elettronica nello Smart Phone è un'altra alternativa utile. Utilizzare le opzioni seguenti che meglio si adattano alle proprie esigenze:
  
- Eseguire l'aggiornamento alla versione più recente di Outlook per migliorare le prestazioni sostanziali rispetto alle versioni precedenti. 

-  Outlook Web App consente di creare i messaggi, i contatti e gli eventi del calendario non in linea caricati quando OWA è in grado di connettersi a Office 365. Per ulteriori informazioni sulla configurazione e l'utilizzo di OWA in modalità offline, vedere [utilizzo di Outlook Web App offline](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36).

- Outlook consente di lavorare in modalità cache, in cui si connette automaticamente quando possibile. È possibile scaricare Outlook per l'intera cassetta postale o solo per una parte di esso. Per ulteriori informazioni, vedere [abilitare la modalità cache di Exchange](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) e [lavorare offline in Outlook](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

- Outlook offre anche una modalità offline. Per utilizzare questa impostazione, è necessario innanzitutto impostare la modalità cache in modo che le informazioni dell'account vengano copiate nel computer. In modalità offline, Outlook tenterà di connettersi utilizzando le impostazioni di invio e ricezione oppure quando viene impostato manualmente per l'utilizzo online. Per ulteriori informazioni, vedere [work offline per evitare addebiti per la connessione dati](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282), [modificare le impostazioni di invio e ricezione quando si lavora offline](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)e [passare dal lavoro offline a online](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9).

- Se si dispone di uno Smart Phone, è possibile utilizzarlo per la valutazione della posta elettronica e del calendario sulla rete del gestore del telefono.

> [!NOTE]
> Di seguito sono riportate alcune indicazioni su quando utilizzare Outlook o OWA. Se lo spazio su disco non è un problema sul dispositivo, Outlook ha un set completo di funzionalità e potrebbe funzionare al meglio per te. Se lo spazio su disco è un problema del dispositivo, è consigliabile utilizzare OWA con un sottoinsieme di funzionalità, ma funziona anche meglio in una situazione online. Naturalmente, è possibile utilizzare entrambi perché funzionano bene insieme.
  
## <a name="best-practices-for-using-onedrive-for-business"></a>Procedure consigliate per l'utilizzo di OneDrive for business

OneDrive for business è stato creato fin dall'alto per lavorare con i file online e offline. Dopo averla configurata, la sincronizzazione delle modifiche avviene in modo automatico e affidabile ovunque e in qualsiasi momento. Se la rete è lenta, è possibile utilizzare la versione offline dei file.
  
L'app di sincronizzazione di OneDrive for business è disponibile con un abbonamento a SharePoint Online e Office 365 business oppure è possibile [scaricare](https://support.microsoft.com/kb/2903984) gratuitamente l'app OneDrive for business Sync. Questa app è anche più veloce rispetto all'utilizzo dei comandi **Apri in Esplora risorse** o **caricamento** . Per ulteriori informazioni, vedere [configurare il computer per sincronizzare i file di OneDrive for business in Office 365](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16).
  
Di seguito sono riportate alcune indicazioni aggiuntive per l'utilizzo dell'app di sincronizzazione di OneDrive for business:
  
- Se si sta sincronizzando una raccolta di grandi dimensioni per la prima volta, avviare la sincronizzazione durante le ore di disattivazione, ad esempio durante la notte.

- È possibile utilizzare la funzionalità [Interrompi sincronizzazione di una raccolta con la caratteristica app di OneDrive for business](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) per interrompere temporaneamente la sincronizzazione degli aggiornamenti. Tuttavia, utilizzare questa funzionalità per brevi periodi, ad esempio alcune ore per volta, per evitare l'accodamento di un numero elevato di aggiornamenti e per ridurre al minimo il rischio di conflitti di Unione se diverse persone lavorano nello stesso documento.
  
## <a name="best-practices-for-using-onenote"></a>Procedure consigliate per l'utilizzo di OneNote

Ogni sito del team di SharePoint dispone di un blocco appunti di OneNote incorporato e può essere creato facilmente. OneNote è un ottimo modo per raccogliere le informazioni tempestive necessarie ogni giorno per ottenere le attività eseguite. Ad esempio, molti team utilizzano OneNote come punto di raccolta per riunioni settimanali, note di progetto, idee, piani e report sullo stato. È possibile organizzare ordinatamente queste informazioni disparate utilizzando pagine, sezioni e schede.
  
La bellezza di OneNote consiste nel fatto che è possibile accedere al contenuto da qualsiasi dispositivo, sia che si tratti di un desktop, di un laptop, di un tablet o di uno Smart Phone. Non è necessario preoccuparsi del salvataggio o della sincronizzazione perché OneNote lo fa per te.
  
Per ulteriori informazioni, vedere [Microsoft OneNote](https://office.microsoft.com/onenote).

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Procedure consigliate per l'utilizzo di Skype for business e Lync Online

Di seguito sono riportate le linee guida generali per l'utilizzo di Skype for business o Lync Online quando la rete è lenta:

- Utilizzare la messaggistica istantanea ogni volta che è possibile perché funziona bene in una rete lenta.

- Evitare di effettuare chiamate telefoniche su una rete privata virtuale (VPN) o su una connessione a un servizio di accesso remoto.

- Verificare che il dispositivo audio sia approvato. Per ulteriori informazioni, vedere [telefoni e dispositivi qualificati per Microsoft Lync](https://docs.microsoft.com/skypeforbusiness/lync-cert/ip-phones).

- Quando si utilizza PowerPoint in una presentazione online, ridurre le dimensioni e la complessità delle diapositive. Per ulteriori informazioni, vedere [Suggerimenti per migliorare le prestazioni della presentazione](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949).

- Le prestazioni video dipendono molto dalle prestazioni di rete. Evitare di utilizzare video se la rete è lenta.

Per ulteriori informazioni, vedere [qualità audio o video scadente in Lync Online](https://support.microsoft.com/kb/2386655)o [risoluzione dei problemi di connessione in Skype for business](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771).
  
## <a name="best-practices-for-using-sharepoint-lists"></a>Procedure consigliate per l'utilizzo di elenchi di SharePoint

L'utilizzo di dati di elenco non in linea su "scrub", Analyze o report è un ottimo modo per ridurre al minimo l'impatto di una rete lenta. È possibile leggere e scrivere la maggior parte degli elenchi di Microsoft Access 2019 e Microsoft Access 2016 collegandosi a essi. È inoltre possibile esportare un elenco in una tabella di Excel, che consente di creare una connessione dati unidirezionale tra la tabella di Excel e l'elenco. Informazioni su come [lavorare in modalità non in linea con le tabelle collegate agli elenchi di SharePoint](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e).
  
Per ulteriori informazioni, vedere la sezione "ulteriori informazioni sulla gestione di elenchi di grandi dimensioni" in [gestire elenchi e raccolte di grandi dimensioni in Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784).
  
## <a name="best-practices-for-customizing-web-pages"></a>Procedure consigliate per la personalizzazione delle pagine Web

Quando si personalizza una pagina Web, è possibile che si verifichino inavvertitamente prestazioni insufficienti sulla pagina. Un certo numero di fattori può avere un impatto, ad esempio la complessità e le dimensioni della pagina, quante Web part vengono aggiunte, quanti elementi di elenco o di raccolta vengono inizialmente visualizzati e il modo in cui la pagina viene codificata.
  
Per ulteriori informazioni, vedere [ottimizzare le prestazioni di SharePoint Online](tune-sharepoint-online-performance.md).
  
## <a name="best-practices-for-using-project-online"></a>Procedure consigliate per l'utilizzo di Project online

Le linee guida seguenti consentono di migliorare le prestazioni della rete.
  
- Project online e SharePoint Online richiedono la sincronizzazione, che può richiedere molto tempo. Se i team del progetto hanno un turnover basso, disabilitare la sincronizzazione dei siti di progetto per migliorare la pubblicazione del progetto e le prestazioni delle pagine dei dettagli del progetto. Limitare la sincronizzazione di Active Directory ai gruppi di risorse che effettivamente devono utilizzare il sistema e monitorare i possibili problemi di autorizzazione dopo la sincronizzazione di gruppi di grandi dimensioni.

- Se nell'organizzazione vengono utilizzati siti di progetto, crearli su richiesta anziché automaticamente. Questo velocizza la prima esperienza di pubblicazione ed evita di creare siti e contenuti non necessari.

- Le pagine dei dettagli del progetto (PDP) possono attivare un ricalcolo dell'intero progetto e avviare azioni del flusso di lavoro, che possono essere entrambe operazioni con utilizzo intensivo delle prestazioni. Per evitare di attivare contemporaneamente due processi di aggiornamento nello stesso PDP, evitare di aggiornare i campi del calendario (data di inizio, data di fine, data stato e data corrente) e i campi non pianificati (nome del progetto, descrizione e proprietario).

- Ridurre il numero di Web part e dei campi personalizzati visualizzati su ogni PDP. Creare un PDP dedicato con gli unici campi che richiedono l'aggiornamento per migliorare il carico e risparmiare tempo.

- Quando si utilizza OData per la creazione di report, limitare la quantità di dati che si esegue una query in fase di esecuzione utilizzando il filtro sul server.

Per ulteriori informazioni, vedere [Tune Project online performance](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c).
  
## <a name="whats-the-best-way-to-report-problems"></a>Qual è il modo migliore per segnalare i problemi?

Microsoft migliora continuamente le prestazioni complessive di Office 365 monitorando la rete, misurando la larghezza di banda e la latenza, migliorando il tempo di caricamento delle pagine, riducendo le operazioni di I/O su disco, riprogettando le pagina per l'utilizzo di una strategia di download minima, aggiungendo hardware ai Data Center e aggiungendo Per ulteriori informazioni su come controllare lo stato corrente e i problemi relativi alle relazioni, vedere [How to Check Office 365 Service Health](view-service-health.md).
  
## <a name="see-also"></a>Vedere anche

[Pianificazione della rete e ottimizzazione delle prestazioni per Office 365](network-planning-and-performance.md)
  
[Principi della connettività di rete di Office 365](microsoft-365-network-connectivity-principles.md)
  
[Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Domande frequenti sugli endpoint di Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
 
