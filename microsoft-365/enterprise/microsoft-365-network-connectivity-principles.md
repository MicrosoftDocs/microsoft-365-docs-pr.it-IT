---
title: Principi di connettività di rete di Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
search.appverid: MET150
ms.assetid: 76e7f232-917a-4b13-8fe2-4f8dbccfe041
f1.keywords:
- NOCSH
description: Questo articolo fornisce le indicazioni più recenti per ottimizzare in modo sicuro la connettività di rete di Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a6f104f53abd0a9aa2376b09c93af96d7f8178e8
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519740"
---
# <a name="microsoft-365-network-connectivity-principles"></a>Principi di connettività di rete di Microsoft 365

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Prima di iniziare la pianificazione della rete per la connettività di rete di Microsoft 365, è importante comprendere i principi di connettività per gestire in modo sicuro il traffico di Microsoft 365 e ottenere le migliori prestazioni possibili. Questo articolo spiega come comprendere le indicazioni più recenti per ottimizzare in modo sicuro la connettività di rete di Microsoft 365.
  
Le reti tradizionali aziendali sono progettate principalmente per fornire agli utenti accesso ad applicazioni e dati ospitati in centri dati aziendali gestiti con un livello di sicurezza perimetrale elevato. Il modello tradizionale presuppone che gli utenti accedano ad applicazioni e dati all'interno del perimetro della rete aziendale, tramite collegamenti WAN dalle filiali o da remoto tramite connessioni VPN.
  
L'adozione di applicazioni SaaS, come Microsoft 365, consente di spostare una combinazione di servizi e dati all'esterno del perimetro di rete. Senza ottimizzazione, il traffico tra gli utenti e le applicazioni SaaS è soggetto a una latenza introdotta dall'ispezione dei pacchetti, fenomeni di hairpinning di rete, connessioni accidentali a endpoint geograficamente lontani e ad altri fattori. È possibile garantire migliori prestazioni e affidabilità di Microsoft 365 comprendendo ed implementando le linee guida chiave per l'ottimizzazione.
  
In questo articolo saranno trattati i seguenti argomenti:
  
