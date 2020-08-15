---
title: Resilienza dei dati di Exchange online in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In questo articolo, trovare una spiegazione dei vari aspetti della resilienza dei dati in Exchange Online e Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfc53fd48a6de61cf47a0441cd2f8b0fa35a73f1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696074"
---
# <a name="exchange-online-data-resiliency-in-microsoft-365"></a>Resilienza dei dati di Exchange online in Microsoft 365

Esistono due tipi di danneggiamento che possono influire su un database di Exchange: il danneggiamento fisico, che in genere è causato da problemi hardware (in particolare, hardware di archiviazione) e da un danneggiamento logico, che si verifica a causa di altri fattori. In generale, esistono due tipi di danneggiamenti logici che possono verificarsi in un database di Exchange: 
- **Danneggiamento logico del database** -il checksum della pagina del database corrisponde, ma i dati della pagina sono errati logicamente. Questo problema può verificarsi quando il motore di database (ESE) tenta di scrivere una pagina di database e, anche se il sistema operativo restituisce un messaggio di esito positivo, i dati non vengono mai scritti nel disco o sono stati scritti nel posto sbagliato. Questo viene definito *rilevamento flush*. ESE include numerose funzionalità e misure di salvaguardia progettate per impedire il danneggiamento fisico di un database e di altri scenari di perdita dei dati. Per impedire la perdita di dati per gli scaricamenti persi, ESE include un meccanismo di rilevamento di incasso perso nel database insieme a una funzionalità (ripristino a pagina singola) per correggerla. 
- **Archiviazione logica di danneggiamento** : i dati vengono aggiunti, eliminati o modificati in modo che l'utente non si aspetti. Questi casi sono generalmente causati da applicazioni di terze parti. Generalmente, questa situazione viene percepita dall'utente come un danneggiamento. L'archivio di Exchange considera la transazione che ha causato il danneggiamento della partizione logica come una serie di operazioni MAPI valide. Le funzionalità di archiviazione sul [posto](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) in Exchange Online offrono protezione dal danneggiamento logico dell'archivio (perché impedisce che il contenuto venga eliminato definitivamente da un utente o da un'applicazione). 

Exchange Online esegue diversi controlli di coerenza sui file di registro replicati durante l'ispezione dei registri e la riproduzione dei registri. Questi controlli di coerenza impediscono la replica del danneggiamento fisico da parte del sistema. Ad esempio, durante l'ispezione dei registri, è presente un controllo dell'integrità fisica che verifica il file di registro e convalida che il checksum registrato nel file di registro corrisponde al checksum generato in memoria. Viene inoltre esaminata l'intestazione del file di registro per verificare che la firma del file di registro registrata nell'intestazione del registro corrisponda a quella del file di registro. Durante la riproduzione dei log, il file di registro subisce un ulteriore controllo. Ad esempio, l'intestazione del database contiene anche la firma del registro che viene confrontata con la firma del file di registro per verificare che corrispondano. 

La protezione contro la corruzione dei dati delle cassette postali in Exchange Online viene ottenuta utilizzando la protezione dei dati nativi di Exchange, una strategia di resilienza che sfrutta la replica a livello di applicazione tra più server e più datacenter insieme ad altre caratteristiche che consentono di proteggere i dati da perdite dovute a danneggiamenti o altri motivi. Queste funzionalità includono funzionalità native gestite da Microsoft o dall'applicazione Exchange Online, ad esempio:

- [Gruppi di disponibilità dei dati](https://docs.microsoft.com/exchange/back-up-email)
- Correzione bit singolo 
- Analisi dei database online 
- Rilevamento di incasso perso 
- Ripristino di una singola pagina 
- Servizio di replica delle cassette postali 
- Controlli file di registro 
- Distribuzione nel file System resiliente 

Per ulteriori informazioni sulle caratteristiche native sopra elencate, fare clic sui collegamenti ipertestuali sopra riportati e vedere di seguito per ulteriori informazioni e per dettagli sugli elementi senza collegamenti ipertestuali. Oltre a queste funzionalità native, Exchange Online include anche funzionalità di resilienza dei dati che i clienti possono gestire, ad esempio: 
- [Ripristino di un singolo elemento (abilitata per impostazione predefinita)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages) 
- [Conservazione in locale e per controversia legale](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds) 
- [Conservazione degli elementi eliminati e cassette postali eliminate temporaneamente (entrambi abilitati per impostazione predefinita)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes) 

## <a name="database-availability-groups"></a>Gruppi di disponibilità del database 
Ogni database delle cassette postali in Microsoft 365 è ospitato in un [gruppo di disponibilità del database (DAG)](https://docs.microsoft.com/exchange/back-up-email) e replicato in datacenter geograficamente separati all'interno della stessa area. La configurazione più comune è costituita da quattro copie del database in quattro datacenter. Tuttavia, alcune aree dispongono di un numero minore di centri dati (i database vengono replicati in tre datacenter in India e due datacenter in Australia e Giappone). Tuttavia, in tutti i casi, ogni database delle cassette postali dispone di quattro copie distribuite su più datacenter, garantendo così che i dati delle cassette postali siano protetti da errori software, hardware e persino del datacenter. 

Tra queste quattro copie, tre sono configurate come estremamente disponibili. La quarta copia è configurata come [copia del database ritardata](https://docs.microsoft.com/Exchange/high-availability/manage-ha/activate-lagged-db-copies). La copia del database ritardata non è progettata per il ripristino di una singola cassetta postale o per il recupero di un elemento. Lo scopo è quello di fornire un meccanismo di ripristino per l'evento raro di un danneggiamento logico irreversibile a livello di sistema. 

Le copie ritardate del database in Exchange Online sono configurate con un intervallo di riesecuzione dei file di registro di sette giorni. Inoltre, il gestore di lag di riesecuzione di Exchange è abilitato a fornire un file di registro dinamico riprodotto per le copie ritardate in modo da consentire le copie ritardate del database per la correzione automatica e la gestione dello sviluppo dei file di registro. Anche se le copie del database ritardate vengono utilizzate in Exchange Online, è importante comprendere che non sono un backup temporizzato garantito. Le copie ritardate del database in Exchange Online hanno una soglia di disponibilità, in genere attorno al 90%, a causa di periodi in cui il disco contenente una copia ritardata viene perso a causa di un errore del disco, la copia ritardata diventa una copia estremamente disponibile (a causa del riutilizzo automatico), nonché i periodi in cui la copia del database ritardata ricostruisce la coda di 

## <a name="transport-resilience"></a>Resilienza del trasporto 
Exchange Online include due caratteristiche di resilienza del trasporto principali: la ridondanza shadow e la rete sicura. La ridondanza shadow conserva una copia ridondante di un messaggio mentre è in transito. La rete sicura mantiene una copia ridondante di un messaggio dopo che il messaggio è stato recapitato correttamente. 

Con la ridondanza shadow, ogni server di trasporto Exchange Online crea una copia di ogni messaggio che riceve prima di riconoscere la ricezione del messaggio al server di invio. In questo modo, tutti i messaggi nella pipeline di trasporto sono ridondanti mentre sono in transito. Se Exchange Online determina che il messaggio originale è stato perso durante il trasporto, viene recapitata una copia ridondante del messaggio. 

Safety net è una coda di trasporto associata al servizio di trasporto su un server cassette postali. In questa coda vengono archiviate le copie dei messaggi elaborati correttamente dal server. Quando un database delle cassette postali o un errore del server richiede l'attivazione di una copia obsoleta del database delle cassette postali, i messaggi nella coda della rete sicura vengono reinoltrati automaticamente alla nuova copia attiva del database delle cassette postali. Anche la rete sicura è ridondante, eliminando così il trasporto come singolo punto di errore. Utilizza il concetto di una rete sicura primaria e una rete di sicurezza Shadow in cui se la rete sicura primaria non è disponibile per più di 12 ore, le richieste di reinvio diventano richieste di reinvio Shadow e i messaggi vengono recapitati dalla rete sicura Shadow.

I reinvii dei messaggi dalla rete sicura vengono avviati automaticamente dal componente Active Manager del servizio replica di Microsoft Exchange che gestisce i DAG e le copie del database delle cassette postali. Per reinviare i messaggi dalla rete sicura non sono necessarie azioni manuali. 

## <a name="single-bit-correction"></a>Correzione bit singolo 
ESE include un meccanismo per rilevare e risolvere gli errori CRC a bit singolo (aka Flip a bit singolo) che sono il risultato di errori hardware (e come tali rappresentano un danneggiamento fisico). Quando si verificano questi errori, ESE corregge automaticamente gli eventi e registra un evento nel registro eventi. 

## <a name="online-database-scanning"></a>Analisi dei database online 
L'analisi dei database online (nota anche come *database checksum dei*) è il processo in cui un ESE utilizza un verificatore di coerenza del database per leggere ogni pagina e controllare il danneggiamento di una pagina. Lo scopo principale è rilevare il danneggiamento fisico e i rossore persi che potrebbero non essere rilevati dalle operazioni transazionali. L'analisi dei database esegue anche operazioni di arresto anomalo successive all'archiviazione. Lo spazio può essere fuoriuscito a causa di arresti anomali e l'analisi dei database online rileva e recupera lo spazio perso. Il sistema è stato creato con l'aspettativa che ogni database sia completamente analizzato una volta ogni sette giorni. 

## <a name="lost-flush-detection"></a>Rilevamento di incasso perso 
Uno svuotamento perso si verifica quando un'operazione di scrittura del database che il sottosistema del disco o il sistema operativo restituito come completato non è stata effettivamente scritta su disco oppure è stata scritta nella posizione errata. Gli incidenti di incasso persi possono comportare un danneggiamento logico del database, in modo da evitare che i risciacquo persi provochino dati persi, ESE include un meccanismo di rilevamento di incasso perduto. Quando le pagine di database vengono scritte in copie passive, viene eseguito un controllo per gli scaricamenti persi sulla copia attiva. Se viene rilevato un colore perso, ESE può riparare il processo utilizzando un processo di applicazione di patch per le pagine. 

## <a name="single-page-restore"></a>Ripristino di una singola pagina 
Il ripristino di una pagina singola, ovvero l'applicazione di *patch*, è un processo automatico in cui le pagine danneggiate del database vengono sostituite da copie integre da una replica sana. Il processo di ripristino di una pagina danneggiata dipende dal fatto che la copia del database sia attiva o passiva. Quando una copia attiva di un database incontra una pagina danneggiata, può copiare una pagina da una delle relative repliche, purché la pagina in cui viene copiato sia completamente aggiornata. Questa operazione viene eseguita inserendo una richiesta per la pagina nel flusso di log, che è la base della replica del database delle cassette postali. Non appena una replica rileva la richiesta di pagina risponde inviando una copia della pagina alla copia del database richiedente. Il ripristino di una singola pagina fornisce anche un meccanismo di comunicazione asincrono per l'attivo per richiedere una pagina dalle repliche, anche se le repliche sono attualmente offline. 

In caso di danneggiamento in una copia passiva del database, inclusa una copia del database ritardata, poiché queste copie sono sempre dietro la loro copia attiva, è sempre possibile copiare una pagina dalla copia attiva a una copia passiva. Una copia passiva del database è a disponibilità elevata, pertanto, durante il processo di applicazione delle patch, la riproduzione del registro viene sospesa, ma la copia del registro continua. La copia passiva del database recupera una copia della pagina danneggiata dalla copia attiva, attende che il file di registro che soddisfa il requisito massimo necessario per la generazione dei registri venga copiato e ispezionato e quindi patch la pagina danneggiata. Dopo la correzione della pagina, la riproduzione del registro riprende. Il processo è lo stesso per la copia ritardata del database, tranne per il fatto che il database ritardato riproduce tutti i file di registro necessari per ottenere uno stato patchable. 

## <a name="mailbox-replication-service"></a>Servizio di replica delle cassette postali 
Lo spostamento delle cassette postali è una parte fondamentale della gestione di un servizio di posta elettronica su larga scala. Sono sempre aggiornate le tecnologie e gli aggiornamenti per l'hardware e la versione da gestire, quindi disporre di un sistema robusto e limitato che consente ai propri ingegneri di realizzare questo lavoro mantenendo la trasparenza degli spostamenti delle cassette postali per gli utenti (assicurandosi che rimangano online durante tutto il processo) sia fondamentale e che il processo venga applicato in modo graduale quando le cassette postali aumentano 

Il servizio di replica delle cassette postali di Exchange (MRS) è responsabile dello spostamento delle cassette postali tra database. Durante lo spostamento, la signora esegue una verifica della coerenza su tutti gli elementi all'interno della cassetta postale. Se si verifica un problema di coerenza, la signora correggerà il problema oppure ignorerà gli elementi danneggiati, rimuovendo così il danneggiamento dalla cassetta postale. 

Poiché la signora è un componente di Exchange Online, è possibile apportare modifiche al codice per risolvere nuove forme di danneggiamento che vengono rilevate in futuro. Ad esempio, se si rileva un problema di coerenza che la signora non è in grado di risolvere, è possibile analizzare il danneggiamento, modificare il codice MRS e correggere l'incongruenza (se si capisce come). 

## <a name="log-file-checks"></a>Controlli file di registro 
Tutti i file di registro delle transazioni generati da un database di Exchange subiscono diverse forme di verifica della coerenza. Quando viene creato un file di registro, la prima cosa da fare è che viene scritto un modello di bit e quindi viene eseguita una serie di scritture dei registri. In questo modo Exchange Online esegue una serie di verifiche (perdita di colore, CRC e altri controlli) per convalidare ogni file di registro così come viene scritto e di nuovo come replicato. 

## <a name="deployment-on-resilient-file-system"></a>Distribuzione nel file System resiliente 
Per evitare che si verifichino danneggiamenti a livello di file System, Exchange Online viene distribuito su partizioni di file System resilienti per offrire funzionalità di ripristino migliorate. ReFS è un file System in Windows Server 2012 e versioni successive che è stato creato per essere più resistente rispetto al danneggiamento dei dati, massimizzando così la disponibilità e l'integrità dei dati. In particolare, ReFS apporta miglioramenti alla modalità di aggiornamento dei metadati, offrendo una maggiore protezione dei dati e riduce i casi di danneggiamento dei dati. Vengono inoltre utilizzati checksum per verificare l'integrità dei dati e dei metadati di file e garantire che il danneggiamento dei dati venga facilmente individuato e ripristinato. 

Exchange Online si avvale di diversi vantaggi per gli arbitri: 
- Maggiore resilienza nell'integrità dei dati significa meno incidenti di danneggiamento dei dati. La riduzione del numero di incidenti di danneggiamento comporta meno reseeding di database inutili. 
- Checksum in esecuzione su metadati che consentono di rilevare i casi di danneggiamento in modo più precoce e deterministico, consentendo di risolvere il danneggiamento dei dati del cliente prima che si verifichino errori grigi sui volumi di dati
- Progettata per funzionare bene con set di dati di dimensioni estremamente grandi, ovvero petabyte e dimensioni maggiori, senza impatto sulle prestazioni
- Supporto per altre funzionalità utilizzate da Exchange Online, ad esempio la crittografia BitLocker. 

Exchange Online beneficia anche di altre caratteristiche di ReFS: 
- **Integrità (flussi di integrità)** -l'arbitro archivia i dati in modo da proteggerli da molti degli errori comuni che in genere possono causare la perdita di dati. Microsoft 365 Search utilizza flussi di integrità per facilitare il rilevamento dei danni del disco precoce e il checksum del contenuto del file. La caratteristica riduce anche gli incidenti di danneggiamento causati da "Scritture strappate" (quando un'operazione di scrittura non viene completata a causa di interruzioni di corrente, ecc.). 
- **Availability (Salvage)** -refs dà la priorità alla disponibilità dei dati. Storicamente, i sistemi di file erano spesso suscettibili di danneggiamento dei dati che richiedeva che il sistema venisse portato offline per il ripristino. Sebbene sia raro, se si verifica un danneggiamento, ReFS implementa il salvataggio, una funzionalità che rimuove i dati danneggiati dallo spazio dei nomi in un volume attivo e assicura che i dati validi non siano influenzati negativamente dai dati danneggiati non riparabili. L'applicazione della funzionalità di salvataggio e l'isolamento del danneggiamento dei dati nei volumi di database di Exchange Online significa che è possibile mantenere integro i database non interessati su un volume danneggiato tra il tempo di danneggiamento e l'azione di ripristino. In questo modo si aumenta la disponibilità dei database che in genere sono danneggiati da problemi di danneggiamento del disco. 