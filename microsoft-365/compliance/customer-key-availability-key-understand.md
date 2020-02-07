---
title: Informazioni sulla chiave di disponibilità per la chiave del cliente di Office 365
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
description: Informazioni sulla chiave di disponibilità utilizzata per recuperare le chiavi dei clienti di Office 365 perse.
ms.openlocfilehash: a4d0bdecfeddb83ffbe47f397f2bda646138b081
ms.sourcegitcommit: b22d6dea2768679428d512ea2bbbdf8748f71712
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845365"
---
# <a name="learn-about-the-availability-key-for-office-365-customer-key"></a>Informazioni sulla chiave di disponibilità per la chiave del cliente di Office 365

La chiave di disponibilità è una chiave radice generata e provisioning automaticamente quando si crea un criterio di crittografia dei dati. Office 365 archivia e protegge il codice di disponibilità. Il codice di disponibilità è funzionalmente analogo alle due chiavi radice fornite per la crittografia del servizio con la chiave del cliente. Il tasto disponibilità esegue il wrapping delle chiavi di un livello inferiore nella gerarchia delle chiavi. A differenza delle chiavi fornite e gestite in Azure Key Vault, non è possibile accedere direttamente alla chiave di disponibilità. Servizi automatizzati di Office 365 gestire la chiave di disponibilità utilizzando i cmdlet di PowerShell. Questi cmdlet avviano operazioni automatizzate che non coinvolgono mai l'accesso diretto al codice di disponibilità.

Lo scopo principale del codice di disponibilità è fornire funzionalità di ripristino dalla perdita imprevista delle chiavi radice gestite. La perdita potrebbe essere il risultato di una cattiva gestione o di un'azione dannosa. Se si perde il controllo delle chiavi principali, contattare il supporto tecnico Microsoft e Microsoft fornisce assistenza tramite il processo di ripristino tramite il codice di disponibilità. Si utilizzerà la chiave di disponibilità per eseguire la migrazione a un nuovo criterio di crittografia dei dati con le nuove chiavi di root provisioning.

Lo spazio di archiviazione e il controllo della chiave di disponibilità sono deliberatamente diversi dai tasti del Vault Key di Azure per tre motivi:

- Il tasto disponibilità fornisce una funzionalità di ripristino, ovvero "Break-Glass", se il controllo su entrambe le chiavi del Vault Key di Azure viene perso.
- La separazione dei controlli logici e delle posizioni di archiviazione sicure fornisce una difesa approfondita e protegge dalla perdita di tutte le chiavi e dei dati, da un singolo attacco o da un punto di errore.
- La chiave di disponibilità fornisce una funzionalità di disponibilità elevata se i servizi di Office 365 non sono in grado di raggiungere le chiavi ospitate in Azure Key Vault a causa di errori temporanei. Questa regola si applica solo alla crittografia del servizio Exchange Online e Skype for business. I file di SharePoint Online, OneDrive for business e teams non utilizzano mai il codice di disponibilità, a meno che non si indichi esplicitamente a Microsoft di avviare il processo di ripristino.

Condividendo la responsabilità di proteggere i dati, utilizzando una vasta gamma di protezioni e processi per la gestione delle chiavi, si riduce il rischio che tutte le chiavi (e quindi i dati) vengano definitivamente perse o distrutte. Microsoft fornisce l'autorità esclusiva per la disabilitazione o la distruzione del codice di disponibilità quando si lascia il servizio. In base alla progettazione, nessuno di Microsoft ha accesso alla chiave di disponibilità: è accessibile solo dal codice del servizio di Office 365.

Per ulteriori informazioni sulla protezione delle chiavi, vedere il [Centro protezione Microsoft](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) .
  
## <a name="availability-key-uses"></a>Utilizzo delle chiavi di disponibilità

La chiave di disponibilità fornisce funzionalità di ripristino per gli scenari in cui un malfattore esterno o un insider dannoso ruba il controllo del Vault chiave, o quando la cattiva gestione accidentale determina la perdita delle chiavi principali. Questa funzionalità di ripristino si applica a tutti i servizi di Office 365 compatibili con la chiave del cliente. I singoli servizi utilizzano la chiave di disponibilità in modo diverso. Office 365 utilizza solo la chiave di disponibilità nei modi descritti di seguito.

### <a name="exchange-online-and-skype-for-business-uses"></a>Utilizzo di Exchange Online e Skype for business

