---
title: Piano di risoluzione dei problemi relativi alle prestazioni per Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 5/10/2019
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
ms.assetid: e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c
ms.collection:
- M365-security-compliance
- Ent_O365
description: In questo articolo è possibile risolvere i problemi relativi alle prestazioni di Office 365 e risolvere anche alcuni dei problemi più comuni.
ms.openlocfilehash: 9287e2649a2eb126d723e7436a9178be93087bc0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691232"
---
# <a name="performance-troubleshooting-plan-for-office-365"></a>Piano di risoluzione dei problemi relativi alle prestazioni per Office 365

È necessario conoscere i passaggi da eseguire per identificare e correggere i ritardi, appendere e rallentare le prestazioni tra SharePoint Online, OneDrive for business, Exchange Online o Skype for business online e il computer client? Prima di chiamare il supporto, questo articolo consente di risolvere i problemi relativi alle prestazioni di Office 365 e persino di risolvere alcuni dei problemi più comuni.
  
Questo articolo è in realtà un piano di azione di esempio che è possibile utilizzare per acquisire dati importanti sul problema delle prestazioni in corso. In questo articolo sono inclusi anche alcuni problemi principali.

Se si è nuovi per le prestazioni di rete e si vuole fare un piano a lungo termine per monitorare le prestazioni tra i computer client e Office 365, esaminare l' [ottimizzazione delle prestazioni di office 365 e la risoluzione dei problemi-admin e IT Pro](performance-tuning-using-baselines-and-history.md).
  
## <a name="sample-performance-troubleshooting-action-plan"></a>Piano d'azione per la risoluzione dei problemi di prestazioni di esempio

Questo piano d'azione contiene due parti; una fase di preparazione e una fase di registrazione. Se si dispone di un problema di prestazioni in questo momento ed è necessario eseguire la raccolta dei dati, è possibile iniziare a usare questo piano subito.
  
### <a name="prepare-the-client-computer"></a>Preparare il computer client
  
