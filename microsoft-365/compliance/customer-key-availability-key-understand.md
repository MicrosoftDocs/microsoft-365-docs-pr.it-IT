---
title: Informazioni sulle chiavi di disponibilità per Customer Key
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Informazioni sulla chiave di disponibilità usata per recuperare le chiavi del cliente perse.
ms.openlocfilehash: 8e9903294d5fc25e51ef25c0ae6237c943dec6ab
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632025"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>Informazioni sulle chiavi di disponibilità per Customer Key

La chiave di disponibilità è una chiave radice generata automaticamente e ne viene eseguito il provisioning quando si crea un criterio di crittografia dei dati. Microsoft 365 archivia e protegge la chiave di disponibilità. La chiave di disponibilità funziona come le due chiavi radice fornite per la crittografia del servizio con Customer Key. La chiave di disponibilità esegue il wrapping delle chiavi di un livello inferiore nella gerarchia delle chiavi. A differenza delle chiavi fornite e gestite in Azure Key Vault, non è possibile accedere direttamente alla chiave di disponibilità. I servizi automatizzati di Microsoft 365 gestiscono la chiave di disponibilità a livello di programmazione. Questi servizi avviano operazioni automatizzate che non implicano mai l'accesso diretto alla chiave di disponibilità.

Lo scopo principale della chiave di disponibilità è fornire funzionalità di ripristino dalla perdita imprevista delle chiavi radice gestite dall'utente. La perdita potrebbe essere il risultato di una gestione errata o di un'azione dannosa. Se si perde il controllo delle chiavi radice, contattare il supporto tecnico Microsoft e Microsoft assisterà l'utente nel processo di ripristino usando la chiave di disponibilità. Userai la chiave di disponibilità per eseguire la migrazione a un nuovo criterio di crittografia dei dati con nuove chiavi radice di cui esegui il provisioning.

L'archiviazione e il controllo della chiave di disponibilità sono deliberatamente diversi dalle chiavi di Azure Key Vault per tre motivi:

- La chiave di disponibilità fornisce una funzionalità di ripristino, "break-glass" se il controllo su entrambe le chiavi di Azure Key Vault viene perso.
- La separazione dei controlli logici e delle posizioni di archiviazione sicure fornisce una difesa approfondita e protegge dalla perdita di tutte le chiavi e dei dati da un singolo attacco o punto di errore.
- La chiave di disponibilità offre una funzionalità di disponibilità elevata se i servizi di Microsoft 365 non riescono a raggiungere le chiavi ospitate in Azure Key Vault a causa di errori temporanei. Questa regola si applica solo alla crittografia dei servizi di Exchange Online e Skype for Business. I file di SharePoint Online, OneDrive for Business e Teams non usano mai la chiave di disponibilità, a meno che non venga indicato esplicitamente a Microsoft di avviare il processo di ripristino.

La condivisione della responsabilità di proteggere i dati, utilizzando una serie di protezioni e processi per la gestione delle chiavi, riduce infine il rischio che tutte le chiavi (e quindi i dati) andranno definitivamente perse o distrutte. Microsoft fornisce all'utente l'unica autorità per la disabilitazione o la distruzione della chiave di disponibilità quando si esce dal servizio. Da progettazione, nessuno di Microsoft ha accesso alla chiave di disponibilità: è accessibile solo dal codice di servizio di Microsoft 365.

Per ulteriori informazioni su come vengono protette le chiavi, vedere il Centro protezione [Microsoft.](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data)
  
## <a name="availability-key-uses"></a>Utilizzi delle chiavi di disponibilità

La chiave di disponibilità offre funzionalità di ripristino per gli scenari in cui un malintenzionato esterno o un insider malintenzionato ruba il controllo dell'insieme di credenziali delle chiavi o quando una gestione errata accidentale comporta la perdita delle chiavi radice. Questa funzionalità di ripristino si applica a tutti i servizi di Microsoft 365 compatibili con Customer Key. I singoli servizi usano la chiave di disponibilità in modo diverso. Microsoft 365 usa la chiave di disponibilità solo nei modi descritti di seguito.

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online e Skype for Business usa

