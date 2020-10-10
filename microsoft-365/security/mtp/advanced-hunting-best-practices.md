---
title: Procedure consigliate per una query di ricerca avanzata in Microsoft Threat Protection
description: Informazioni su come creare query di ricerca di minacce veloci, efficienti e prive di errori con la ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, schema, kusto, evitare il timeout, linee di comando, Process ID, Optimize, Best practice, Parse, join, riepilogare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 522f4900bb9d2746c16eaf2172d756e2517e75c3
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412251"
---
# <a name="advanced-hunting-query-best-practices"></a>Procedure consigliate per query in Ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

Applicare questi suggerimenti per ottenere risultati più velocemente ed evitare timeout durante l'esecuzione di query complesse. Per altre informazioni su come migliorare le prestazioni della query, vedere [procedure consigliate per le query di Esplora dati](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-limits"></a>Informazioni sui limiti relativi alle risorse della CPU
A seconda delle dimensioni, ogni tenant ha accesso a una quantità di risorse della CPU allocata per l'esecuzione di query di ricerca avanzate. Per informazioni dettagliate sui vari limiti di servizio, [vedere informazioni sui limiti di caccia avanzati](advanced-hunting-limits.md).

I clienti che eseguono più query regolarmente devono tenere conto dei consumi e applicare le indicazioni di ottimizzazione in questo articolo per ridurre al minimo le interruzioni derivanti dal superamento dei limiti.

## <a name="general-optimization-tips"></a>Suggerimenti per l'ottimizzazione generale