- Trovare un computer client in grado di riprodurre il problema delle prestazioni. Questo computer verrà utilizzato nel corso della risoluzione dei problemi.
- Annotare i passaggi che causano il verificarsi del problema delle prestazioni in modo da essere pronti quando arriva il momento di testare.
- Installare gli strumenti per la raccolta e la registrazione delle informazioni:
  - Installare [Netmon 3,4](https://www.microsoft.com/download/details.aspx?id=4865) (o utilizzare uno strumento di traccia di rete equivalente).
  - Installare la versione gratuita di base di [HttpWatch](https://www.httpwatch.com/download/) (o utilizzare uno strumento di traccia di rete equivalente).
  - Utilizzare un registratore schermo o eseguire la procedura di registrazione dei passaggi (PSR.exe) fornita con Windows Vista e versioni successive, per tenere traccia delle operazioni eseguite durante il testing.

### <a name="log-the-performance-issue"></a>Registrare il problema delle prestazioni
  
- Chiudere tutti i browser Internet estranei.
- Avviare la procedura di registrazione o un altro registratore di schermata.
- Avviare l'acquisizione di Netmon (o lo strumento di traccia di rete).
- Cancellare la cache DNS sul computer client dalla riga di comando digitando ipconfig/flushdns.
- Avviare una nuova sessione del browser e attivare HTTPWatch.
- Facoltativo: se si sta testando Exchange Online, eseguire Exchange client Performance Analyzer Tool dalla console di amministrazione di Office 365.
- Riprodurre i passaggi esatti che causano il problema delle prestazioni.
- Interrompere la traccia di NetMon o di altro strumento.
- Nella riga di comando eseguire una route di traccia per l'abbonamento a Office 365 digitando il comando seguente e quindi premendo INVIO:

  ``` cmd
  tracert <subscriptionname>.onmicrosoft.com
  ```

- Interrompere la procedura di registrazione e salvare il video. Assicurarsi di includere la data e l'ora dell'acquisizione e se viene mostrata una prestazione positiva o negativa.
- Salvare i file di traccia. Anche in questo caso, assicurarsi di includere la data e l'ora dell'acquisizione e se viene mostrata una prestazione positiva o negativa.

Se non si ha familiarità con l'esecuzione degli strumenti citati in questo articolo, non si preoccupi perché vengono forniti i passaggi successivi. Se si è abituati a eseguire questo tipo di acquisizione di rete, è possibile passare a [come raccogliere le linee di base](performance-tuning-using-baselines-and-history.md#how-to-collect-baselines), in cui vengono descritti i filtri e la lettura dei log.
  
### <a name="flush-the-dns-cache-first"></a>Svuotare la cache DNS per primo

Perché? Scaricando la cache DNS vengono avviati i test con una tabulazione pulita. Deselezionando la cache, si sta reimpostando il contenuto del resolver DNS nelle voci più aggiornate. Tenere presente che un colore non rimuove le voci del file hosts. Se si utilizzano ampiamente le voci dei file HOST, è consigliabile copiare tali voci in un file in un'altra directory e quindi svuotare il file HOST.
  
#### <a name="flush-your-dns-resolver-cache"></a>Svuotare la cache del resolver DNS
  
1. Aprire il prompt dei comandi ( **iniziare** a \> **eseguire** \> **cmd** o **Key** \> **cmd**di Windows).
2. Digitare il comando seguente e premere INVIO:

    ``` cmd
    ipconfig /flushdns
    ```

## <a name="netmon"></a>Netmon

Microsoft ' s Network Monitoring Tool ([Netmon](https://www.microsoft.com/download/details.aspx?id=4865)) analizza i pacchetti, ovvero il traffico, che passa da un computer all'altra. Se si utilizza NetMon per tracciare il traffico con Office 365, è possibile acquisire, visualizzare e leggere le intestazioni dei pacchetti, identificare i dispositivi intervenuti, controllare le impostazioni importanti per l'hardware di rete, cercare i pacchetti eliminati e seguire il flusso di traffico tra i computer della rete aziendale e Office 365. Poiché il corpo effettivo del traffico è crittografato, ovvero (viaggia sulla porta 443 tramite SSL/TLS, non è possibile leggere i file inviati. Invece, si ottiene una traccia non filtrata del percorso che il pacchetto prende che può aiutare a rintracciare il comportamento del problema.
  
Assicurarsi di non applicare un filtro in questo momento. Eseguire invece i passaggi e illustrare il problema prima di interrompere la traccia e il salvataggio.
  
Dopo aver installato NetMon 3,4, aprire lo strumento e procedere come segue:
  
### <a name="take-a-netmon-trace-and-reproduce-the-issue"></a>Eseguire una traccia Netmon e riprodurre il problema
  
1. Avviare NetMon 3,4.
Nella pagina **iniziale** sono presenti tre riquadri: **acquisizioni recenti**, **selezionare reti**e **guida introduttiva a Microsoft Network Monitor 3,4. Avviso**. Il pannello Seleziona reti fornirà anche un elenco delle reti predefinite da cui è possibile acquisire. Verificare che le schede di rete siano selezionate qui.

2. Fare clic su **nuova acquisizione** nella parte superiore della pagina **iniziale** . Viene aggiunta una nuova scheda accanto alla scheda pagina **iniziale** denominata **Capture 1**.
![Interfaccia utente di NetMon con i nuovi pulsanti di acquisizione, avvio e arresto evidenziati.](../media/d4527d84-62ec-4301-82d5-e0166ff71f20.PNG)

3. Per eseguire un'acquisizione semplice, fare clic su **Avvia** sulla barra degli strumenti.

4. Riprodurre i passaggi che presentano un problema di prestazioni.

5. Fare clic su **Interrompi** \> **file** \> **Salva con nome**. Tenere presente la data e l'ora con il fuso orario e indicare se sono state apportate prestazioni negative o valide.

## <a name="httpwatch"></a>HTTPWatch

[HttpWatch](https://www.httpwatch.com/download/) viene caricato e un'edizione gratuita. La versione gratuita di base include tutto ciò che è necessario per questo test. HTTPWatch monitora il traffico di rete e il tempo di caricamento delle pagine direttamente dalla finestra del browser. HTTPWatch è un plug-in per Internet Explorer che descrive graficamente le prestazioni. L'analisi può essere salvata e visualizzata in HTTPWatch Studio.
  
> [!NOTE]
> Se si utilizza un altro browser, ad esempio Firefox, Google Chrome o se non è possibile installare HTTPWatch in Internet Explorer, aprire una nuova finestra del browser e premere F12 sulla tastiera. Verrà visualizzato lo strumento di sviluppo pop-up nella parte inferiore del browser. Se si utilizza Opera, premere CTRL + MAIUSC + I per Web Inspector, quindi fare clic sulla scheda **rete** e completare i test illustrati di seguito. Le informazioni saranno leggermente diverse, ma i tempi di caricamento verranno comunque visualizzati in millisecondi. > HTTPWatch è molto utile anche per i problemi relativi ai tempi di caricamento delle pagine di SharePoint Online.
  
### <a name="run-httpwatch-and-reproduce-the-issue"></a>Eseguire HTTPWatch e riprodurre il problema
  
HTTPWatch è un plug-in del browser, quindi esporre lo strumento nel browser è leggermente diverso per ogni versione di Internet Explorer. In genere, è possibile trovare HTTPWatch sotto la barra dei comandi nel browser Internet Explorer. Se il plug-in di HttpWatch non viene visualizzato nella finestra del browser, vedere la versione del browser facendo clic **Help** \> **su**guida o su versioni successive di Internet Explorer, fare clic sul simbolo dell'ingranaggio e **su Internet Explorer**. Per avviare la barra dei **comandi** , fare clic con il pulsante destro del mouse sulla barra dei menu in Internet Explorer e scegliere **barra comandi**.

In passato, HTTPWatch è stato associato sia ai comandi che alle barre di Explorer, quindi, una volta installato, se non si vede immediatamente l'icona (anche dopo il riavvio), controllare gli **strumenti**e le barre strumenti per l'icona. Tenere presente che le barre degli strumenti possono essere personalizzate e che è possibile aggiungervi le opzioni.

![Barra degli strumenti di comando di Internet Explorer con l'icona di HTTPWatch visualizzata.](../media/198590b0-d7b1-4bff-a6ad-e4ec3a1e83df.png)
  
1. Avviare HTTPWatch in una finestra del browser di Internet Explorer. Verrà visualizzato ancorato al browser nella parte inferiore della finestra. Fare clic su **registra**.

2. Riprodurre i passaggi esatti coinvolti nel problema delle prestazioni. Fare clic sul pulsante **Interrompi** in HttpWatch.

3. **Salvare** il HttpWatch o **inviare tramite posta elettronica**. Ricordarsi di assegnare un nome al file in modo che includa informazioni relative a data e ora e indicazione del fatto che l'orologio contiene una dimostrazione di prestazioni valide o negative.

![HTTPWatch che mostra la scheda Rete per il caricamento pagina della homepage di Office 365.](../media/021a2c64-d581-49fd-adf4-4c364f589d75.PNG)

Questo screenshot è della versione professionale di HTTPWatch. È possibile aprire le tracce eseguite nella versione di base in un computer con una versione professionale e leggerle. Informazioni aggiuntive possono essere rese disponibili dalla traccia tramite il metodo.

## <a name="problem-steps-recorder"></a>Record di passaggi del problema

La registrazione dei passaggi o PSR.exe consente di registrare i problemi che si verificano. Si tratta di uno strumento molto utile e molto semplice da eseguire.
  
### <a name="run-problem-steps-recorder-psrexe-to-record-your-work"></a>Eseguire la registrazione dei passaggi del problema (PSR.exe) per registrare il proprio lavoro
  
1. Utilizzare **Avvia** \> tipo di **esecuzione** \> **PSR.exe** \> **OK**oppure fare clic sul tipo di **chiave di Windows** \> **PSR.exe** \> e quindi premere INVIO.

2. Quando viene visualizzata la finestra di PSR.exe di piccole dimensioni, fare clic su **Avvia record** e riprodurre i passaggi che riproducono il problema delle prestazioni. È possibile aggiungere commenti in base alle esigenze, facendo clic su **Aggiungi commenti**.

3. Fare clic su **Interrompi record** dopo aver completato la procedura. Se il problema delle prestazioni è un rendering della pagina, attendere che la pagina venga renderizzata prima di interrompere la registrazione.

4. Fare clic su **Salva**.

![Schermata della procedura di registrazione o PSR.exe.](../media/8542b0aa-a3ff-4718-8dc4-43f5521c6c34.PNG)
  
La data e l'ora vengono registrate per l'utente. Questo collega il PSR alla traccia Netmon e HTTPWatch nel tempo e contribuisce alla risoluzione dei problemi di precisione. La data e l'ora nel record PSR possono mostrare che un minuto è passato tra l'account di accesso e l'esplorazione dell'URL e il rendering parziale del sito di amministrazione, ad esempio.
  
## <a name="read-your-traces"></a>Leggere le tracce

Non è possibile insegnare tutto ciò che riguarda la risoluzione dei problemi di rete e prestazioni che un utente deve conoscere tramite un articolo. Ottenere una buona performance richiede esperienza e informazioni su come funziona la rete e di solito esegue. Tuttavia, è possibile arrotondare un elenco di problemi principali e mostrare come gli strumenti possano rendere più facile eliminare i problemi più comuni.
  
Se si desidera raccogliere le competenze di lettura delle tracce di rete per i siti di Office 365, non esiste un insegnante migliore rispetto alla creazione regolare delle tracce dei carichi di pagina e all'esperienza di lettura. Ad esempio, quando si ha la possibilità, caricare un servizio di Office 365 e tracciare il processo. Filtrare la traccia per il traffico DNS o cercare in FrameData il nome del servizio visitato. Analizzare la traccia per ottenere un'idea dei passaggi che si verificano quando il servizio viene caricato. In questo modo viene illustrato il tipo di caricamento normale della pagina e, in caso di risoluzione dei problemi, in particolare per quanto riguarda le prestazioni, il confronto tra il bene e le tracce negative può essere molto utile.
  
Netmon utilizza Microsoft IntelliSense nel campo filtro visualizzazione. IntelliSense, o il completamento intelligente del codice, è quel trucchetto in cui si digita un punto e tutte le opzioni disponibili vengono visualizzate in una casella di selezione a discesa. Se, ad esempio, si è preoccupati per la scalabilità delle finestre TCP, è possibile trovare un filtro (come  `.protocol.tcp.window < 100` ) con questo mezzo.
  
![Schermata di Netmon che indica che il campo filtro visualizzazione utilizza IntelliSense.](../media/75a56c11-9a60-47ee-a100-aabdfb1ba10f.PNG)
  
Le tracce Netmon possono essere molto trafficate. Se non si ha esperienza con la lettura, è probabile che si sarà sopraffatti aprendo la traccia per la prima volta. La prima cosa da fare è separare il segnale dal rumore di sottofondo nella traccia. Sono stati testati su Office 365 e questo è il traffico che si desidera visualizzare. Se si è abituati all'esplorazione tramite traccia, potrebbe non essere necessario questo elenco.
  
Il traffico tra il client e Office 365 viaggia tramite TLS, il che significa che il corpo del traffico verrà crittografato e non leggibile in una traccia Netmon generico. L'analisi delle prestazioni non deve conoscere le specifiche delle informazioni presenti nel pacchetto. Tuttavia, è molto interessato alle intestazioni di pacchetti e alle informazioni che contengono.
  
### <a name="tips-to-get-a-good-trace"></a>Suggerimenti per ottenere una buona traccia
  
- Conoscere il valore dell'indirizzo IPv4 o IPv6 del computer client. È possibile ottenere questo comando dal prompt dei comandi digitando **ipconfig** e quindi premendo INVIO. Se si conosce l'indirizzo, è possibile indicare a breve se il traffico nella traccia coinvolge direttamente il computer client. Se è presente un proxy conosciuto, eseguirne il ping e ottenere anche il relativo indirizzo IP.

- Svuotare la cache del resolver DNS e, se possibile, chiudere tutti i browser eccetto quello in cui si eseguono i test. Se non si è in grado di eseguire questa operazione, ad esempio, se il supporto utilizza alcuni strumenti basati su browser per visualizzare il desktop del computer client, prepararsi a filtrare la traccia.

- In una traccia molto trafficata, individuare il servizio Office 365 che si sta utilizzando. Se non si è mai visto o raramente il traffico prima, questo è un passaggio utile per separare il problema delle prestazioni da altro rumore di rete. Esistono alcuni modi per eseguire questa operazione. Direttamente prima del test, è possibile utilizzare _ping_ o _PSPING_ rispetto all'URL del servizio specifico ( `ping outlook.office365.com` o `psping -4 microsoft-my.sharepoint.com:443` , ad esempio,). È inoltre possibile trovare facilmente il ping o PsPing in una traccia Netmon (in base al nome del processo). Che vi darà un posto per iniziare a guardare.

Se si utilizza solo l'analisi Netmon al momento del problema, va bene anche questo. Per orientarsi, utilizzare un filtro come `ContainsBin(FrameData, ASCII, "office")` o `ContainsBin(FrameData, ASCII, "outlook")` . È possibile registrare il numero di frame dal file di traccia. È inoltre possibile scorrere il riquadro di _Riepilogo dei frame_ fino a destra e cercare la colonna ID conversazione. Vi è un numero indicato per l'ID di questa conversazione specifica che è anche possibile registrare e guardare in isolamento in un secondo momento. Ricordarsi di rimuovere il filtro prima di applicare qualsiasi altro filtro.

> [!TIP]
> Netmon ha un sacco di utili filtri incorporati. Provare il pulsante **Carica filtro** nella parte superiore del riquadro del filtro di _visualizzazione_ .
  
![Individuare l'indirizzo IP utilizzando PSPing nella riga di comando del computer client.](../media/4c43ac67-e28e-4536-842d-7add7aa28847.PNG)
  
![Traccia Netmon dal client che mostra lo stesso comando PSPing tramite il filtro TCP. Flags. SYN = = 1.](../media/0ae7ef7d-e003-4d01-a006-dc49bd1fcef2.PNG)
  
Familiarizzare con il traffico e imparare a individuare le informazioni necessarie. Ad esempio, informazioni per determinare quale pacchetto nella traccia ha il primo riferimento al servizio Office 365 che si sta utilizzando (come "Outlook").

Se si prende come esempio Office 365 Outlook online, il traffico inizia in questo modo:
  
- Query DNS standard e risposta DNS per outlook.office365.com con QueryIDs corrispondenti. È importante notare la distanza di tempo per questo turno, così come dove nel mondo il DNS globale di Office 365 invia la richiesta di risoluzione dei nomi. Idealmente, il più localmente possibile, piuttosto che a metà strada in tutto il mondo.

- Una richiesta HTTP GET la cui relazione sullo stato è stata spostata in modo permanente (301)

- Traffico RW, incluse le richieste di connessione di RW e le risposte. (Questo è Remote Winsock che effettua una connessione per l'utente).

- Una conversazione TCP SYN e TCP SYN/ACK. Molte delle impostazioni di questa conversazione hanno un impatto sulle prestazioni.

- Quindi una serie di traffico TLS: TLS che è il luogo in cui si verificano le conversazioni tra TLS e TLS. (Tenere presente che i dati vengono crittografati tramite SSL/TLS).

Tutte le parti del traffico sono importanti e connesse, ma piccole porzioni di traccia contengono informazioni particolarmente importanti in termini di risoluzione dei problemi relativi alle prestazioni, quindi ci concentreremo su queste aree. Inoltre, dal momento che è stata eseguita una risoluzione dei problemi relativi alle prestazioni di Office 365 in Microsoft per compilare un elenco dei primi dieci, si concentrerà su tali problemi e su come usare gli strumenti che è necessario sradicare successivamente.
  
Se non sono state installate tutte pronte, la matrice seguente utilizza diversi strumenti. Se possibile. I collegamenti vengono forniti ai punti di installazione. L'elenco include strumenti comuni di traccia di rete come [Netmon](https://www.microsoft.com/download/details.aspx?id=4865) e [Wireshark](https://www.wireshark.org/), ma utilizza qualsiasi strumento di tracciabilità con cui si è pratici e in cui si è abituati a filtrare il traffico di rete. Quando si esegue il testing, tenere presente quanto segue:
  
- *Chiudere il browser e verificare che sia presente un solo browser in esecuzione, in*  questo modo si riduce il traffico globale acquisito. Consente una traccia meno trafficata.
- *Svuotare la cache del resolver DNS sul computer client*  -questo vi darà una tabula rasa quando si inizia a prendere la cattura, per una traccia più pulita.

## <a name="common-issues"></a>Problemi comuni

Alcuni problemi comuni che possono essere affrontati e come individuarli nella traccia di rete.

### <a name="tcp-windows-scaling"></a>Scalabilità di Windows TCP

Presenti nel SYN-SYN/ACK. L'hardware legacy o di invecchiamento potrebbe non trarre vantaggio dalla scalabilità di Windows TCP.  Senza appropriate impostazioni di ridimensionamento di Windows TCP, il buffer a 16 bit predefinito nelle intestazioni TCP si riempie in millisecondi.  Il traffico non può continuare a essere inviato finché il client non riceve un riconoscimento per il quale i dati originali sono stati ricevuti, causando ritardi.

#### <a name="tools"></a>Strumenti

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Cosa cercare

Cercare il traffico SYN-SYN/ACK nella traccia di rete.  In Netmon, utilizzare un filtro come  `tcp.flags.syn == 1` . Questo filtro è lo stesso in Wireshark.  

![Filtrare in Netmon o Wireshark per i pacchetti SYN per entrambi gli strumenti: TCP. Flags. SYN = = 1.](../media/4b9a12a1-c915-43c8-ac2f-a679d0435a29.PNG)

Si noti che per ogni SYN è presente un numero di porta di origine (SrcPort) corrispondente nella porta di destinazione (DstPort) del riconoscimento correlato (SYN/ACK).

Per visualizzare il valore di ridimensionamento di Windows utilizzato dalla connessione di rete, espandere prima il SYN e quindi il relativo SYN/ACK.  

![Grafico che illustra come corrispondere SrcPort a DstPort in una traccia, per ottenere il Delta del tempo.](../media/6a4ca573-0253-4fbd-93e8-92821ee1c351.png)  

### <a name="tcp-idle-time-settings"></a>Impostazioni di tempo di inattività TCP

Storicamente, la maggior parte delle reti perimetrali è configurata per le connessioni transitorie, che significa che le connessioni inattive vengono Le sessioni TCP inattive possono essere interrotte da proxy e firewall a un valore superiore a 100 a 300 secondi. Questo è un problema per Outlook online perché crea e utilizza connessioni a lungo termine, sia che siano inattive o meno.  

Quando le connessioni vengono terminate da dispositivi proxy o firewall, il client non è informato e un tentativo di utilizzare Outlook online significherà che un computer client tenterà ripetutamente di rilanciare la connessione prima di crearne una nuova. È possibile che si verifichino blocchi nel prodotto, nelle istruzioni o in una lenta esecuzione del caricamento della pagina.

#### <a name="tools"></a>Strumenti

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Cosa cercare

In Netmon, guardare il campo scostamento orario per un round trip. Un round trip è il tempo tra il client che invia una richiesta al server e la ricezione di una risposta. Controllare tra il client e il punto di uscita (es. Client-- \> proxy) o il client a office 365 (client-- \> Office 365). È possibile visualizzarlo in molti tipi di pacchetti.

Ad esempio, il filtro in Netmon può essere simile  `.Protocol.IPv4.Address == 10.102.14.112 AND .Protocol.IPv4.Address == 10.201.114.12` o, in Wireshark,  `ip.addr == 10.102.14.112 &amp;&amp; ip.addr == 10.201.114.12` .  

> [!TIP]
> Non è possibile sapere se l'indirizzo IP nella traccia appartiene al server DNS? Provare a cercarlo dalla riga di comando. Fare clic su **Avvia** \> **esecuzione** \> e digitare **cmd**oppure premere il **tasto Windows** \> e digitare **cmd**. Al prompt dei comandi digitare  `nslookup <the IP address from the network trace>` . Per eseguire il test, utilizzare Nslookup rispetto all'indirizzo IP del proprio computer. > per visualizzare un elenco degli intervalli IP di Microsoft, vedere [URL e intervalli di indirizzi IP di Office 365](https://technet.microsoft.com/library/hh373144.aspx).

Se si verifica un problema, si prevede che gli offset di tempo prolungati vengano visualizzati, in questo caso (Outlook online), in particolare nei pacchetti TLS: TLS che mostrano il passaggio dei dati delle applicazioni (ad esempio, in Netmon è possibile trovare i pacchetti di dati dell'applicazione tramite  `.Protocol.TLS AND Description == "TLS:TLS Rec Layer-1 SSL Application Data"` ). Verrà visualizzata una graduale progressione nel tempo della sessione. Se si verificano ritardi prolungati durante l'aggiornamento di Outlook online, ciò può essere causato da un elevato grado di reimpostazione inviati.

### <a name="latencyround-trip-time"></a>Latenza/tempo di andata e ritorno

La latenza è una misura che può cambiare molto a seconda di molte variabili, ad esempio l'aggiornamento dei dispositivi di invecchiamento, l'aggiunta di un numero elevato di utenti a una rete e la percentuale di larghezza di banda complessiva utilizzata da altre attività in una connessione di rete.

Esistono calcolatrici della larghezza di banda per Office 365 disponibili in questa pagina di [pianificazione della rete e ottimizzazione delle prestazioni per office 365](network-planning-and-performance.md) .  

È necessario misurare la velocità della connessione o la larghezza di banda della connessione dell'ISP? Provare questo sito (o siti simili): [speedtest Official Site](https://www.speedtest.net/)o eseguire una query sul motore di ricerca preferito per il **test della velocità**della frase.

#### <a name="tools"></a>Strumenti

- Ping
- PsPing
- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Cosa cercare

Per tenere traccia della latenza in una traccia, si trarrà vantaggio dall'aver registrato l'indirizzo IP del computer client e l'indirizzo IP del server DNS in Office 365. Questo è allo scopo di semplificare la traccia del filtro. Se si effettua la connessione tramite un proxy, sarà necessario l'indirizzo IP del computer client, l'indirizzo IP del proxy/uscita e l'indirizzo IP DNS di Office 365 per semplificare il lavoro.  

Una richiesta di ping inviata a outlook.office365.com diranno il nome del datacenter che riceve la richiesta, anche se il ping  *potrebbe*  non essere in grado di connettersi per inviare i pacchetti ICMP del marchio consecutivi. Se si utilizza PsPing (uno strumento gratuito per il download) e specifica la porta (443) e, se si desidera utilizzare IPv4 (-4), si otterrà una media di andata e ritorno per i pacchetti inviati. Questo funzionerà per altri URL nei servizi di Office 365, ad esempio `psping -4 yourSite.sharepoint.com:443` . In effetti, è possibile specificare un numero di ping per ottenere un campione più grande per la media, provare qualcosa di simile `psping -4 -n 20 yourSite-my.sharepoint.com:443` .  

> [!NOTE]
> PsPing non invia pacchetti ICMP. Viene eseguito il ping con i pacchetti TCP su una porta specifica, quindi è possibile utilizzarne uno che si conosce per essere aperti. In Office 365, che utilizza SSL/TLS, provare a collegare la porta: 443 al PsPing.

![Schermata che consente di visualizzare un ping di risoluzione di outlook.office365.com e un PSPing con il 443 facendo lo stesso, ma anche segnalando un RTT medio di 6.5 ms.](../media/c64339f2-2c96-45b8-b168-c2a060430266.PNG)

Se è stata caricata la pagina di Office 365 lenta eseguendo una traccia di rete, è necessario filtrare una traccia NetMon o Wireshark per `DNS` . Questo è uno degli indirizzi IP che stiamo cercando.  

Di seguito sono riportati i passaggi da eseguire per filtrare Netmon per ottenere l'indirizzo IP (e dare un'occhiata alla latenza DNS). In questo esempio viene utilizzato outlook.office365.com, ma è anche possibile utilizzare l'URL di un tenant di SharePoint Online (ad esempio, hithere.sharepoint.com).  

1. Eseguire il ping dell'URL `ping outlook.office365.com` e, nei risultati, registrare il nome e l'indirizzo IP del server DNS a cui è stata inviata la richiesta di ping.
2. Traccia di rete apertura della pagina o esecuzione dell'azione che consente di ottenere il problema delle prestazioni oppure, se viene visualizzata una latenza elevata sul ping stesso, la traccia di rete viene eseguita.
3. Aprire la traccia in Netmon e filtrare per DNS (questo filtro funziona anche in Wireshark, ma è sensibile al caso `-- dns` ). Dal momento che si conosce il nome del server DNS dal ping è possibile anche filtrare più rapidamente in Netmon come questo: `DNS AND ContainsBin(FrameData, ASCII, "namnorthwest")` , che assomiglia a questo in Wireshark DNS e frame contiene "namnorthwest".<br/>Aprire il pacchetto di risposta e, nella finestra **Dettagli struttura** Netmon, fare clic su **DNS** per espandersi per ulteriori informazioni. Nelle informazioni DNS è possibile trovare l'indirizzo IP del server DNS in cui la richiesta è stata indirizzata in Office 365. Questo indirizzo IP dovrà essere utilizzato per il passaggio successivo (lo strumento PsPing). Rimuovere il filtro, fare clic con il pulsante destro del mouse sulla risposta DNS in Netmon (**frame Summary** \> **Find conversazioni** \> **DNS**) per visualizzare la query DNS e la risposta affiancata.
4. In Netmon, prendere nota anche della colonna offset temporale tra la richiesta e la risposta DNS. Nel passaggio successivo, lo strumento di [PsPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) di facile installazione e utilizzo risulta molto utile, sia perché ICMP è spesso bloccato sui firewall, sia perché PsPing tiene traccia della latenza in millisecondi in modo elegante. PsPing completa una connessione TCP a un indirizzo e una porta (nel nostro caso aprire la porta 443).
5. Installare PsPing.
6. Aprire un prompt dei comandi ( \> avviare \> il tipo di esecuzione cmd o \> il tipo di chiave di Windows cmd) e passare alla directory in cui è stato installato PsPing per eseguire il comando PsPing. Nei miei esempi è possibile vedere che ho creato una cartella ' perf ' nella radice di C. È possibile eseguire la stessa operazione per un accesso rapido.
7. Digitare il comando in modo da rendere PsPing l'indirizzo IP del server DNS di Office 365 dalla traccia Netmon precedente, incluso il numero di porta, ad esempio `psping -n 20 132.245.24.82:445` . Questo vi darà un campionamento di 20 ping e la media della latenza quando PsPing si arresta.

Se si sta per Office 365 tramite un server proxy, la procedura è leggermente diversa. Per prima cosa, è necessario PsPing al server proxy per ottenere un valore medio di latenza in millisecondi per proxy/uscita e viceversa, quindi eseguire PsPing nel proxy o su un computer con una connessione Internet diretta per ottenere il valore mancante (quello di Office 365 e viceversa).  

Se si sceglie di eseguire PsPing dal proxy, saranno disponibili due valori di millisecondi: il computer client per il server proxy o il punto di uscita e il server proxy su Office 365. Ed è tutto finito. Bene, i valori di registrazione, comunque.  

Se si esegue PsPing in un altro computer client che dispone di una connessione diretta a Internet, ovvero senza un proxy, saranno disponibili due valori di millisecondi: il computer client per il server proxy o il punto di uscita e il computer client in Office 365. In questo caso, sottrarre il valore del computer client al server proxy o al punto di uscita dal valore del computer client a Office 365 e si avranno i numeri di RTT dal computer client al server proxy o al punto di uscita e dal server proxy o dal punto di uscita a Office 365.

Tuttavia, se è possibile trovare un computer client nel percorso interessato direttamente connesso oppure ignorare il proxy, è possibile scegliere se il problema si riproduce per iniziare e quindi verificarne l'utilizzo in seguito.

Latenza, come illustrato in una traccia Netmon, i millisecondi aggiuntivi possono essere aggiunti, se sono sufficienti in una determinata sessione.  

![Latenza generale in Network Monitor, con la colonna dell'intervallo di tempo predefinita di Network Monitor aggiunta al riepilogo dei frame.](../media/7ad17380-8527-4bc2-9b9b-6310cf19ba6b.PNG)

> [!NOTE]
> L'indirizzo IP potrebbe essere diverso da quello visualizzato qui, ad esempio, il ping potrebbe restituire qualcosa di più simile a 157.56.0.0/16 o a un intervallo simile. Per un elenco degli intervalli utilizzati da Office 365, vedere [URL e intervalli di indirizzi IP di office 365](https://technet.microsoft.com/library/hh373144.aspx).

Tenere presente che per espandere tutti i nodi (è presente un pulsante nella parte superiore) se si desidera eseguire la ricerca, ad esempio 132,245.

### <a name="proxy-authentication"></a>Autenticazione proxy

Questo si applica solo a te se stai attraversando un server proxy. In caso contrario, è possibile ignorare questi passaggi. Quando si lavora correttamente, l'autenticazione proxy deve essere eseguita in millisecondi in modo coerente. Non è possibile visualizzare le prestazioni Intermittent negative durante i periodi di utilizzo di picco (ad esempio).  

Se l'autenticazione proxy è attiva, ogni volta che si crea una nuova connessione TCP a Office 365 per ottenere informazioni, è necessario passare attraverso un processo di autenticazione dietro le quinte. Quando, ad esempio, si passa dal calendario alla posta elettronica in Outlook online, verrà effettuato l'autenticazione. E in SharePoint Online, se una pagina Visualizza supporti o dati provenienti da più siti o posizioni, l'autenticazione per ogni connessione TCP diversa è necessaria per eseguire il rendering dei dati.  

In Outlook online, è possibile che si verifichino tempi di caricamento indesiderati quando si passa da un calendario alla cassetta postale o carichi di pagine rallentati in SharePoint Online. Tuttavia, vi sono altri sintomi non elencati qui.

L'autenticazione proxy è un'impostazione del server proxy di uscita. Se si sta causando un problema di prestazioni con Office 365, è necessario consultare il team di rete.  

#### <a name="tools"></a>Strumenti

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>Cosa cercare

L'autenticazione proxy avviene ogni volta che è necessario eseguire il filato su una nuova sessione TCP, in genere per richiedere file o informazioni dal server o per fornire informazioni. Ad esempio, è possibile che venga visualizzato l'autenticazione proxy attorno alle richieste HTTP GET o HTTP POST. Se si desidera visualizzare i frame in cui si eseguono le richieste di autenticazione nella traccia, aggiungere la colonna ' NTLMSSP Summary ' a Netmon e filtrare per  `.property.NTLMSSPSummary` . Per visualizzare il tempo di esecuzione dell'autenticazione, aggiungere la colonna Delta del tempo.

Per aggiungere una colonna a Netmon:

1. Fare clic con il pulsante destro del mouse su una colonna, ad esempio **Descrizione**.
2. Fare clic su **Scegli colonne**.
3. Individuare il _Riepilogo di NTLMSSP_ e il _Delta temporale_ nell'elenco e fare clic su **Aggiungi**.
4. Spostare le nuove colonne in posizione prima o dietro la colonna _Descrizione_ in modo da poterle leggere affiancate.
5. Fare clic su **OK**.

Anche se non si aggiunge la colonna, il filtro Netmon funzionerà. Tuttavia, la risoluzione dei problemi è molto più semplice se è possibile visualizzare il livello di autenticazione in cui si è in uso.

Quando si cercano istanze di autenticazione proxy, è necessario studiare tutti i frame in cui è presente una richiesta NTLM oppure è presente un messaggio di autenticità. Se necessario, fare clic con il pulsante destro del mouse sulla parte di traffico specifica e individuare le conversazioni \> TCP. Tenere conto dei valori Delta temporali in queste conversazioni.

![Traccia Netmon che mostra l'autenticazione proxy, filtrata tramite conversazione.](../media/b640f176-0a52-4bbb-972e-60fb3d6aece2.PNG)

Un ritardo di quattro secondi nell'autenticazione del proxy come mostrato in Wireshark. L' **intervallo di tempo tra la colonna del fotogramma visualizzato precedente** è stato eseguito facendo clic con il pulsante destro del mouse sul campo dello stesso nome nei dettagli della cornice e selezionando Aggiungi come colonna.  <br/> ![In Wireshark, la colonna ' Time Delta from previous displayd frame ' può essere fatta facendo clic con il pulsante destro del mouse sul campo dello stesso nome nei dettagli della cornice e selezionando Aggiungi come colonna.](../media/f5b7bde4-8067-4ee0-bc7f-e9062ce1ba6f.PNG)

### <a name="dns-performance"></a>Prestazioni DNS

La risoluzione dei nomi funziona in modo ottimale e più rapidamente quando avviene il più vicino possibile al paese del client.

Se la risoluzione del nome DNS è in corso all'estero, è possibile aggiungere secondi ai carichi di pagina. Idealmente, la risoluzione del nome avviene in 100 ms. In caso contrario, è consigliabile eseguire ulteriori indagini.

> [!TIP]
> Non si è sicuri di come funziona la connettività client in Office 365? Esaminare il documento di riferimento per la connettività client [qui](https://technet.microsoft.com/library/dn741250.aspx).

#### <a name="tools"></a>Strumenti

- Netmon
- Wireshark
- PsPing

#### <a name="what-to-look-for"></a>Cosa cercare

L'analisi delle prestazioni DNS è in genere un altro processo per una traccia di rete. Tuttavia, PsPing è utile anche per determinare o escludere una possibile causa.

Il traffico DNS è basato sulle richieste TCP e UDP e le risposte sono chiaramente contrassegnate con un ID che consentirà di corrispondere una richiesta specifica con la risposta specifica. Verrà visualizzato il traffico DNS quando, ad esempio, SharePoint Online utilizza un nome di rete o un URL in una pagina Web. Come regola generale, la maggior parte del traffico, tranne per il trasferimento delle aree, viene eseguito su UDP.

In entrambi i casi Netmon e Wireshark, il filtro di base che consente di esaminare il traffico DNS è semplicemente `dns` . Assicurarsi di utilizzare la minuscola quando si specifica il filtro. Prima di iniziare a riprodurre il problema nel computer client, ricordarsi di svuotare la cache del resolver DNS. Ad esempio, se si dispone di un caricamento lenta della pagina di SharePoint Online per la Home page, è necessario chiudere tutti i browser, aprire un nuovo browser, avviare la traccia, svuotare la cache del resolver DNS e passare al sito di SharePoint Online. Dopo la risoluzione dell'intera pagina, è necessario arrestare e salvare la traccia.

![Un filtro di base per DNS in Netmon è DNS.](../media/1bebc118-ca13-45f3-803f-ab73e7af401d.png)

Si desidera esaminare l'offset del tempo qui. Potrebbe essere utile aggiungere la colonna Delta del **tempo** a Netmon che è possibile eseguire eseguendo la procedura seguente:

1. Fare clic con il pulsante destro del mouse su una colonna, ad esempio **Descrizione**.
2. Fare clic su **Scegli colonne**.
3. Individuare _Time Delta_ nell'elenco e fare clic su **Aggiungi**.
4. Spostare la nuova colonna in posizione prima o dopo la colonna _Descrizione_ in modo da poterli leggere affiancate.
5. Fare clic su **OK**.

Se si trova una query di interesse, è consigliabile isolarla facendo clic con il pulsante destro del mouse su tale query nel riquadro dettagli frame, scegliendo **Trova conversazioni** \> **DNS**. Si noti che il riquadro conversazioni di rete passa direttamente alla conversazione specifica nel log del traffico UDP.

![Una traccia Netmon del caricamento di Outlook online filtrata da DNS e l'utilizzo di trova conversazioni quindi DNS per limitare i risultati.](../media/763cf20e-7b48-4a37-9449-c9978cfe118b.PNG)

In Wireshark è possibile creare una colonna per il tempo DNS. Prendere la traccia (o aprire una traccia) in Wireshark e filtrare in base `dns` o, più utile,  `dns.time` . Fare clic su qualsiasi query DNS e, nel riquadro che mostra i dettagli, espandere i  `Domain Name System (response)` Dettagli. Verrà visualizzato un campo per il tempo, ad esempio `[Time: 0.001111100 seconds]` . Fare clic con il pulsante destro del mouse e selezionare **applica come colonna**. In questo modo verrà restituita una colonna **temporale** per l'ordinamento più rapido della traccia. Fare clic sulla nuova colonna per ordinare i valori decrescenti per vedere quale chiamata DNS ha richiesto la risoluzione più lunga.

[Una ricerca di SharePoint Online filtrata in Wireshark da (tutto minuscolo) dns.time, con il tempo dei dettagli realizzato in una colonna e classificato in ordine crescente.](../media/1439dcc2-12ff-4ee2-9ef3-1484cf79c384.PNG)

Se si desidera eseguire ulteriori indagini sul tempo di risoluzione DNS, provare a utilizzare PsPing sulla porta DNS utilizzata da TCP (ad esempio,  `psping <IP address of DNS server>:53` ). Si vede ancora un problema di prestazioni? In caso contrario, è più probabile che si tratti di un problema di rete più ampio rispetto a un problema di specifica applicazione DNS che si sta colpendo per la risoluzione. Vale anche la pena di ricordare che un ping a outlook.office365.com ti dirà dove è in corso la risoluzione dei nomi DNS per Outlook online (ad esempio, outlook-namnorthwest.office365.com).

Se il problema sembra specifico DNS, potrebbe essere necessario rivolgersi al proprio reparto IT per esaminare le configurazioni DNS e i Forwarder DNS per analizzare ulteriormente questo problema.

### <a name="proxy-scalability"></a>Scalabilità del proxy

Servizi come Outlook online in Office 365 concedere ai client più connessioni a lungo termine. Pertanto, ogni utente può utilizzare più connessioni che richiedono una durata più lunga.  

#### <a name="tools"></a>Strumenti

Matematiche  

#### <a name="what-to-look-for"></a>Cosa cercare

Non è presente alcuna traccia di rete o uno strumento di risoluzione dei problemi specifico. Invece, si basa su calcoli di larghezza di banda determinate limitazioni e altre variabili.  

### <a name="tcp-max-segment-size"></a>Dimensione massima del segmento TCP

Presenti nel SYN-SYN/ACK.  Eseguire questo controllo in qualsiasi traccia di rete di prestazioni eseguita per garantire che i pacchetti TCP siano configurati in modo da contenere la quantità massima di dati possibile.

L'obiettivo è vedere un MSS di 1460 byte per la trasmissione dei dati. Se si è dietro un proxy o si utilizza un NAT, ricordarsi di eseguire il test da client a proxy/uscita/NAT e da proxy/uscita/NAT a Office 365 per ottenere risultati ottimali. Si tratta di sessioni TCP diverse.

#### <a name="tools"></a>Strumenti

Netmon

#### <a name="what-to-look-for"></a>Cosa cercare

La dimensione del segmento TCP Max (MSS) è un altro parametro dell'handshake a tre vie nella traccia di rete, quindi i dati necessari sono disponibili nel pacchetto SYN-SYN/ACK. MSS è in realtà piuttosto semplice da vedere.

Aprire qualsiasi traccia di rete delle prestazioni di cui si dispone e trovare la connessione di cui si è curiosi o che dimostra il problema delle prestazioni.

> [!NOTE]
> Se si sta esaminando una traccia ed è necessario trovare il traffico pertinente per la conversazione, filtrare in base all'indirizzo IP del client o all'IP del server proxy o del punto di uscita o di entrambi. Se si sta eseguendo direttamente, è necessario eseguire il ping sull'URL che si sta testando per l'indirizzo IP di Office 365 nella traccia e filtrare in base al filtro.

Guardando la traccia di seconda mano? Provare a utilizzare i filtri per orientarsi. In Netmon eseguire una ricerca in base all'URL, ad esempio `Containsbin(framedata, ascii, "sphybridExample")` , prendere nota del numero di fotogrammi.

In Wireshark utilizzare qualcosa di simile  `frame contains "sphybridExample"` . Se si nota che il traffico di Winsock (RW) remoto è stato trovato (potrebbe essere visualizzato come [PSH, ACK] in Wireshark), tenere presente che la connessione di RW può essere visualizzata poco prima della pertinente SYN-SYN/ACK, come descritto in precedenza.

A questo punto, è possibile registrare il numero di frame, eliminare il filtro, fare clic su **tutto il traffico** nella finestra conversazioni di rete in Netmon per esaminare il SYN più vicino.

[! Importante] se non si ricevono le informazioni sull'indirizzo IP al momento della traccia, la ricerca dell'URL nella traccia (parte di `sphybridExample-my.sharepoint.com` , ad esempio) fornirà gli indirizzi IP da filtrare.

Individuare la connessione nella traccia che si desidera visualizzare. È possibile eseguire questa operazione analizzando la traccia, filtrando in base agli indirizzi IP o selezionando ID di conversazione specifici utilizzando la finestra conversazioni di rete in Netmon. Dopo aver trovato il pacchetto SYN, espandere TCP (in Netmon) o Transmission Control Protocol (in Wireshark) nel riquadro dettagli frame. Espandere Opzioni TCP e MaxSegmentSize. Individuare il frame SYN-ACK correlato ed espandere Opzioni TCP e MaxSegmentSize. Minore dei due valori sarà la dimensione massima del segmento. In questa immagine, si utilizza la colonna incorporata in Netmon definì la risoluzione dei problemi relativi a TCP.  

![Traccia di rete filtrata in Netmon utilizzando le colonne predefinite.](../media/e073df13-71f8-497a-83b4-bb9f70bd9833.PNG)

La colonna incorporata si trova nella parte superiore del riquadro dei **Dettagli della cornice** . Per tornare alla visualizzazione normale, fare di nuovo clic su **colonne** e quindi scegliere **fuso orario**.

![Dove trovare l'elenco a discesa delle colonne per l'opzione di risoluzione dei problemi di TCP (nella parte superiore del riepilogo dei frame).](../media/64fd4baa-a872-4f07-b959-752d7d37fd62.PNG)

Ecco una traccia filtrata in Wireshark. È presente un filtro specifico per il valore MSS ( `tcp.options.mss` ). Le cornici di un SYN, SYN/ACK, handshake ACK sono collegate nella parte inferiore del Wireshark equivalente ai dettagli dei fotogrammi (in modo da frame 47 ACK, collegamenti a 46 SYN/ACK, collegamenti a 43 SYN) per semplificare questo tipo di lavoro.

![Traccia filtrata in Wireshark da TCP. Options. MSS per la dimensione massima del segmento (MSS).](../media/51e278db-801b-48bc-9b68-87cf92f03fd6.PNG)

Se è necessario controllare il **riconoscimento selettivo** (argomento successivo in questa matrice), non chiudere la traccia.

### <a name="selective-acknowledgment"></a>Riconoscimento selettivo

Presenti nel SYN-SYN/ACK. Devono essere segnalate come consentito sia in SYN che in SYN/ACK. Il riconoscimento selettivo (SACK) consente di ritrasmettere più agevolmente i dati quando un pacchetto o pacchetti risultano mancanti. I dispositivi possono disabilitare questa funzionalità, che può causare problemi di prestazioni.

Se si è dietro un proxy o si utilizza un NAT, ricordarsi di eseguire il test da client a proxy/uscita/NAT e da proxy/uscita/NAT a Office 365 per ottenere risultati ottimali. Si tratta di sessioni TCP diverse.

#### <a name="tools"></a>Strumenti

Netmon

#### <a name="what-to-look-for"></a>Cosa cercare

Il riconoscimento selettivo (SACK) è un altro parametro nell'handshake SYN-SYN/ACK. È possibile filtrare la traccia per i diversi modi SYN-SYN/ACK.

Individuare la connessione nella traccia che si desidera visualizzare analizzando la traccia, filtrando in base agli indirizzi IP o facendo clic su un ID di conversazione utilizzando la finestra conversazioni di rete in Netmon. Dopo aver trovato il pacchetto SYN, espandere TCP in Netmon o Transmission Control Protocol in Wireshark nella sezione frame details. Espandere Opzioni TCP e quindi SACK. Individuare il frame SYN-ACK correlato ed espandere Opzioni TCP e il relativo campo SACK. Fare in modo che alcuni sacchi siano ammessi sia in SYN che in SYN/ACK. Di seguito sono riportati i valori di SACK come visualizzato in Netmon e Wireshark.

![Riconoscimento selettivo (SACK) in Netmon come risultato di TCP. Flags. SYN = = 1.](../media/216f556f-5031-4ed2-b066-a0d9b3251fa2.PNG)

![SACK come visualizzato in Wireshark con il filtro tcp.flags.syn == 1.](../media/0a6e26e5-43dc-403b-adc9-3349a55f4e4b.PNG)

### <a name="dns-geolocation"></a>Geolocation DNS

Dove nel mondo Office 365 cerca di risolvere gli effetti della chiamata DNS la velocità di connessione.

In Outlook online, dopo aver completato la prima ricerca DNS, il percorso del DNS verrà utilizzato per la connessione al datacenter più vicino. L'utente sarà connesso a un server Accesso client di Outlook online, che utilizzerà la rete backbone per connettersi al datacenter (dC) in cui sono archiviati i dati. Questo è più veloce.

Quando si accede a SharePoint Online, gli utenti che viaggiano all'estero verranno indirizzati al data center attivo, ovvero il controller di database la cui posizione si basa sulla base di casa del tenant di SPO (pertanto, un controller di rete negli Stati Uniti, se l'utente è basato su Stati Uniti).

Lync Online dispone di nodi attivi in più di un controller di rete alla volta. Quando le richieste vengono inviate per le istanze di Lync Online, il DNS di Microsoft determinerà il percorso da cui proviene la richiesta e restituirà gli indirizzi IP dal controller di dominio regionale più vicino in cui è attivo Lync Online.

> [!TIP]
> Per ulteriori informazioni sul modo in cui i client si connettono a Office 365? Esaminare l'articolo di riferimento per la [connettività dei client](https://technet.microsoft.com/library/dn741250.aspx) (e la grafica utile).

#### <a name="tools"></a>Strumenti

- Ping
- PsPing

#### <a name="what-to-look-for"></a>Cosa cercare

Le richieste di risoluzione dei nomi dai server DNS del client ai server DNS di Microsoft dovrebbero, nella maggior parte delle ipotesi, comportare la restituzione di un indirizzo IP di un datacenter regionale (dC) tramite Microsoft DNS. Cosa significa questo per te? Se il tuo quartier generale si trova a Bangalore (India), ma viaggi negli Stati Uniti, quando il browser effettua una richiesta per Outlook online, i server DNS di Microsoft dovrebbero consegnare gli indirizzi IP ai datacenter negli Stati Uniti--un datacenter regionale. Se è necessario un messaggio di posta elettronica da Outlook, i dati viaggeranno tra la rete backbone rapida di Microsoft tra i datacenter.

DNS funziona più velocemente quando la risoluzione dei nomi viene fatta il più vicino possibile alla posizione dell'utente. Se si è in Europa, si vuole andare a Microsoft DNS in Europa e (idealmente) si tratta di un datacenter in Europa. Le prestazioni di un client in Europa che vanno a DNS e un datacenter in America saranno più lente.

Eseguire lo strumento Ping su outlook.office365.com per determinare la posizione in cui viene instradata la richiesta DNS. Se ci si trova in Europa, dovrebbe essere visualizzata una risposta da qualcosa di simile a outlook-emeawest.office365.com. Nelle Americhe, aspettatevi qualcosa di simile a outlook-namnorthwest.office365.com.

Aprire il prompt dei comandi nel computer client (tramite avvia \> esecuzione \> cmd o il tipo di chiave cmd di Windows \> ). Digitare ping outlook.office365.com e premere INVIO. Tenere presente che per specificare-4 Se si desidera specificare il ping tramite IPv4. Potrebbe non essere possibile ottenere una risposta dai pacchetti ICMP, ma dovrebbe essere visualizzato il nome del DNS in cui la richiesta è stata instradata. Se si desidera visualizzare i numeri di latenza per la connessione, provare PsPing nell'indirizzo IP del server restituito da ping.  

![Ping di outlook.office365.com che mostra la risoluzione in outlook-namnorthwest.](../media/06c944d5-6159-43ec-aa31-757770695e8b.PNG)

![PSPing all'indirizzo IP restituito dal ping a outlook.office365.com mostrando una latenza media di 28 millisecondi.](../media/f2b25a75-1a87-4479-b8a7-fa4375683507.PNG)

### <a name="office-365-application-troubleshooting"></a>Risoluzione dei problemi relativi alle applicazioni di Office 365

#### <a name="tools"></a>Strumenti

- Netmon
- HTTPWatch
- Console F12 nel browser

Non vengono illustrati gli strumenti utilizzati per la risoluzione dei problemi specifici di un'applicazione in questo articolo specifico della rete. Tuttavia, è possibile trovare le risorse che  *possono*  essere utilizzate [in questa pagina](https://support.office.com/article/Network-planning-and-performance-tuning-for-Office-365-e5f1228c-da3c-4654-bf16-d163daee8848).

## <a name="related-topics"></a>Argomenti correlati

[Gestione degli endpoint di Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Domande frequenti sugli endpoint di Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