Oltre alla funzionalità di ripristino, Exchange Online e Skype for business utilizzano la chiave di disponibilità per garantire la disponibilità dei dati in caso di problemi operativi transitori o intermittenti relativi al servizio che accede alle chiavi principali. Quando il servizio non è in grado di raggiungere nessuna delle chiavi del cliente in Azure Key Vault a causa di errori transitori, il servizio utilizza automaticamente il codice di disponibilità. Il servizio non passa mai direttamente al codice di disponibilità.

I sistemi automatizzati in Exchange Online e Skype for business possono utilizzare la chiave di disponibilità durante gli errori temporanei per supportare i servizi back-end automatici, ad esempio antivirus, e-Discovery, la prevenzione della perdita di dati, gli spostamenti delle cassette postali e l'indicizzazione dei dati.

### <a name="sharepointonlineonedriveforbusinessandteamsfiles-uses"></a>Utilizzo dei file di SharePoint Online, OneDrive for business e teams

Per i file di SharePoint Online, OneDrive for business e teams, la chiave di disponibilità non viene mai utilizzata al di fuori della funzionalità di ripristino e i clienti devono indicare esplicitamente a Microsoft di avviare l'utilizzo della chiave di disponibilità durante uno scenario di ripristino. Le operazioni di servizio automatizzate si basano esclusivamente sulle chiavi dei clienti in Azure Key Vault. Per informazioni approfondite su come funziona la gerarchia delle chiavi per questi servizi, vedere [How SharePoint Online, OneDrive for business e teams files use the availability Key](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key).

## <a name="availability-key-security"></a>Sicurezza delle chiavi di disponibilità

Microsoft condivide la responsabilità della protezione dei dati con l'utente creando un'istanza del codice di disponibilità e adottando misure estese per proteggerlo. Microsoft non espone il controllo diretto della chiave di disponibilità ai clienti. Ad esempio, è possibile eseguire il rollback solo delle chiavi di cui si dispone in Azure Key Vault. Per ulteriori informazioni, vedere [Roll or rotate a Customer Key o a availability Key](customer-key-availability-key-roll.md).

### <a name="availability-key-secret-stores"></a>Archivi segreti chiave di disponibilità

Microsoft protegge le chiavi di disponibilità negli archivi segreti interni controllati da Access, come il Vault Key Azure con accesso ai clienti. Implementiamo i controlli di accesso per impedire agli amministratori di Microsoft di accedere direttamente ai segreti contenuti all'interno. Le operazioni di archiviazione segrete, incluse la rotazione, l'eliminazione e il recupero delle chiavi, avvengono tramite comandi automatici che non coinvolgono mai l'accesso diretto al codice di disponibilità. L'accesso per regolare questi comandi è limitato a specifici ingegneri e richiede l'escalation dei privilegi tramite uno strumento interno, protetto. L'escalation dei privilegi richiede l'approvazione e la giustificazione del responsabile prima di essere concessa. L'archivio protetto garantisce che l'accesso sia associato al tempo associato alla revoca di accesso automatico al momento della scadenza o del logout del tecnico.

I tasti di disponibilità di **Exchange Online e Skype for business** sono archiviati in un archivio segreto di Active Directory. Exchange Online Active Directory è costituito da foreste di gestione che instradano foreste di traffico e capacità che contengono oggetti, identità e dati. Le foreste di capacità sono costituite da foreste account e foreste di risorse. Gli insiemi di strutture account dispongono di controller di dominio con più capacità sincronizzati tra loro. I tasti di disponibilità sono archiviati in modo sicuro all'interno dei controller di dominio Capacity. Questo percorso di archiviazione sicura è separato e isolato dall'archivio segreto di SharePoint Online, OneDrive for business e dei file teams.

Le chiavi di disponibilità dei **file di SharePoint Online, OneDrive for business e teams** sono archiviate in un archivio segreto interno gestito dal team di servizio. Questo servizio di archiviazione con protezione e segreti ha server front-end con endpoint applicazione e un database SQL come back-end. Le chiavi di disponibilità sono archiviate nel database SQL e vengono avvolte (crittografate) dalle chiavi di crittografia dell'archivio segreto che utilizzano una combinazione di AES-256 e HMAC per crittografare la chiave di disponibilità a riposo. Le chiavi di crittografia dell'archivio segreto sono archiviate in un componente logicamente isolato dello stesso database SQL e vengono ulteriormente crittografate con le chiavi RSA-2048 contenute nei certificati gestiti dall'autorità di certificazione (CA) di Microsoft. Questi certificati vengono archiviati nei server front-end dell'archivio segreto che eseguono operazioni sul database.