Oltre alla funzionalità di ripristino, Exchange Online e Skype for Business usano la chiave di disponibilità per garantire la disponibilità dei dati durante problemi operativi temporanei o intermittenti relativi al servizio che accede alle chiavi radice. Quando il servizio non riesce a raggiungere una delle chiavi cliente in Azure Key Vault a causa di errori temporanei, il servizio usa automaticamente la chiave di disponibilità. Il servizio non passa mai direttamente alla chiave di disponibilità.

I sistemi automatizzati in Exchange Online e Skype for Business possono usare la chiave di disponibilità durante gli errori temporanei per supportare i servizi back-end automatizzati come antivirus, e-discovery, prevenzione della perdita dei dati, spostamenti delle cassette postali e indicizzazione dei dati.

### <a name="sharepointonlineonedriveforbusinessandteamsfiles-uses"></a>Utilizzo dei file di SharePoint Online, OneDrive for Business e Teams

Per i file di SharePoint Online, OneDrive for Business e Teams, la chiave di disponibilità non viene mai usata al di fuori della funzionalità di ripristino e i clienti devono indicare esplicitamente a Microsoft di avviare l'uso della chiave di disponibilità durante uno scenario di ripristino. Le operazioni di servizio automatizzate si basano esclusivamente sulle chiavi dei clienti nell'insieme di credenziali delle chiavi di Azure. Per informazioni dettagliate sul funzionamento della gerarchia delle chiavi per questi servizi, vedere Come i file di [SharePoint Online, OneDrive for Business](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key)e Teams usano la chiave di disponibilità.

## <a name="availability-key-security"></a>Sicurezza della chiave di disponibilità

Microsoft condivide con l'utente la responsabilità della protezione dei dati creando un'istanza della chiave di disponibilità e adottando misure estese per proteggerla. Microsoft non espone ai clienti il controllo diretto della chiave di disponibilità. Ad esempio, è possibile ruotare (ruotare) solo le chiavi di cui si è proprietari in Azure Key Vault. Per ulteriori informazioni, vedere [Roll or rotate a customer key or an availability key.](customer-key-availability-key-roll.md)

### <a name="availability-key-secret-stores"></a>Archivi segreti chiave di disponibilità

Microsoft protegge le chiavi di disponibilità in archivi segreti interni controllati dall'accesso, come Azure Key Vault per i clienti. I controlli di accesso vengono implementati per impedire agli amministratori Microsoft di accedere direttamente ai segreti contenuti all'interno. Le operazioni dell'archivio segreto, tra cui la rotazione e l'eliminazione delle chiavi, si verificano tramite comandi automatizzati che non implicano mai l'accesso diretto alla chiave di disponibilità. Le operazioni di gestione degli archivi segreti sono limitate a tecnici specifici e richiedono l'escalation dei privilegi tramite uno strumento interno, Lockbox. L'escalation dei privilegi richiede l'approvazione e la giustificazione del manager prima di essere concessa. Lockbox garantisce che l'accesso sia associato alla revoca automatica dell'accesso alla scadenza del periodo di tempo o alla disconnessione del tecnico.

**Le chiavi di disponibilità di Exchange Online** e Skype for Business vengono archiviate in un archivio segreto di Active Directory di Exchange Online. Le chiavi di disponibilità vengono archiviate in modo sicuro all'interno di contenitori specifici del tenant all'interno del controller di dominio di Active Directory. Questo percorso di archiviazione sicura è separato e isolato dall'archivio segreto dei file di SharePoint Online, OneDrive for Business e Teams.

Le chiavi di disponibilità dei file di **SharePoint Online, OneDrive for Business** e Teams vengono archiviate in un archivio segreto interno gestito dal team del servizio. Questo servizio di archiviazione segreti protetto include server front-end con endpoint applicazione e un database SQL database come back-end. Le chiavi di disponibilità vengono archiviate nel database di SQL e vengono incapsulate (crittografate) dalle chiavi di crittografia dell'archivio segreto che usano una combinazione di AES-256 e HMAC per crittografare la chiave di disponibilità in stato di inaltere. Le chiavi di crittografia dell'archivio segreto vengono archiviate in un componente isolato logicamente dello stesso database SQL e vengono ulteriormente crittografate con le chiavi RSA-2048 contenute nei certificati gestiti dall'autorità di certificazione (CA) Microsoft. Questi certificati vengono archiviati nei server front-end dell'archivio segreto che eseguono operazioni sul database.