- **Dimensione nuove query**: se si ritiene che una query restituirà un set di risultati di grandi dimensioni, valutarla prima utilizzando l' [operatore Count](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator). Utilizzare [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) o il relativo sinonimo `take` per evitare set di risultati di grandi dimensioni.
- **Applicare i filtri all'inizio**: applicare filtri temporali e altri filtri per ridurre il set di dati, soprattutto prima di utilizzare le funzioni di trasformazione e analisi, ad esempio [substring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [Replace ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [Trim ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [ToUpper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)o [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Nell'esempio riportato di seguito, la funzione di analisi [extractjson ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) viene utilizzata dopo che gli operatori del filtro hanno ridotto il numero di record.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Contiene i battimenti**: per evitare che le sottostringhe vengano cercate inutilmente nelle parole, utilizzare l' `has` operatore anziché `contains` . [Informazioni sugli operatori di stringa](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Cerca in colonne specifiche**: cercare in una colonna specifica invece di eseguire ricerche full-text su tutte le colonne. Non utilizzare `*` per controllare tutte le colonne.
- **Distinzione tra maiuscole**e minuscole per velocità: le ricerche con distinzione tra maiuscole e minuscole sono più specifiche e generalmente più performanti. Nomi di [operatori stringa](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)con distinzione tra maiuscole e minuscole, ad esempio `has_cs` e `contains_cs` , in genere terminano con `_cs` . È inoltre possibile utilizzare l'operatore Equals con distinzione tra maiuscole e minuscole `==` anziché `~=` .
- **Parse, non estrarre**: quando possibile, utilizzare l' [operatore parse](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) o una funzione di analisi come [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Evitare l' `matches regex` operatore stringa o la [funzione Extract ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), che utilizzano entrambe le espressioni regolari. Riservare l'utilizzo dell'espressione regolare per scenari più complessi. [Altre informazioni sulle funzioni di analisi](#parse-strings)
- **Filtro tabelle non espressioni**: non filtrare su una colonna calcolata se è possibile filtrare in una colonna di tabella.
- **N. tre caratteri termini**: evitare il confronto o il filtraggio utilizzando termini con tre caratteri o meno. Questi termini non sono indicizzati e la loro corrispondenza richiederà più risorse.
- **Progetto in modo selettivo**: rendere i risultati più facili da comprendere proiettando solo le colonne necessarie. La proiezione di colonne specifiche prima dell'esecuzione di [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) o operazioni simili consente inoltre di migliorare le prestazioni.

## <a name="optimize-the-join-operator"></a>Ottimizzare l' `join` operatore
L' [operatore join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) unisce le righe di due tabelle eseguendo la corrispondenza dei valori nelle colonne specificate. Applicare questi suggerimenti per ottimizzare le query che utilizzano questo operatore.

- **Tabella più piccola a sinistra**: l' `join` operatore corrisponde ai record nella tabella a sinistra dell'istruzione join nei record a destra. Se si utilizza la tabella più piccola a sinistra, sarà necessario un numero minore di record, velocizzando così la query. 

    Nella tabella seguente è possibile ridurre la tabella a sinistra `DeviceLogonEvents` per coprire solo tre dispositivi specifici prima di aggiungerli ai `IdentityLogonEvents` SID account.
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- **Utilizzare il sapore**di join interno: il [sapore di join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) predefinito o il [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplica le righe nella tabella sinistra per il join Key prima di restituire una riga per ogni corrispondenza alla tabella di destra. Se nella tabella a sinistra sono presenti più righe con lo stesso valore per la `join` chiave, tali righe verranno deduplicate in modo da lasciare una singola riga casuale per ogni valore univoco.

    Questo comportamento predefinito può lasciare invariate le informazioni importanti dalla tabella di sinistra che può fornire utili Insight. Ad esempio, la query seguente mostrerà solo un messaggio di posta elettronica contenente un allegato specifico, anche se lo stesso allegato è stato inviato utilizzando più messaggi di posta elettronica:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Per risolvere questa limitazione, è possibile applicare il sapore del [join interno](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) specificando la `kind=inner` visualizzazione di tutte le righe nella tabella a sinistra con i valori corrispondenti nel lato destro:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Join Records from a time window**: quando si esaminano gli eventi di sicurezza, gli analisti cercano gli eventi correlati che si verificano nello stesso periodo di tempo. Applicare lo stesso approccio quando `join` si utilizzano anche le prestazioni dei vantaggi riducendo il numero di record da controllare.
    
    La query seguente consente di controllare gli eventi di accesso entro 30 minuti dalla ricezione di un file dannoso:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Applicare i filtri temporali su entrambi i lati**, anche se non si sta indagando su una finestra temporale specifica, l'applicazione dei filtri temporali nelle tabelle Left e Right può ridurre il numero di record da controllare e migliorare le `join` prestazioni. La query seguente si applica `Timestamp > ago(1h)` a entrambe le tabelle in modo che si unisca solo ai record dell'ultima ora:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Utilizzo dei suggerimenti per le prestazioni**: utilizzare i suggerimenti con l' `join` operatore per indicare al backend di distribuire il carico quando eseguono operazioni con utilizzo intensivo delle risorse. [Ulteriori informazioni sugli hint di join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Ad esempio, il **[Suggerimento shuffle](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** consente di migliorare le prestazioni delle query quando si collegano tabelle utilizzando una chiave con una cardinalità elevata, ovvero una chiave con molti valori univoci, come `AccountObjectId` nella query seguente:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    Il **[Suggerimento](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** per la trasmissione aiuta quando la tabella a sinistra è di dimensioni ridotte (fino a 100.000 record) e la tabella a destra è estremamente grande. Ad esempio, la query seguente sta tentando di aggiungere alcuni messaggi di posta elettronica che presentano argomenti specifici con _tutti_ i collegamenti contenuti nella `EmailUrlInfo` tabella:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Ottimizzare l' `summarize` operatore
L' [operatore di riepilogo](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggrega il contenuto di una tabella. Applicare questi suggerimenti per ottimizzare le query che utilizzano questo operatore.

- **Individuare valori distinti**, in generale, `summarize` per individuare valori distinti che possono essere ripetitivi. Non è possibile utilizzarlo per aggregare colonne prive di valori ripetitivi.

    Anche se un singolo messaggio di posta elettronica può essere incluso in più eventi, l'esempio seguente _non_ è un utilizzo efficace `summarize` perché un ID di messaggi di rete per un singolo indirizzo di posta elettronica viene sempre fornito con un mittente univoco.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    L' `summarize` operatore può essere facilmente sostituito con `project` , producendo potenzialmente gli stessi risultati, consumando meno risorse:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    Nell'esempio seguente viene utilizzato un utilizzo più efficiente `summarize` perché possono essere presenti più istanze distinte di un indirizzo mittente che invia messaggi di posta elettronica allo stesso indirizzo del destinatario. Tali combinazioni sono meno distinte e probabilmente sono duplicate.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Shuffle la query**, mentre `summarize` è meglio utilizzata nelle colonne con valori ripetitivi, le stesse colonne possono anche avere una _cardinalità elevata_ o un numero elevato di valori univoci. Analogamente all' `join` operatore, è anche possibile applicare l' [hint shuffle](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` a per distribuire il carico di elaborazione e potenzialmente migliorare le prestazioni quando si opera su colonne con alta cardinalità.

    La query che segue utilizza `summarize` per contare l'indirizzo di posta elettronica del destinatario distinto, che può essere eseguito in centinaia di migliaia di organizzazioni di grandi dimensioni. Per migliorare le prestazioni, include `hint.shufflekey` :

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Scenari di query

### <a name="identify-unique-processes-with-process-ids"></a>Identificare i processi univoci con gli ID processo
Gli ID processo (PID) sono riciclati in Windows e riutilizzati per i nuovi processi. Di per sé, non possono servire come identificatori univoci per processi specifici.

Per ottenere un identificatore univoco per un computer specifico, usare l'ID processo insieme all'ora di creazione del processo. Quando si uniscono o si riepilogano i dati relativi a processi, includere le colonne per l'identificatore del computer (`DeviceId` o `DeviceName`), l'ID processo (`ProcessId` o `InitiatingProcessId`) e l'ora di creazione del processo (`ProcessCreationTime` o `InitiatingProcessCreationTime`)

La seguente query di esempio trova i processi che accedono a più di 10 indirizzi IP dalla porta 445 (SMB), possibilmente analizzando le condivisioni file.

Query di esempio:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

La query riepiloga sia `InitiatingProcessId` che `InitiatingProcessCreationTime` in modo da visualizzare un singolo processo, senza combinare più processi con lo stesso ID processo.

### <a name="query-command-lines"></a>Righe di comando di query
Esistono diversi modi per creare una riga di comando per eseguire un'attività. Ad esempio, un utente malintenzionato può fare riferimento a un file di immagine senza un percorso, senza un'estensione di file, utilizzando variabili di ambiente o con virgolette. L'utente malintenzionato può anche modificare l'ordine dei parametri o aggiungere più virgolette e spazi.

Per creare query più durevoli sulle righe di comando, applicare le procedure seguenti:

- Identificare i processi noti, ad esempio *net.exe* o *psexec.exe*, in base ai campi del nome di file anziché filtrare nella riga di comando stessa.
- Analizzare le sezioni della riga di comando utilizzando la [funzione parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- Quando si eseguono query per gli argomenti della riga di comando, non cercare una corrispondenza esatta su più argomenti non correlati in un determinato ordine. Usare invece espressioni regolari o utilizzare più operatori distinti.
- Usare corrispondenza maiuscole/minuscole. Ad esempio, utilizzare `=~` , `in~` e `contains` invece di `==` , `in` e `contains_cs` .
- Per attenuare le tecniche di offuscamento della riga di comando, valutare la possibilità di rimuovere le virgolette, sostituire le virgole con spazi e sostituire più spazi consecutivi con un singolo spazio. Sono disponibili tecniche di offuscamento più complesse che richiedono altri approcci, ma queste modifiche possono essere utili per l'indirizzamento di quelle comuni.

Negli esempi seguenti vengono illustrati diversi modi per creare una query che cerca il file *net.exe* per arrestare il servizio firewall "MPSSVC":

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a>Ingestione dei dati da origini esterne
Per incorporare elenchi lunghi o tabelle di grandi dimensioni nella query, utilizzare l' [operatore externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) per ingerire dati da un URI specificato. È possibile ottenere dati da file in formato TXT, CSV, JSON o in [altri formati](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats). Nell'esempio seguente viene illustrato come utilizzare l'elenco completo degli hash SHA-256 di malware forniti da MalwareBazaar (abuse.ch) per controllare gli allegati nei messaggi di posta elettronica:

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a>Stringhe di analisi
Esistono diverse funzioni che è possibile utilizzare per gestire in modo efficiente le stringhe che richiedono l'analisi o la conversione. 

| Stringa | Funzione | Esempio di utilizzo |
|--|--|--|
| Riga di comando | [parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | Estrarre il comando e tutti gli argomenti. | 
| Percorsi | [parse_path ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Estrarre le sezioni di un percorso di file o cartella. |
| Numeri di versione | [parse_version ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Deconstruct un numero di versione con un massimo di quattro sezioni e fino a otto caratteri per sezione. Utilizzare i dati analizzati per confrontare la versione di Age. |
| Indirizzi IPv4 | [parse_ipv4 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Convertire un indirizzo IPv4 in un numero intero lungo. Per confrontare gli indirizzi IPv4 senza convertirli, utilizzare [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| Indirizzi IPv6 | [parse_ipv6 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Convertire un indirizzo IPv4 o IPv6 nella notazione IPv6 canonica. Per confrontare gli indirizzi IPv6, utilizzare [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Per informazioni su tutte le funzioni di analisi supportate, [vedere informazioni sulle funzioni di stringa di Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions). 

## <a name="related-topics"></a>Argomenti correlati
- [Documentazione relativa alla lingua di query di Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Limiti di servizio](advanced-hunting-limits.md)
- [Gestire gli errori di ricerca avanzata](advanced-hunting-errors.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