### <a name="defense-in-depth"></a>Difesa in profondità

Microsoft impiega una strategia di difesa approfondita per impedire agli utenti malintenzionati di influenzare la riservatezza, l'integrità o la disponibilità dei dati del cliente archiviati nel cloud Microsoft. Sono stati implementati controlli preventivi e detective specifici per proteggere l'archivio segreto e la chiave di disponibilità nell'ambito della strategia di sicurezza generale.

Office 365 è stato creato per impedire l'uso improprio del codice di disponibilità. Il livello dell'applicazione è l'unico metodo tramite il quale le chiavi, incluso il codice di disponibilità, possono essere utilizzate per crittografare e decrittografare i dati. Solo il codice di servizio di Office 365 è in grado di interpretare e attraversare la gerarchia delle chiavi per le attività di crittografia e decrittografia. Se un amministratore di Microsoft malintenzionato dovesse eludere i controlli per estrarre una chiave di disponibilità dall'archivio segreto, la chiave sarebbe inutilizzabile per accedere ai dati dei clienti. L'isolamento logico esiste tra le posizioni di archiviazione delle chiavi dei clienti, delle chiavi di disponibilità, di altre chiavi gerarchiche e dei dati del cliente. Questo isolamento attenua il rischio di esposizione dei dati nel caso in cui una o più posizioni vengano compromesse. Ogni layer della gerarchia è stato costruito in funzionalità di rilevamento delle intrusioni 24x7 per proteggere i dati e i segreti.