### <a name="defense-in-depth"></a>Difesa approfondita

Microsoft usa una strategia di difesa approfondita per impedire agli utenti malintenzionati di influire sulla riservatezza, l'integrità o la disponibilità dei dati dei clienti archiviati in Microsoft Cloud. Vengono implementati controlli preventivi e investigativi specifici per proteggere l'archivio segreto e la chiave di disponibilità nell'ambito della strategia di sicurezza generale.

Microsoft 365 è progettato per evitare un uso improprio della chiave di disponibilità. Il livello applicazione è l'unico metodo con cui le chiavi, inclusa la chiave di disponibilità, possono essere usate per crittografare e decrittografare i dati. Solo il codice del servizio Microsoft 365 è in grado di interpretare e attraversare la gerarchia delle chiavi per le attività di crittografia e decrittografia. L'isolamento logico esiste tra le posizioni di archiviazione di Customer Keys, le chiavi di disponibilità, altre chiavi gerarchiche e i dati dei clienti. Questo isolamento riduce il rischio di esposizione dei dati nel caso in cui una o più posizioni siano compromesse. Ogni livello della gerarchia include funzionalità di rilevamento delle intrusioni 24x7 per proteggere i dati e i segreti archiviati.

I controlli di accesso vengono implementati per impedire l'accesso non autorizzato ai sistemi interni, inclusi gli archivi segreti delle chiavi di disponibilità. I tecnici Microsoft non hanno accesso diretto agli archivi segreti delle chiavi di disponibilità. Per ulteriori dettagli sui controlli di accesso, vedere [Controlli di accesso amministrativi in Microsoft 365.](https://docs.microsoft.com/Office365/securitycompliance/office-365-administrative-access-controls-overview)

I controlli tecnici impediscono al personale Microsoft di accedere ad account di servizio con privilegi elevati, che altrimenti potrebbero essere utilizzati dagli utenti malintenzionati per rappresentare i servizi Microsoft. Ad esempio, questi controlli impediscono l'accesso interattivo.

I controlli di monitoraggio e registrazione della sicurezza sono un'altra protezione approfondita implementata che attenua i rischi per i servizi Microsoft e i dati. I team di servizi Microsoft hanno distribuito soluzioni di monitoraggio attive che generano avvisi e log di controllo. Tutti i team di servizio caricano i log in un archivio centrale in cui i log vengono aggregati ed elaborati. Gli strumenti interni esaminano automaticamente i record per verificare che i servizi funzionino in uno stato ottimale, resiliente e protetto. Attività insolita viene contrassegnata per un'ulteriore revisione.

Qualsiasi evento di registro che indica una potenziale violazione dei criteri di sicurezza Microsoft viene immediatamente portato all'attenzione dei team di sicurezza Microsoft. La sicurezza di Microsoft 365 ha configurato avvisi per rilevare tentativi di accesso agli archivi segreti chiave di disponibilità. Gli avvisi vengono generati anche se il personale Microsoft tenta l'accesso interattivo agli account di servizio, che è proibito e protetto dai controlli di accesso. La sicurezza di Microsoft 365 rileva e avvisa anche le deviazioni del servizio Microsoft 365 dalle normali operazioni di base. I malfattori che tentano di utilizzare in modo improprio i servizi di Microsoft 365 attiverebbero avvisi che causano lo sfratto dell'autore del reato dall'ambiente cloud Microsoft.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>Utilizzare la chiave di disponibilità per il ripristino da una perdita di chiave

Se si perde il controllo delle chiavi cliente, la chiave di disponibilità consente di recuperare e crittografare di nuovo i dati.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Procedura di ripristino per Exchange Online e Skype for Business

Se si perde il controllo delle chiavi del cliente, la chiave di disponibilità offre la possibilità di recuperare i dati e riportare online le risorse di Microsoft 365. La chiave di disponibilità continua a proteggere i dati durante il ripristino. A livello elevato, per ripristinare completamente la perdita delle chiavi, è necessario creare una nuova protezione esecuzione programmi e spostare le risorse influenzate nel nuovo criterio.