- [Architettura di Microsoft 365 ](microsoft-365-network-connectivity-principles.md#BKMK_Architecture) siccome si applica alla connettività dei clienti al cloud
- [Principi di connettività Microsoft 365](microsoft-365-network-connectivity-principles.md#BKMK_Principles)aggiornati e strategie per ottimizzare il traffico di rete e l’esperienza utente finale
- Il [servizio web per gli endpoint di Office 365](microsoft-365-network-connectivity-principles.md#BKMK_WebSvc), che consente agli amministratori di rete di usare un elenco strutturato di endpoint al fine di ottimizzare la rete
- [Nuove categorie di endpoint di Office 365](microsoft-365-network-connectivity-principles.md#BKMK_Categories) e indicazioni di ottimizzazione
- [Confronto tra la sicurezza perimetrale di rete e sicurezza degli endpoint](microsoft-365-network-connectivity-principles.md#BKMK_SecurityComparison)
- [Opzioni di ottimizzazione incrementale](microsoft-365-network-connectivity-principles.md#BKMK_IncOpt) per il traffico di Microsoft 365
- Il [test di connettività Microsoft 365](https://aka.ms/netonboard), un nuovo strumento per testare la connettività di base a Microsoft 365

## <a name="microsoft-365-architecture"></a>Architettura Microsoft 365
<a name="BKMK_Architecture"> </a>

Microsoft 365 è un cloud SaaS distribuito (Software As A Service) che garantisce scenari di produttività e collaborazione con diversi set di micro-servizi e applicazioni, come Exchange Online, SharePoint Online, Skype for business online, Microsoft teams, Exchange Online Protection, Office in un browser e molti altri. Anche se specifiche applicazioni di Microsoft 365 potrebbero avere funzionalità esclusive per quanto riguarda la rete clienti e la connettività al cloud, tutte condividono alcuni principali criteri, obiettivi e modelli di architettura. Questi criteri e modelli di architettura per la connettività sono tipici per molti altri cloud SaaS e allo stesso tempo diversi dai modelli di distribuzione di piattaforma distribuita come servizio e infrastruttura distribuita come servizio, come Microsoft Azure.
  
Una delle caratteristiche più significative a livello di architettura di Microsoft 365, spesso dimenticata o interpretata in modo non corretto dai progettisti di rete, è che si tratta di un servizio distribuito globale nel maniera in cui gli utenti si connettono a esso. La posizione del tenant di Microsoft 365 è importante per comprendere la località in cui sono archiviati i dati dei clienti nel cloud, ma l'esperienza utente con Microsoft 365 non implica la connessione diretta ai dischi che contengono i dati. L'esperienza utente con Microsoft 365, incluse prestazioni, affidabilità e altre importanti caratteristiche di qualità, prevede la connettività attraverso porte di servizio ampiamente distribuite che si espandono orizzontalmente in centinaia di sedi Microsoft in tutto il mondo. Nella maggior parte dei casi, l'esperienza utente ottimale consente alla rete del cliente di instradare le richieste degli utenti al punto di ingresso del servizio Microsoft 365 più vicino, invece di connettersi a Microsoft 365 attraverso un punto di uscita in una località centrale o regionale.
  
Per la maggior parte dei clienti, gli utenti Microsoft 365 sono distribuiti in diverse località. Per ottenere risultati ottimali, è consigliabile esaminare  questo documento dal punto di vista della scalabilità orizzontale, non verticale, con particolare attenzione all'ottimizzazione della connettività al punto di presenza più vicino nella rete globale di Microsoft, non alla posizione geografica del tenant di Microsoft 365. In sostanza, questo significa che, anche se i dati dei tenant di Microsoft 365 potrebbero essere archiviati in una specifica posizione geografica, l'esperienza di Microsoft 365 per quel tenant resta distribuita e può essere presente in prossimità (di rete) a tutte le località dell'utente finale.
  
## <a name="microsoft-365-connectivity-principles"></a>Principi della connettività di Microsoft 365
<a name="BKMK_Principles"> </a>

Microsoft consiglia i seguenti criteri per ottenere connettività e prestazioni ottimali di Microsoft 365. Usa questi principi di connettività di Microsoft 365 per gestire il traffico e ottenere prestazioni ottimali quando ci si connette a Microsoft 365.
  
L'obiettivo principale della struttura di rete deve essere ridurre al minimo la latenza, riducendo il tempo di round trip (RTT) dalla rete alla rete globale di Microsoft, la backbone di rete pubblica Microsoft che connette tutti i centri dati di Microsoft con bassa latenza e punti di ingresso dell'applicazione cloud sparsi in tutto il mondo. Per altre informazioni sulla rete globale di Microsoft, vedere [Come Microsoft sviluppa la sua rete globale veloce e affidabile](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).
  
<a name="BKMK_P1"> </a>
### <a name="identify-and-differentiate-microsoft-365-traffic"></a>Identificare e differenziare il traffico di Microsoft 365

![Identificare il traffico di Microsoft 365](../media/621aaec9-971d-4f19-907a-1ae2ef6d72fc.png)
  
Identificare il traffico di rete di Microsoft 365 è il primo passaggio per poter distinguere tale traffico da quello di rete generico Internet. La connettività di Microsoft 365 può essere ottimizzata implementando una combinazione di approcci come l'ottimizzazione del percorso di rete, regole del firewall, impostazioni del proxy del browser ed esclusione dei dispositivi di controllo di rete per alcuni endpoint.
  
Le precedenti indicazioni per l'ottimizzazione di Microsoft 365 divideva gli endpoint in due categorie: **Necessario** e **Facoltativo**. Quando sono stati aggiunti endpoint per supportare nuovi servizi e caratteristiche di Microsoft 365, tali sono stati riorganizzati in tre categorie: **Ottimizzare**, **Consentire**, e **Predefinito**. Le linee guida per ogni categoria sono valide per tutti gli endpoint della categoria, semplificando la comprensione e l'implementazione delle ottimizzazioni.
  
Per altre informazioni sulle categorie e sui metodi di ottimizzazione di Microsoft 365, vedere la sezione [Nuove categorie di endpoint di Office 365](microsoft-365-network-connectivity-principles.md#BKMK_Categories).
  
Microsoft pubblica ora tutti gli endpoint Microsoft 365 come servizio web e fornisce indicazioni sul modo migliore per usare questi dati. Per altre informazioni su come recuperare e usare gli endpoint di Microsoft 365, vedere l'articolo [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
<a name="BKMK_P2"> </a>
### <a name="egress-network-connections-locally"></a>Uscita dalle connessione di rete a livello locale

![Uscita dalle connessione di rete a livello locale](../media/b42a45be-1ab4-4073-a7dc-fbdfb4aedd24.png)
  
Il DNS locale e l'uscita internet sono essenziali per ridurre la latenza della connessione e garantire che le connessioni utente vengano apportate al punto di accesso più vicino ai servizi di Microsoft 365. In una topologia di rete complessa è importante implementare contemporaneamente sia DNS locale che uscita internet locale. Per altre informazioni su come Microsoft 365 instrada le connessioni client al punto di ingresso più vicino, vedere l'articolo [Connessioni client](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b).
  
Prima dell'avvento dei servizi cloud come Microsoft 365, la connettività internet degli utenti finali come fattore di progettazione nell'architettura di rete era relativamente semplice. Quando i servizi internet e i siti web sono distribuiti in tutto il globo, la latenza tra i punti di uscita aziendali e un endpoint di destinazione specifico è in gran parte una funzione di distanza geografica.
  
In un'architettura di rete tradizionale, tutte le connessioni internet in uscita attraversano la rete aziendale, ed escono da una posizione centralizzata. Con la maturazione delle offerte cloud di Microsoft, l'importanza di avere un'architettura di rete distribuita accessibile da Internet è cresciuta al fine di supportare i servizi cloud sensibili alla latenza. La rete globale di Microsoft è stata pensata per supportare i requisiti di latenza con l'infrastruttura porta di servizio distribuita, un tessuto dinamico di punti di ingresso globali che instrada le connessioni al servizio cloud in ingresso al punto di ingresso più vicino. Si tratta di un problema che consente di ridurre la durata dell’ “ultimo miglio” per i clienti Microsoft cloud riducendo efficacemente il percorso tra il cliente e il cloud.
  
Le reti WAN aziendali sono spesso progettate per il backhaul del traffico di rete verso una sede centrale dell'azienda per l'ispezione, prima dell'uscita su internet, di solito attraverso uno o più server proxy. Il diagramma seguente illustra una topologia di rete.
  
![Modello di rete aziendale tradizionale](../media/fc87b8fd-a191-47a7-9704-1e445599813a.png)
  
Poiché Microsoft 365 viene eseguito sulla rete globale Microsoft, che include server front-end in tutto il mondo, spesso ci sarà un server front-end vicino alla posizione dell'utente. Fornendo l'uscita internet locale e configurando i server DNS interni per fornire la risoluzione dei nomi locali per gli endpoint di Microsoft 365, il traffico di rete destinato a Microsoft 365 può connettersi ai server front-end Microsoft 365 il più vicino possibile all'utente. Il diagramma seguente mostra un esempio di una topologia di rete che consente agli utenti che si connettono dalla sede centrale, dalla filiale e da remoto di seguire il percorso più breve al punto di ingresso di Microsoft 365 più vicino.
  
![Modello di rete WAN con punti di uscita regionali](../media/4d4c07cc-a928-42b8-9a54-6c3741380a33.png)
  
Ridurre il percorso di rete ai punti di ingresso di Microsoft 365 consente di migliorare le prestazioni di connettività, l'esperienza degli utenti finali in Microsoft 365 e anche ridurre l'impatto sulle future modifiche che saranno apportate all'architettura di rete in base alle prestazioni e all'affidabilità di Microsoft 365.
  
Inoltre, le richieste DNS possono presentare una latenza se il server DNS di risposta è distante o occupato. È possibile ridurre al minimo la latenza della risoluzione dei nomi eseguendo il provisioning dei server DNS locali nelle filiali e configurandoli per memorizzare nella cache i record DNS in modo appropriato.
  
Anche se l'uscita regionale può funzionare per Microsoft 365, il modello di connettività ottimale dovrebbe fornire sempre l'uscita di rete in base alla posizione dell'utente, indipendentemente dal fatto che si trovi nella rete aziendale o da remoto, come in case, alberghi, caffetterie e aeroporti. Il modello di uscita diretta locale è rappresentato nel diagramma seguente.
  
![Architettura di rete locale di uscita](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)
  
Le aziende che hanno adottato Microsoft 365 possono trarre vantaggio dall'architettura del servizio distribuito dalla rete globale di Microsoft, assicurando che le connessioni utente a Microsoft 365 portino il percorso più breve possibile al punto di ingresso della rete globale Microsoft più vicino. L'architettura di rete locale di uscita consente di instradare il traffico di Microsoft 365 nell'uscita più vicina, indipendentemente dalla posizione dell'utente.
  
L'architettura di uscita locale offre i seguenti vantaggi rispetto al modello tradizionale:
  
- Garantisce prestazioni ottimali di Microsoft 365 ottimizzando la lunghezza del percorso. Le connessioni degli utenti finali sono instradate in modo dinamico al punto di ingresso Microsoft 365 più vicino dall'infrastruttura per le porte di servizio distribuite.
- Consente di ridurre il carico sull'infrastruttura di rete aziendale consentendo l'uscita locale.
- Protegge le connessioni in entrambe le estremità sfruttando le caratteristiche di sicurezza dell’endpoint client e le caratteristiche di sicurezza del cloud.

<a name="BKMK_P3"> </a>
### <a name="avoid-network-hairpins"></a>Evitare fenomeni di hairpinning di rete

![Evitare fenomeni di hairpinning](../media/ee53e8af-f57b-4292-a256-4f36733b263a.png)
  
Come regola generale, il percorso più breve e diretto tra l'utente e l'endpoint Microsoft 365 più vicino offre le migliori prestazioni. Un hairpinning di rete si verifica quando il traffico WAN o VPN associato a una determinata destinazione viene prima indirizzato a un altro percorso intermedio, ad esempio stack di sicurezza, cloud Access broker, gateway web basato su cloud, introducendo la latenza e il reindirizzamento potenziale a un punto finale geograficamente distante. I fenomeni di hairpinning di rete possono essere causati anche da inefficienze di routing e peering o da ricerche DNS subottimali (remote).
  
Per fare in modo che la connettività di Microsoft 365 non sia soggetta a fenomeni di hairpinning di rete anche nel caso di uscita locale, verificare se l'ISP usata per fornire l'uscita Internet per la posizione dell'utente ha una relazione di peering diretta con la rete globale Microsoft in prossimità di tale percorso. È inoltre possibile configurare il routing in uscita per inviare direttamente il traffico Microsoft 365 attendibile, anziché eseguire il proxy o il tunneling attraverso un cloud di terze parti o un fornitore di sicurezza di rete basato su cloud che elabora il traffico Internet. La risoluzione dei nomi DNS locale degli endpoint di Microsoft 365 aiuta a garantire che oltre al routing diretto, vengano utilizzati i punti di ingresso di Microsoft 365 più vicini per le connessioni utente.
  
Se utilizzi servizi di sicurezza o rete basati sul cloud per il traffico Microsoft 365, assicurati che il risultato dell’hairpinning sia valutato e che il suo impatto sulle prestazioni di Microsoft 365 sia compreso. Questa operazione può essere eseguita esaminando il numero e le posizioni dei provider di servizi con cui viene inviato il traffico in relazione al numero di filiali e ai punti di peering della rete globale Microsoft, la qualità della relazione di peering di rete del provider di servizi con il proprio ISP e Microsoft e l'impatto sulle prestazioni del backhauling nell'infrastruttura del provider di servizi.
  
A causa dell'elevato numero di posizioni distribuite con punti di accesso Microsoft 365 e della loro vicinanza agli utenti finali, l'instradamento del traffico di Microsoft 365 a qualsiasi rete di terze parti o provider di sicurezza può avere un impatto negativo sulle connessioni di Microsoft 365 se la rete del provider non è configurata per il peering ottimale di Microsoft 365.
  
<a name="BKMK_P4"> </a>
### <a name="assess-bypassing-proxies-traffic-inspection-devices-and-duplicate-security-technologies"></a>Valutare l'omissione dei proxy, dispositivi di ispezione del traffico e tecnologie di sicurezza duplicate

![Ignorare i proxy, dispositivi di ispezione del traffico e tecnologie di sicurezza duplicate](../media/0131930d-c6cb-4ae1-bbff-fe4cf6939a23.png)
  
I clienti aziendali devono rivedere i propri metodi di sicurezza della rete e riduzione dei rischi, specificatamente per il traffico associato a Microsoft 365 e usare le funzionalità di sicurezza di Microsoft 365 per ridurre la dipendenza da tecnologie  intrusive, che incidono sulle prestazioni e sono costose per il traffico di rete di Microsoft 365.
  
La maggior parte delle reti aziendali applica la sicurezza di rete per il traffico Internet usando tecnologie come proxy, controllo SSL, controllo dei pacchetti e sistemi di prevenzione della perdita dei dati. Queste tecnologie forniscono importanti riduzioni dei rischi per le richieste Internet generiche, ma consentono di ridurre in modo significativo le prestazioni, la scalabilità e la qualità dell'esperienza utente finale se applicati agli endpoint Microsoft 365.
  
<a name="BKMK_WebSvc"> </a>
#### <a name="office-365-endpoints-web-service"></a>Servizio Web endpoint di Office 365

Gli amministratori di Microsoft 365 possono utilizzare uno script o una chiamata REST per utilizzare un elenco strutturato di endpoint dal servizio web endpoint di Office 365 e aggiornare le configurazioni dei firewall perimetrali e di altri dispositivi di rete. Ciò assicura che il traffico associato a Microsoft 365 sia identificato, trattato in modo appropriato e gestito in modo diverso dal traffico di rete associato a siti web generici e spesso sconosciuti. Per ulteriori informazioni su come usare il servizio web endpoint di Office 365, vedere l'articolo [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
#### <a name="pac-proxy-automatic-configuration-scripts"></a>Script PAC (configurazione automatica proxy)
<a name="BKMK_WebSvc"> </a>

Gli amministratori di Microsoft 365 possono creare script PAC (configurazione automatica proxy) che possono essere recapitati nei computer degli utenti tramite WPAD o GPO. Gli script PAC possono essere usati per ignorare i proxy per le richieste di Microsoft 365 da utenti WAN o VPN, consentendo a Microsoft 365 Traffic di usare connessioni internet dirette anziché passare alla rete aziendale.
  
#### <a name="microsoft-365-security-features"></a>Caratteristiche sicurezza Microsoft 365
<a name="BKMK_WebSvc"> </a>

Microsoft è trasparente in merito alla sicurezza dei centri dati, sicurezza operativa e riduzione dei rischi relazionati ai server Microsoft 365 e agli endpoint di rete che rappresentano. Le funzionalità di sicurezza predefinite di Microsoft 365 sono disponibili per ridurre i rischi di sicurezza di rete, ad esempio prevenzione della perdita dei dati, antivirus, autenticazione a più fattori, Customer Lock Box, Defender per Office 365, Microsoft 365 Threat Intelligence, Microsoft 365 Secure Score, Exchange Online Protection e sicurezza della rete DDOS.
  
Per ulteriori informazioni sui centri dati Microsoft e sulla sicurezza della rete globale, vedere il [Centro protezione Microsoft](https://www.microsoft.com/trustcenter/security).
  
## <a name="new-office-365-endpoint-categories"></a>Nuove categorie di endpoint di Office 365
<a name="BKMK_Categories"> </a>

Gli endpoint di Office 365 rappresentano un set variegato di indirizzi di rete e subnet. Gli endpoint potrebbero essere URL, indirizzi IP o intervalli di indirizzi IP e alcuni endpoint sono elencati con porte TCP/UDP specifiche. Gli URL possono essere un nome di dominio completo, come *account.office.net*, o un URL con caratteri jolly come *\*.office365.com*.
  
> [!NOTE]
> Le posizioni degli endpoint di Office 365 all'interno della rete non sono direttamente correlate alla posizione dei dati del tenant Microsoft 365. Per questo motivo, i clienti devono considerare Microsoft 365 come un servizio distribuito e globale e non devono cercare di bloccare connessioni di rete agli endpoint di Office 365 in base a criteri geografici.
  
Nelle precedenti indicazioni per la gestione del traffico di Microsoft 365, gli endpoint erano organizzati in due categorie: **necessario** e **facoltativo**.  Agli endpoint all'interno di ogni categoria erano richieste ottimizzazioni diverse a seconda della criticità del servizio e molti clienti sono stati messi a dura prova per giustificare l'applicazione delle stesse ottimizzazioni di rete all'elenco completo di URL e indirizzi IP di Office 365.
  
Nel nuovo modello, gli endpoint sono suddivisi in tre categorie, **ottimizzare**, **consentire**, e **predefinito**, fornendo un pivot basato sulle priorità su cui focalizzare l'attenzione sugli sforzi per ottimizzare la rete al fine di migliorare le prestazioni e avere un ritorno degli investimenti. Gli endpoint sono consolidati nelle categorie descritte in base alla sensibilità dell'esperienza utente effettiva rispetto alla qualità della rete, al volume e all'inviluppo delle prestazioni degli scenari e alla facilità di implementazione. È possibile applicare le ottimizzazioni consigliate allo stesso modo per tutti gli endpoint di una specifica categoria.
  
- Gli endpoint della categoria **Ottimizzare** sono obbligatori per la connessione a tutti i servizi di Office 365 e rappresentano più del 75% della larghezza di banda, delle connessioni e del volume di dati di Microsoft 365. Questi endpoint rappresentano gli scenari di Office 365 più sensibili alle prestazioni, la latenza e la disponibilità di rete. Tutti gli endpoint sono ospitati in centri dati Microsoft. Si prevede che il tasso di variazione agli endpoint di questa categoria sia molto inferiore rispetto agli endpoint nelle altre due categorie. Questa categoria include un piccolo set, nell'ordine di ~ 10, di URL chiave e una serie definita di sottoreti IP dedicate ai carichi principali di lavoro di Office 365 come Exchange Online, SharePoint Online, Skype for Business Online e Microsoft Teams.

    Un elenco ridotto di endpoint critici ben definiti dovrebbe aiutarti a pianificare e implementare le ottimizzazioni di rete di alto valore per queste destinazioni in modo più rapido e semplice.

    Alcuni esempi di endpoint della categoria *Ottimizzare*  sono *https://outlook.office365.com*, *https://\<tenant\>.sharepoint.com*, and *https://\<tenant\>-my.sharepoint.com*.

    I metodi di ottimizzazione includono:

  - Ignorare gli endpoint della categoria *Ottimizzare* in dispositivi di rete e servizi che eseguono l'intercettazione del traffico, decrittografia SSL, ispezione approfondita dei pacchetti e filtro del contenuto.
  - Ignorare i dispositivi proxy locali e i servizi proxy basati sul cloud usati comunemente per la navigazione internet generica.
  - Assegnare priorità alla valutazione di questi endpoint come completamente attendibile dalla propria infrastruttura di rete e sistemi perimetrali.
  - Assegnare priorità alla riduzione o all'eliminazione del backhauling WAN e semplificare l'uscita diretta distribuita su internet per questi endpoint il più vicino possibile alle posizioni degli utenti/filiali.
  - È possibile semplificare la connettività diretta a questi endpoint del cloud per gli utenti VPN mediante split tunneling.
  - Assicurati che gli indirizzi IP restituiti dalla risoluzione dei nomi DNS corrispondano al percorso di uscita del routing per questi endpoint.
  - Assegnare una priorità agli endpoint per l'integrazione con la rete SD-WAN, per il routing di latenza diretto e minimo, al punto di peering internet più vicino alla rete globale Microsoft.

- Gli endpoint della categoria **Consentire** sono obbligatori per la connessione a funzionalità e servizi specifici di Office 365, ma che non sono sensibili alle prestazioni e alla latenza di rete come quelli della categoria *Ottimizzare*. Anche il footprint della rete generale di questi endpoint, dal punto di vista della larghezza di banda e del conteggio connessioni, è minore. Questi endpoint sono dedicati a Office 365 e sono ospitati nei centri dati Microsoft. Rappresentano un ampio set di microservizi di Office 365 e relative dipendenze (nell'ordine di ~ 100 URL) e dovrebbero cambiare con un tasso superiore a quello della categoria  *Ottimizzare*. Non tutti gli endpoint della categoria sono associati a sottoreti IP dedicate e definite.

    Le ottimizzazioni di rete per gli endpoint della catergoria *Consentire*  permettono di migliorare l'esperienza utente di Office 365, ma alcuni clienti possono scegliere di limitare l'ambito di tali ottimizzazioni per ridurre al minimo le modifiche alla rete.

    Alcuni esempi di endpoint della categoria *Consentire* sono *https://\*.protection.outlook.com* and *https://accounts.accesscontrol.windows.net*.

    I metodi di ottimizzazione includono:

  - Ignorare gli endpoint della categoria *Consentire* in dispositivi di rete e servizi che eseguono l'intercettazione del traffico, decrittografia SSL, ispezione approfondita dei pacchetti e filtro del contenuto.
  - Assegnare priorità alla valutazione di questi endpoint come completamente attendibile dalla propria infrastruttura di rete e sistemi perimetrali.
  - Assegnare priorità alla riduzione o all'eliminazione del backhauling WAN e semplificare l'uscita diretta distribuita su internet per questi endpoint il più vicino possibile alle posizioni degli utenti/filiali.
  - Assicurati che gli indirizzi IP restituiti dalla risoluzione dei nomi DNS corrispondano al percorso di uscita del routing per questi endpoint.
  - Assegnare una priorità agli endpoint per l'integrazione con la rete SD-WAN, per il routing di latenza diretto e minimo, al punto di peering internet più vicino alla rete globale Microsoft.

- Gli endpoint della categoria **Predefinito** rappresentano i servizi e dipendenze di Office 365 che non richiedono alcuna ottimizzazione. La rete del cliente può considerarli come normale traffico internet. Alcuni endpoint di tale categoria potrebbero non essere ospitati in centri dai Microsoft. Alcuni esempi includono  *https://odc.officeapps.live.com*  e  *https://appexsin.stb.s-msn.com*.

Per altre informazioni sulle tecniche di ottimizzazione della rete di Office 365, vedere l'articolo [Gestione degli endpoint di Office 365](managing-office-365-endpoints.md).
  
## <a name="comparing-network-perimeter-security-with-endpoint-security"></a>Confronto tra la sicurezza perimetrale di rete e sicurezza degli endpoint
<a name="BKMK_SecurityComparison"> </a>

L'obiettivo di una sicurezza di rete tradizionale è rafforzare il perimetro della rete aziendale contro intrusioni ed exploit dannosi. Man mano che le organizzazioni adottano Microsoft 365, alcuni servizi e dati di rete vengono migrati parzialmente o completamente nel cloud. Come per qualsiasi modifica fondamentale all'architettura di rete, questo processo richiede una rivalutazione della sicurezza della rete che tenga conto dei fattori emergenti:
  
- Con l'adozione dei servizi cloud, i servizi di rete e dati vengono distribuiti tra i centri dati locali e il cloud e la sola sicurezza perimetrale non è più sufficiente.
- Gli utenti remoti si connettono alle risorse aziendali sia nei centri dati locali che nel cloud, da posizioni non controllate come case, hotel e caffetterie.
- Le funzionalità di sicurezza appositamente progettate sono sempre più integrate nei servizi cloud e possono potenzialmente integrare o sostituire i sistemi di sicurezza esistenti.

Microsoft offre una vasta gamma di funzionalità di sicurezza di Microsoft 365 e fornisce una guida prescrittiva per l'utilizzo delle migliori pratiche di sicurezza che possono aiutare a garantire la sicurezza dei dati e della rete per Microsoft 365. Le procedure consigliate sono le seguenti:
  
- **Usare l'autenticazione a più fattori (MFA)** MFA aggiunge un livello di protezione supplementare a una strategia basata su password complessa, richiedendo agli utenti di confermare la ricezione di una chiamata, un messaggio di testo o una notifica dell’app sullo smartphone dopo avere inserito correttamente la password.

- **Usare Microsoft Cloud App Security** Configurare criteri per tenere traccia delle attività anomale e intervenire sulle stesse. Configurare avvisi con Microsoft Cloud App Security per consentire agli amministratori di esaminare le attività utente insolite o rischiose, ad esempio il download di grandi quantità di dati, ripetuti tentativi di accesso non riusciti o connessioni da un indirizzo IP sconosciuto o pericoloso.

- **Configurare la prevenzione della perdita dei dati (DLP)** DPL consente di identificare i dati sensibili e creare criteri tali da impedire agli utenti di condividere i dati per errore o intenzionalmente. DLP funziona in Microsoft 365, includendo Exchange Online, SharePoint Online e OneDrive, consentendo agli utenti di restare conformi senza interrompere il flusso di lavoro.

- **Usare Customer Lockbox** In qualità di amministratore di Microsoft 365, è possibile usare Customer Lockbox per controllare il modo in cui un tecnico del supporto Microsoft può accedere ai dati dell'utente durante una sessione di assistenza. Nei casi in cui il tecnico richiede l'accesso ai dati dell'utente per risolvere e correggere un problema, Customer Lockbox consente di approvare o rifiutare la richiesta di accesso.

- **Usare Secure Score di Office 365** Si tratta di uno strumento di analisi della sicurezza che fornisce suggerimenti per ridurre ulteriormente il rischio. Secure Score esamina le impostazioni e attività di Microsoft 365 e le confronta con una linea di base definita da Microsoft. Il punteggio viene assegnato in base all'allineamento dell'azienda rispetto alle procedure consigliate per la sicurezza.

Per raggiungere un approccio olistico alla sicurezza avanzata, è necessario considerare quanto segue:
  
- Spostare l'attenzione dalla sicurezza perimetrale a quella degli endpoint applicando le funzionalità di sicurezza client basate su Office e cloud.
  - Ridurre il perimetro di sicurezza al centro dati
  - Abilitare l’affidabilità equivalente per i dispositivi degli utenti all'interno dell'ufficio o da remoto
  - Concentrarsi sulla protezione della posizione dei dati e della posizione dell'utente
  - I computer degli utenti gestiti hanno un livello di fiducia più elevato con la sicurezza degli endpoint
- Gestire tutte le informazioni in sicurezza, in maniera olistica, senza focalizzare l'attenzione esclusivamente sul perimetro
  - Ridefinire la WAN e creare la sicurezza della rete perimetrale consentendo al traffico attendibile di ignorare i dispositivi di sicurezza e spostare i dispositivi non gestiti dalle reti Wi-Fi ospiti
  - Ridurre i requisiti di sicurezza della rete del margine WAN aziendale
  - Alcuni dispositivi di sicurezza perimetrali di rete, come i firewall, sono comunque necessari, ma il carico viene ridotto
  - Assicura l'uscita locale per il traffico di Microsoft 365
- È possibile indirizzare i miglioramenti in modo incrementale come descritto nella sezione [Ottimizzazione incrementale](microsoft-365-network-connectivity-principles.md#BKMK_IncOpt). Alcune tecniche di ottimizzazione possono offrire rapporti costi/benefici migliori in base all'architettura di rete, ed è necessario scegliere ottimizzazioni che siano più importanti per la propria organizzazione.

Per ulteriori informazioni sulla sicurezza e conformità di Microsoft 365, vedere l’articolo [Sicurezza Microsoft 365](https://docs.microsoft.com/microsoft-365/security) e [Conformità Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance).
  
## <a name="incremental-optimization"></a>Ottimizzazione incrementale
<a name="BKMK_IncOpt"> </a>

In questo articolo è stato rappresentato il modello di connettività di rete ideale per SaaS, ma per molte organizzazioni di grandi dimensioni, con architetture di rete complesse, non sarà pratico apportare direttamente tutte queste modifiche. In questa sezione vengono illustrate diverse modifiche incrementali che consentono di migliorare le prestazioni e l'affidabilità di Microsoft 365.
  
I metodi che verranno usati per ottimizzare il traffico di Microsoft 365 variano in base alla topologia di rete e ai dispositivi di rete implementati. Grandi imprese con numerose postazioni e procedure complesse di sicurezza della rete devono sviluppare una strategia che includa la maggior parte o tutti i principi elencati nella sezione [Principi di connettività Microsoft 365](microsoft-365-network-connectivity-principles.md#BKMK_Principles), mentre per le organizzazioni più piccole potrebbero considerare solo uno o due principi.
  
È possibile approcciare l'ottimizzazione come processo incrementale applicando ogni metodo successivamente. La tabella seguente mostra un elenco di metodi di ottimizzazione chiave ordinati per impatto su latenza e affidabilità per il maggior numero possibile di utenti.
  
|**Metodo di ottimizzazione**|**Descrizione**|**Impatto**|
|:-----|:-----|:-----|
|Risoluzione DNS locale e uscita Internet  <br/> |Effettuare il provisioning dei server DNS locali in ogni posizione e assicurarsi che l'uscita internet delle connessioni di Microsoft 365 sia il più vicino possibile alla posizione dell'utente.  <br/> | Ridurre al minimo la latenza  <br/>  Migliorare la connettività affidabile con il punto di ingresso Microsoft 365 più vicino  <br/> |
|Aggiungere punti di uscita regionali  <br/> |Se la rete aziendale ha più posizioni, ma solo un punto di uscita, aggiungere punti di uscita regionali per consentire agli utenti di connettersi al punto di ingresso Microsoft 365 più vicino.  <br/> | Ridurre al minimo la latenza  <br/>  Migliorare la connettività affidabile con il punto di ingresso Microsoft 365 più vicino  <br/> |
|Ignorare proxy e dispositivi di controllo  <br/> |Configurare i browser con i file PAC che inviano richieste Microsoft 365 direttamente ai punti di uscita.  <br/> Configurare router perimetrali e firewall per consentire il traffico di Microsoft 365 senza controllo.  <br/> | Ridurre al minimo la latenza  <br/>  Ridurre il carico nei dispositivi di rete  <br/> |
|Abilitare la connessione diretta per gli utenti VPN  <br/> |Per gli utenti VPN, abilitare Microsoft 365 Connections per connettersi direttamente dalla rete dell'utente anziché tramite il tunnel VPN implementando split tunneling.  <br/> | Ridurre al minimo la latenza  <br/>  Migliorare la connettività affidabile con il punto di ingresso Microsoft 365 più vicino  <br/> |
|Migrare dalla WAN tradizionale alla SD-WAN  <br/> |Le SD-WAN (Software Defined Wide Area Networks) semplificano la gestione della WAN e migliorano le prestazioni sostituendo i router WAN tradizionali con applicazioni virtuali, in modo simile alla virtualizzazione delle risorse di processo mediante macchine virtuali (VM).  <br/> | Migliorare le prestazioni e la gestibilità del traffico WAN  <br/>  Ridurre il carico nei dispositivi di rete  <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Informazioni generali sulla connettività di rete di Microsoft 365](microsoft-365-networking-overview.md)

[Gestione degli endpoint di Office 365](managing-office-365-endpoints.md)

[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)

[Servizio Web per URL e indirizzi IP di Office 365](microsoft-365-ip-web-service.md)

[Valutazione della connettività di rete di Microsoft 365](assessing-network-connectivity.md)

[Pianificazione della rete e ottimizzazione delle prestazioni per Microsoft 365](network-planning-and-performance.md)

[Ottimizzazione delle prestazioni di Office 365 mediante l'uso della cronologia delle prestazioni e delle previsioni](performance-tuning-using-baselines-and-history.md)

[Piano di risoluzione dei problemi di prestazioni per Office 365](performance-troubleshooting-plan.md)

[Reti per la distribuzione di contenuti](content-delivery-networks.md)

[Test di connettività di Microsoft 365](https://aka.ms/netonboard)

[Come Microsoft sviluppa la sua rete globale veloce e affidabile](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog di rete di Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