I controlli di accesso vengono implementati per impedire l'accesso non autorizzato ai sistemi interni, compresi gli archivi segreti chiave di disponibilità. Gli ingegneri Microsoft non dispongono dell'accesso diretto agli archivi segreti chiave di disponibilità. Per ulteriori informazioni sui controlli di accesso, consultare [controlli di accesso amministrativo in Office 365](https://docs.microsoft.com/Office365/securitycompliance/office-365-administrative-access-controls-overview).

I controlli tecnici impediscono ai dipendenti Microsoft di accedere a account di servizio con privilegi elevati, che potrebbero altrimenti essere utilizzati dagli utenti malintenzionati per rappresentare i servizi di Office 365. Questi controlli, ad esempio, impediscono l'accesso interattivo.

La registrazione di sicurezza e i controlli di monitoraggio rappresentano un'altra protezione per la difesa approfondita implementata che consente di attenuare i rischi per i servizi Microsoft e i dati. I team di servizi Microsoft hanno distribuito soluzioni di monitoraggio attivo che generano avvisi e registri di controllo. Tutti i team di servizio caricano i propri registri in un archivio centrale in cui vengono aggregati ed elaborati i registri. Gli strumenti interni esaminano automaticamente i record per verificare che i servizi funzionino in uno stato ottimale, resiliente e sicuro. L'attività insolita è contrassegnata per ulteriori riesami.

Qualsiasi evento di registro che indichi una possibile violazione dei criteri di sicurezza Microsoft viene immediatamente portato all'attenzione dei team di sicurezza di Microsoft. La sicurezza di Office 365 ha configurato avvisi per rilevare il tentativo di accesso agli archivi segreti chiave di disponibilità. Gli avvisi vengono generati anche se i membri del personale Microsoft tentano l'accesso interattivo agli account di servizio, che sono vietati e protetti dai controlli di accesso. La sicurezza di Office 365 rileva e allerta anche le deviazioni del servizio Office 365 dalle normali operazioni di base. Malfattori il tentativo di abusare dei servizi di Office 365 innescherà gli avvisi che causano l'eliminazione del trasgressore dall'ambiente cloud Microsoft.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>Utilizzare la chiave di disponibilità per eseguire il ripristino dalla perdita di chiave

Se si perde il controllo delle chiavi dei clienti, la chiave di disponibilità fornisce la possibilità di recuperare e rieseguire la crittografia dei dati.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Procedura di ripristino per Exchange Online e Skype for business

Se si perde il controllo delle chiavi dei clienti, la chiave di disponibilità fornisce la possibilità di recuperare i dati e di riportare le risorse di Office 365 ripercussioni online. Il codice di disponibilità continua a proteggere i dati durante il ripristino. A livello elevato, per il ripristino completo dalla perdita di chiave, è necessario creare un nuovo DEP e spostare le risorse interessate al nuovo criterio.

Per crittografare i dati con le nuove chiavi dei clienti, creare nuove chiavi in Azure Key Vault, creare una nuova funzionalità di protezione esecuzione programmi utilizzando le nuove chiavi del cliente, quindi assegnare il nuovo DEP alle cassette postali attualmente crittografate con la precedente DEP per la quale le chiavi sono state perse o compromesse.

Questo processo di riesecuzione della crittografia può richiedere fino a 72 ore. Questa è la durata standard quando si modifica una funzionalità di protezione esecuzione programmi.
  
### <a name="recovery-procedure-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Procedura di ripristino per i file di SharePoint Online, OneDrive for business e teams

Per i file di SharePoint Online, OneDrive for business e teams, la chiave di disponibilità non viene mai utilizzata al di fuori della funzionalità di ripristino. È necessario indicare in modo esplicito a Microsoft di avviare l'utilizzo della chiave di disponibilità durante uno scenario di ripristino. Per iniziare il processo di ripristino, contattare Microsoft per attivare il codice di disponibilità. Una volta attivato, il tasto di disponibilità viene automaticamente utilizzato per decrittografare i dati che consentono di crittografare i dati con una protezione esecuzione programmi appena creata associata a nuove chiavi del cliente.  

Questa operazione è proporzionale al numero di siti nell'organizzazione. Dopo aver chiamato Microsoft per l'utilizzo della chiave di disponibilità, è necessario essere completamente online entro circa quattro ore.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Come Exchange Online e Skype for business utilizzano il codice di disponibilità

Quando si crea una funzionalità di protezione esecuzione programmi con il codice cliente, Office 365 genera una chiave del criterio di crittografia dei dati (chiave DEP) associata alla funzionalità di protezione esecuzione programmi. Il servizio crittografa il tasto DEP tre volte: una volta con ognuna delle chiavi del cliente e una volta con il tasto disponibilità. Solo le versioni crittografate del tasto DEP sono archiviate e una chiave DEP può essere decrittografata solo con le chiavi del cliente o con il tasto disponibilità. La chiave DEP viene quindi utilizzata per crittografare le chiavi delle cassette postali, che vengono quindi utilizzate per crittografare le singole cassette postali.
  
Office 365 segue questo processo per decrittografare e fornire dati quando i clienti utilizzano il servizio:
  
1. Decrittografare la chiave DEP utilizzando il codice "Customer Key".

2. Utilizzare la chiave DEP decrittografata per decrittografare una chiave della cassetta postale.

3. Utilizzare la chiave della cassetta postale decrittografata per decrittografare la cassetta postale stessa, consentendo all'utente di accedere ai dati all'interno della cassetta postale.

Office 365 decrittografa un tasto DEP emettendo due richieste di decrittografia in Azure Key Vault con una leggera offset. La prima per completare fornisce il risultato, annullando l'altra richiesta.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>Utilizzo del codice di disponibilità dei file di SharePoint Online, OneDrive for business e teams

L'architettura e l'implementazione di SharePoint Online e OneDrive for business per i Key Key e la disponibilità dei clienti sono diverse da Exchange Online e Skype for business.
  
Quando un'organizzazione si sposta su chiavi gestite dal cliente, Office 365 crea una chiave intermedia specifica del tenant. Office 365 crittografa il tick due volte, una volta con ognuna delle chiavi del cliente, e archivia le due versioni crittografate del tick. Vengono memorizzate solo le versioni crittografate del tick e un tick può essere decrittografato solo con le chiavi del cliente. L'oggetto Tick viene quindi utilizzato per crittografare le chiavi del sito, che vengono quindi utilizzate per crittografare le chiavi BLOB (denominate anche chiavi di blocco dei file). A seconda delle dimensioni del file, il servizio può suddividere un file in più blocchi di file ognuno con una chiave univoca. Gli oggetti BLOB (blocchi di file) vengono crittografati con le chiavi BLOB e archiviati nel servizio di archiviazione BLOB di Microsoft Azure.
  
Office 365 segue questo processo per decrittografare e fornire i file dei clienti quando i clienti utilizzano il servizio:

1. Decrittografare l'elemento tick utilizzando il codice "Customer Key".

2. Per decrittografare una chiave del sito, utilizzare l'elemento di crittografia decrittografato.

3. Utilizzare la chiave del sito decrittografato per decrittografare una chiave BLOB.

4. Utilizzare la chiave BLOB decrittografata per decrittografare il BLOB.

Office 365 decrittografa un tick emettendo due richieste di decrittografia nel Vault Key di Azure con una leggera offset. La prima per completare fornisce il risultato, annullando l'altra richiesta.
  
Nel caso in cui si perda l'accesso alle chiavi dei clienti, Office 365 crittografa anche l'oggetto Tick con una chiave di disponibilità e lo archivia insieme all'TIKs crittografato con ogni chiave del cliente. L'utente crittografato con la chiave di disponibilità viene utilizzato solo quando il cliente chiama Microsoft per integrare il percorso di ripristino quando ha perso l'accesso alle chiavi, in modo dannoso o accidentale.
  
Per motivi di disponibilità e scalabilità, le TIKs decrittografate vengono memorizzate nella cache in una memoria limitata nel tempo. Due ore prima che la cache di un sistema di posta in scadenza venga scaduta, Office 365 tenta di decrittografare ogni tick. La decrittografia di TIKs consente di estendere la durata della cache. Se la decrittografia di tick ha esito negativo per un periodo di tempo significativo, Office 365 genera un avviso per notificare l'ingegnerizzazione prima della scadenza della cache. Solo se il cliente chiama Microsoft, Office 365 avvierà l'operazione di ripristino, che implica la decrittografia del tick con la chiave di disponibilità memorizzata nell'archivio segreto di Microsoft e l'onboarding del tenant utilizzando di nuovo il tipo di dati decrittografato e un nuovo set di chiavi del Vault Key di Azure fornite dal cliente.
  
A questo punto, la chiave del cliente è coinvolta nella catena di crittografia e decrittografia dei dati del file di SharePoint Online archiviati nell'archivio BLOB di Azure, ma non elementi o metadati dell'elenco di SharePoint Online archiviati nel database SQL. Office 365 non utilizza la chiave di disponibilità per Exchange Online, Skype for business, SharePoint Online, OneDrive for business e i file di team diversi da quelli descritti in alto, che sono stati avviati dal cliente. L'accesso umano ai dati dei clienti è protetto dall'archivio protetto dei clienti.

## <a name="availability-key-triggers"></a>Trigger di chiave di disponibilità

Office 365 attiva la chiave di disponibilità solo in determinate circostanze. Tali circostanze variano in base al servizio.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Trigger per Exchange Online e Skype for business
  
1. Office 365 legge la funzionalità DEP a cui è assegnata la cassetta postale per determinare la posizione delle due chiavi del cliente in Azure Key Vault.

2. Office 365 sceglie casualmente una delle due chiavi del cliente dalla DEP e invia una richiesta al Vault Key di Azure per annullare il wrapping del tasto DEP utilizzando il codice "Customer Key".

3. Se la richiesta di annullare il wrapping del tasto DEP tramite la chiave Customer ha esito negativo, Office 365 invierà una seconda richiesta a Azure Key Vault, questa volta per istruirlo sull'utilizzo del codice cliente alternativo (secondo).

4. Se la seconda richiesta di annullare il wrapping del tasto DEP tramite la chiave Customer ha esito negativo, in Office 365 vengono esaminati i risultati di entrambe le richieste.

    - Se l'esame determina che le richieste non hanno restituito un errore di sistema:

       - Office 365 attiva la chiave di disponibilità per decrittografare il tasto DEP.

       - In Office 365 viene quindi utilizzato il tasto DEP per decrittografare la chiave della cassetta postale e completare la richiesta dell'utente. 

       - In questo caso, l'archiviazione delle chiavi di Azure non è in grado di rispondere o irraggiungibile a causa di un errore temporaneo.

    - Se l'esame determina che le richieste non sono state restituite con accesso negato:

       - Questo significa che è stata eseguita un'azione deliberata, involontaria o dannosa per eseguire il rendering delle chiavi del cliente non disponibili, ad esempio durante il processo di eliminazione dei dati come parte dell'uscita del servizio.

       - In questo caso, la chiave di disponibilità non verrà utilizzata, la richiesta dell'utente avrà esito negativo e l'utente riceverà un messaggio di errore.

>[!IMPORTANT]
>Il codice di servizio di Office 365 ha sempre un token di accesso valido per il ragionamento sui dati dei clienti per fornire servizi cloud con aggiunta di valore. Pertanto, finché il codice di disponibilità non è stato eliminato, può essere utilizzato come fallback per le azioni avviate da, o da interno a, Exchange Online e Skype for business, ad esempio la creazione di un indice di ricerca o lo spostamento delle cassette postali. Questo vale sia per gli errori temporanei sia per le richieste di accesso negato a Azure Key Vault.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Trigger per i file di SharePoint Online, OneDrive for business e teams

Per i file di SharePoint Online, OneDrive for business e teams, la chiave di disponibilità non viene mai utilizzata al di fuori della funzionalità di ripristino e i clienti devono indicare esplicitamente a Microsoft di avviare l'utilizzo della chiave di disponibilità durante uno scenario di ripristino.

## <a name="audit-logs-and-the-availability-key"></a>Registri di controllo e chiave di disponibilità

I sistemi automatizzati in Office 365 elaborano tutti i dati che scorre attraverso il sistema per fornire servizi cloud, ad esempio, antivirus, e-Discovery, prevenzione della perdita di dati e indicizzazione dei dati. Office 365 non genera registri visibili al cliente per questa attività. Inoltre, il personale Microsoft non accede ai dati nell'ambito di queste normali operazioni di sistema.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Registrazione chiave della disponibilità di Exchange Online e Skype for business

Exchange Online e Skype for business utilizzano automaticamente la chiave di disponibilità durante gli errori transitori. Quando si verifica questo fallback, Office 365 pubblica i log visibili al cliente accessibili dal centro sicurezza e conformità. Un record del registro di controllo per l'operazione di chiave di disponibilità viene generato ogni volta che questi servizi passano all'utilizzo del tasto disponibilità. Un nuovo tipo di record denominato "Customer Key Service Encryption" con tipo di attività "fallback alla chiave di disponibilità" consente agli amministratori di filtrare i risultati della ricerca del [Registro di controllo unificato](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) per visualizzare i record delle chiavi di disponibilità. Il record della chiave di disponibilità viene generato solo quando viene utilizzata la chiave del cliente per accedere ai dati e non per le chiavi gestite dal servizio Microsoft.

I record di log includono attributi quali data, ora, attività, ID organizzazione e ID del criterio di crittografia dei dati. Il record è disponibile come parte dei log di controllo unificato di Office 365 ed è accessibile dalla scheda ricerca del registro di controllo del Centro sicurezza e conformità di Office 365.

![Ricerca del registro di controllo per gli eventi chiave di disponibilità](media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

I record chiave di disponibilità di Exchange Online e Skype for business utilizzano lo [schema comune](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) attività di gestione di Office 365 con parametri personalizzati aggiunti: ID criterio, ID versione della chiave dell'ambito e ID richiesta.

![Parametri personalizzati della chiave di disponibilità](media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>Registrazione delle chiavi di disponibilità dei file di SharePoint Online, OneDrive for business e teams

La registrazione delle chiavi di disponibilità non è ancora disponibile per questi servizi. Per i file di SharePoint Online, OneDrive for business e teams, la chiave di disponibilità è attivata solo da Microsoft, se richiesto dall'utente, per il ripristino. Di conseguenza, si conosce già ogni evento in cui viene utilizzato il codice di disponibilità per questi servizi.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>Chiave di disponibilità nella gerarchia delle chiavi del cliente
  
Office 365 utilizza la chiave di disponibilità per eseguire il wrapping del livello delle chiavi più in basso nella gerarchia chiave stabilita per la crittografia del servizio chiave del cliente. Tra i servizi esistono gerarchie di chiavi diverse. Gli algoritmi chiave differiscono anche tra le chiavi di disponibilità e altre chiavi della gerarchia di ogni servizio applicabile. Gli algoritmi chiave di disponibilità utilizzati dai diversi servizi sono i seguenti:

- I tasti di disponibilità di Exchange Online e Skype for business utilizzano AES-256.

- Le chiavi di disponibilità dei file di SharePoint Online, OneDrive for business e teams utilizzano RSA-2048.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Crittografia cifratura utilizzata per crittografare le chiavi per Exchange Online e Skype for business

![Crittografia cifratura per la chiave del cliente di Exchange Online](media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>Crittografia crittografica utilizzata per crittografare le chiavi di SharePoint Online e OneDrive for business

![Crittografia cifratura per la chiave del cliente di SharePoint Online](media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Articoli correlati

- [Crittografia del servizio con la chiave del cliente per Office 365](customer-key-overview.md)

- [Configurare la chiave cliente per Office 365](customer-key-set-up.md)

- [Gestire la chiave del cliente per Office 365](customer-key-manage.md)

- [Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità](customer-key-availability-key-roll.md)