Per crittografare i dati con nuove chiavi cliente, creare nuove chiavi in Azure Key Vault, creare una nuova protezione esecuzione programmi usando le nuove chiavi cliente, quindi assegnare la nuova protezione esecuzione programmi alle cassette postali attualmente crittografate con protezione esecuzione programmi precedente per cui le chiavi sono state perse o compromesse.

Questo processo di crittografia può richiedere fino a 72 ore. Questa è la durata standard quando si modifica protezione esecuzione programmi.
  
### <a name="recovery-procedure-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Procedura di ripristino per i file di SharePoint Online, OneDrive for Business e Teams

Per i file di SharePoint Online, OneDrive for Business e Teams, la chiave di disponibilità non viene mai usata al di fuori della funzionalità di ripristino. È necessario indicare esplicitamente a Microsoft di avviare l'uso della chiave di disponibilità durante uno scenario di ripristino. Per avviare il processo di ripristino, contattare Microsoft per attivare la chiave di disponibilità. Una volta attivata, la chiave di disponibilità viene usata automaticamente per decrittografare i dati, consentendoti di crittografare i dati con una protezione esecuzione programmi appena creata associata alle nuove chiavi cliente.  

Questa operazione è proporzionale al numero di siti nell'organizzazione. Dopo aver chiamato Microsoft per usare la chiave di disponibilità, è consigliabile essere completamente online entro circa quattro ore.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Utilizzo della chiave di disponibilità da parte di Exchange Online e Skype for Business

Quando si crea una protezione esecuzione programmi con Customer Key, Microsoft 365 genera una chiave dei criteri di crittografia dei dati associata a tale protezione. Il servizio crittografa la chiave protezione esecuzione programmi tre volte: una con ognuna delle chiavi del cliente e una con la chiave di disponibilità. Vengono archiviate solo le versioni crittografate della chiave protezione esecuzione programmi e una chiave protezione esecuzione programmi può essere decrittografata solo con le chiavi del cliente o la chiave di disponibilità. La chiave protezione esecuzione programmi viene quindi utilizzata per crittografare le chiavi delle cassette postali, che crittografa singole cassette postali.
  
Microsoft 365 segue questo processo per decrittografare e fornire dati quando i clienti usano il servizio:
  
1. Decrittografa la chiave protezione esecuzione programmi usando customer key.

2. Utilizzare la chiave decrittografata di Protezione esecuzione programmi per decrittografare una chiave della cassetta postale.

3. Utilizzare la chiave della cassetta postale decrittografata per decrittografare la cassetta postale stessa, consentendo di accedere ai dati all'interno della cassetta postale.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>Uso della chiave di disponibilità per i file di SharePoint Online, OneDrive for Business e Teams

L'architettura e l'implementazione di SharePoint Online e OneDrive for Business per Customer Key e la chiave disponibilità sono diverse da Exchange Online e Skype for Business.
  
Quando un'organizzazione passa alle chiavi gestite dal cliente, Microsoft 365 crea una chiave intermedia specifica dell'organizzazione (TIK). Microsoft 365 crittografa il CODICE TIK due volte, una con ognuna delle chiavi del cliente, e archivia le due versioni crittografate del TIK. Vengono archiviate solo le versioni crittografate del TIK e un TIK può essere decrittografato solo con le chiavi del cliente. Il codice TIK viene quindi usato per crittografare le chiavi del sito, che vengono quindi usate per crittografare le chiavi BLOB (denominate anche chiavi di blocco file). A seconda delle dimensioni del file, il servizio può dividere un file in più blocchi di file ognuno con una chiave univoca. I BLOB (blocchi di file) vengono crittografati con le chiavi BLOB e archiviati nel servizio di archiviazione BLOB di Microsoft Azure.
  
Microsoft 365 segue questo processo per decrittografare e fornire i file dei clienti quando i clienti usano il servizio:

1. Decrittografa il codice TIK usando customer key.

2. Utilizzare il codice TIK decrittografato per decrittografare una chiave del sito.

3. Utilizzare la chiave del sito decrittografata per decrittografare una chiave BLOB.

4. Utilizzare la chiave BLOB decrittografata per decrittografare il BLOB.

Microsoft 365 decrittografa un TIK emettendo due richieste di decrittografia per Azure Key Vault con un leggero offset. Il primo a terminare fornisce il risultato, annullando l'altra richiesta.
  
Nel caso in cui si perda l'accesso alle chiavi dei clienti, Microsoft 365 crittografa anche il CODICE TIK con una chiave di disponibilità e lo archivia insieme ai CODICI AKI crittografati con ogni chiave del cliente. Il CODICE TIK crittografato con la chiave di disponibilità viene usato solo quando il cliente chiama Microsoft per integrare il percorso di ripristino quando ha perso l'accesso alle chiavi, in modo dannoso o accidentale.
  
Per motivi di disponibilità e scalabilità, i TIK decrittografati vengono memorizzati nella cache in una cache di memoria limitata nel tempo. Due ore prima della scadenza di una cache TIK, Microsoft 365 tenta di decrittografare ogni TIK. La decrittografia dei TIK estende la durata della cache. Se la decrittografia TIK non riesce per un periodo di tempo significativo, Microsoft 365 genera un avviso per notificare la progettazione prima della scadenza della cache. Solo se il cliente chiama Microsoft, Microsoft 365 avvierà l'operazione di ripristino, che implica la decrittografia del CODICE TIK con la chiave di disponibilità archiviata nell'archivio segreto di Microsoft e l'onboarding del tenant di nuovo usando il TIK decrittografato e un nuovo set di chiavi dell'Azure Key Vault fornite dal cliente.
  
A partire da oggi, Customer Key è coinvolto nella catena di crittografia e decrittografia dei dati dei file di SharePoint Online archiviati nell'archivio BLOB di Azure, ma non nelle voci di elenco o nei metadati di SharePoint Online archiviati nel database di SQL. Microsoft 365 non usa la chiave di disponibilità per i file di Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e Teams diversi dal caso descritto in precedenza, che è avviato dal cliente. L'accesso umano ai dati dei clienti è protetto da Customer Lockbox.

## <a name="availability-key-triggers"></a>Trigger delle chiavi di disponibilità

Microsoft 365 attiva la chiave di disponibilità solo in circostanze specifiche. Queste circostanze sono diverse in base al servizio.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Trigger per Exchange Online e Skype for Business
  
1. Microsoft 365 legge protezione esecuzione programmi a cui è assegnata la cassetta postale per determinare la posizione delle due chiavi cliente in Azure Key Vault.

2. Microsoft 365 sceglie in modo casuale una delle due chiavi cliente da Protezione esecuzione programmi e invia una richiesta ad Azure Key Vault per annullare il wrapping della chiave dep usando customer key.

3. Se la richiesta di annullamento del wrapping della chiave protezione esecuzione programmi tramite Customer Key ha esito negativo, Microsoft 365 invia una seconda richiesta ad Azure Key Vault, questa volta indicando di usare la (seconda) chiave cliente alternativa.

4. Se la seconda richiesta di annullamento del wrapping della chiave Protezione esecuzione programmi tramite Customer Key ha esito negativo, Microsoft 365 esamina i risultati di entrambe le richieste.

    - Se l'esame determina che le richieste non sono riuscite a restituire un errore di sistema:

       - Microsoft 365 attiva la chiave di disponibilità per decrittografare la chiave protezione esecuzione programmi.

       - Microsoft 365 utilizza quindi la chiave Protezione esecuzione programmi per decrittografare la chiave della cassetta postale e completare la richiesta dell'utente. 

       - In questo caso, Azure Key Vault non è in grado di rispondere o non è raggiungibile a causa di un errore temporaneo.

    - Se l'esame determina che le richieste non sono riuscite a restituire ACCESS DENIED:

       - Ciò significa che sono state intraprese azioni intenzionali, accidentali o dannose per rendere non disponibili le chiavi del cliente (ad esempio, durante il processo di eliminazione dei dati come parte dell'uscita dal servizio).

       - In questo caso, la chiave di disponibilità verrà utilizzata solo per le azioni di sistema e non per le azioni dell'utente, la richiesta dell'utente avrà esito negativo e l'utente riceverà un messaggio di errore.

>[!IMPORTANT]
>Il codice del servizio Microsoft 365 ha sempre un token di accesso valido per il motivo dei dati dei clienti per fornire servizi cloud a valore aggiunto. Pertanto, fino a quando la chiave di disponibilità non viene eliminata, può essere utilizzata come fallback per le azioni avviate da, o interne a, Exchange Online e Skype for Business, ad esempio la creazione dell'indice di ricerca o lo spostamento delle cassette postali. Questo vale sia per gli ERRORI temporanei che per le richieste ACCESS DENIED per Azure Key Vault.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Trigger per i file di SharePoint Online, OneDrive for Business e Teams

Per i file di SharePoint Online, OneDrive for Business e Teams, la chiave di disponibilità non viene mai usata al di fuori della funzionalità di ripristino e i clienti devono indicare esplicitamente a Microsoft di avviare l'uso della chiave di disponibilità durante uno scenario di ripristino.

## <a name="audit-logs-and-the-availability-key"></a>Registri di controllo e chiave di disponibilità

I sistemi automatizzati in Microsoft 365 elaborano tutti i dati mentre attraversano il sistema per fornire servizi cloud, ad esempio anti-virus, e-discovery, prevenzione della perdita dei dati e indicizzazione dei dati. Microsoft 365 non genera log visibili al cliente per questa attività. Inoltre, il personale Microsoft non accede ai dati come parte di queste normali operazioni di sistema.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Registrazione delle chiavi di disponibilità di Exchange Online e Skype for Business

Quando Exchange Online e Skype for Business accedono alla chiave di disponibilità per fornire il servizio, Microsoft 365 pubblica i log visibili ai clienti accessibili dal Centro sicurezza e conformità. Ogni volta che il servizio utilizza la chiave di disponibilità, viene generato un record del registro di controllo per l'operazione della chiave di disponibilità. Un nuovo tipo di record denominato "Customer Key Service Encryption" con tipo di attività "Fallback alla chiave di disponibilità" consente agli amministratori di filtrare i risultati della ricerca nel [log](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) di controllo unificato per visualizzare i record delle chiavi di disponibilità.

I record di registro includono attributi quali data, ora, attività, ID organizzazione e ID criteri di crittografia dei dati. Il record è disponibile come parte dei log di controllo unificati ed è accessibile dalla scheda Ricerca log di controllo del Centro sicurezza & conformità.

![Ricerca di eventi chiave di disponibilità nel log di controllo](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

I record delle chiavi di disponibilità di Exchange Online e Skype for Business usano lo [schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) comune office 365 Management Activity con parametri personalizzati aggiunti: ID criterio, ID versione chiave ambito e ID richiesta.

![Parametri personalizzati della chiave di disponibilità](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>Registrazione delle chiavi di disponibilità dei file di SharePoint Online, OneDrive for Business e Teams

La registrazione della chiave di disponibilità non è ancora disponibile per questi servizi. Per i file di SharePoint Online, OneDrive for Business e Teams, la chiave di disponibilità viene attivata solo da Microsoft, se richiesto dall'utente, a scopo di ripristino. Di conseguenza, si conosce già ogni evento in cui viene usata la chiave di disponibilità per questi servizi.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>Chiave di disponibilità nella gerarchia customer key
  
Microsoft 365 usa la chiave di disponibilità per eseguire il wrapping del livello di chiavi più basso nella gerarchia delle chiavi stabilita per la crittografia del servizio customer key. Tra i servizi esistono gerarchie chiave diverse. Gli algoritmi delle chiavi sono inoltre diversi tra le chiavi di disponibilità e altre chiavi nella gerarchia di ogni servizio applicabile. Gli algoritmi delle chiavi di disponibilità utilizzati dai diversi servizi sono i seguenti:

- Le chiavi di disponibilità di Exchange Online e Skype for Business usano AES-256.

- Le chiavi di disponibilità dei file di SharePoint Online, OneDrive for Business e Teams usano RSA-2048.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Crittografia utilizzata per crittografare le chiavi per Exchange Online e Skype for Business

![Crittografie di crittografia per Exchange Online Customer Key](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>Crittografia utilizzata per crittografare le chiavi per SharePoint Online e OneDrive for Business

![Crittografia delle crittografie per la chiave del cliente di SharePoint Online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Articoli correlati

- [Crittografia del servizio con Customer Key](customer-key-overview.md)

- [Configurare Customer Key](customer-key-set-up.md)

- [Gestire Customer Key](customer-key-manage.md)

- [Implementare o distribuire una Customer Key o una chiave di disponibilità](customer-key-availability-key-roll.md)
