---
title: Procedure consigliate per la ricerca avanzata di query in Microsoft 365 Defender
description: Informazioni su come creare query di ricerca delle minacce veloci, efficienti e senza errori con la ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, schema, kusto, evitare timeout, righe di comando, ID processo, ottimizzare, procedure consigliate, analizzare, partecipare, riepilogare
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e0744a01fc599b66f371b01194579f4845ed19fb
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498724"
---
# <a name="advanced-hunting-query-best-practices"></a>Procedure consigliate per query in Ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Applicare questi suggerimenti per ottenere risultati più veloci ed evitare timeout durante l'esecuzione di query complesse. Per altre informazioni su come migliorare le prestazioni della query, vedere [procedure consigliate per le query di Esplora dati](/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-quotas"></a>Informazioni sulle quote delle risorse CPU
A seconda delle dimensioni, ogni tenant ha accesso a una quantità impostata di risorse CPU allocate per l'esecuzione di query di ricerca avanzate. Per informazioni dettagliate sui vari limiti del servizio, vedere informazioni sulle quote di ricerca [avanzate e sui parametri di utilizzo.](advanced-hunting-limits.md)

I clienti che eseguono più query regolarmente devono tenere traccia del consumo e applicare le linee guida per l'ottimizzazione in questo articolo per ridurre al minimo le interruzioni derivanti dal superamento di quote o parametri di utilizzo.

## <a name="general-optimization-tips"></a>Suggerimenti generali per l'ottimizzazione

- **Ridimensionare le nuove query:** se si sospetta che una query restituirà un set di risultati di grandi dimensioni, valutarla innanzitutto utilizzando l'operatore [count](/azure/data-explorer/kusto/query/countoperator). Utilizzare [limit](/azure/data-explorer/kusto/query/limitoperator) o il relativo sinonimo `take` per evitare set di risultati di grandi dimensioni.
- **Applica i** filtri in anticipo: applica filtri tempo e altri filtri per ridurre il set di dati, in particolare prima di utilizzare le funzioni di trasformazione e analisi, ad esempio [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction)o [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). Nell'esempio seguente viene utilizzata la funzione di analisi [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) dopo che gli operatori di filtro hanno ridotto il numero di record.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Contiene battiti:** per evitare di cercare sottostringhe all'interno di parole inutilmente, utilizzare `has` l'operatore invece di `contains` . [Informazioni sugli operatori stringa](/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Cercare in colonne specifiche:** cercare in una colonna specifica anziché eseguire ricerche full-text in tutte le colonne. Non utilizzare per `*` controllare tutte le colonne.
- **Distinzione tra maiuscole e** minuscole per la velocità: le ricerche con distinzione tra maiuscole e minuscole sono più specifiche e generalmente più performanti. I nomi degli operatori stringa con [distinzione tra maiuscole e](/azure/data-explorer/kusto/query/datatypes-string-operators)minuscole, `has_cs` ad esempio e , in genere `contains_cs` terminano con `_cs` . È inoltre possibile utilizzare l'operatore uguale a distinzione tra maiuscole e minuscole `==` anziché `=~` .
- **Analizza, non estrarre:** se possibile, usa [l'operatore di](/azure/data-explorer/kusto/query/parseoperator) analisi o una funzione di analisi come [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). Evitare `matches regex` l'operatore stringa o la [funzione extract(),](/azure/data-explorer/kusto/query/extractfunction)che utilizzano entrambe l'espressione regolare. Riservare l'uso dell'espressione regolare per scenari più complessi. [Altre informazioni sulle funzioni di analisi](#parse-strings)
- **Filtra tabelle non espressioni:** non filtrare in base a una colonna calcolata se è possibile filtrare in base a una colonna di tabella.
- **Nessun termine di tre caratteri:** evita di confrontare o filtrare usando termini con un massimo di tre caratteri. Questi termini non sono indicizzati e la corrispondenza richiederà più risorse.
- **Progetto in modo** selettivo: semplifica la comprensione dei risultati proiettando solo le colonne necessarie. L'esecuzione di colonne specifiche prima dell'esecuzione di [operazioni di join](/azure/data-explorer/kusto/query/joinoperator) o simili consente inoltre di migliorare le prestazioni.

## <a name="optimize-the-join-operator"></a>Ottimizzare `join` l'operatore
[L'operatore join](/azure/data-explorer/kusto/query/joinoperator) unisce le righe di due tabelle in base ai valori corrispondenti nelle colonne specificate. Applicare questi suggerimenti per ottimizzare le query che utilizzano questo operatore.

- **Tabella più piccola a sinistra:** l'operatore genera una corrispondenza tra i record della tabella a sinistra dell'istruzione di join e `join` i record a destra. Con la tabella più piccola a sinistra, sarà necessario trovare una corrispondenza con un numero minore di record, velocizzando così la query. 

    Nella tabella seguente riduciamo la tabella sinistra in modo da coprire solo tre dispositivi specifici prima di `DeviceLogonEvents` unirla `IdentityLogonEvents` con i SID dell'account.
 
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

- Use the **inner-join flavor**— The default [join flavor](/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table. Se nella tabella sinistra sono presenti più righe con lo stesso valore per la chiave, tali righe verranno deduplicate in modo da lasciare una singola riga casuale `join` per ogni valore univoco.

    Questo comportamento predefinito può osare informazioni importanti dalla tabella a sinistra che possono fornire informazioni utili. Ad esempio, la query seguente mostrerà solo un messaggio di posta elettronica contenente un allegato specifico, anche se lo stesso allegato è stato inviato utilizzando più messaggi di posta elettronica:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    Per risolvere questa limitazione, viene applicato [l'inner join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) specificando di visualizzare tutte le righe della tabella sinistra con i valori `kind=inner` corrispondenti a destra:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Unire i record da un intervallo di tempo:** quando si analizzano gli eventi di sicurezza, gli analisti ricercano gli eventi correlati che si verificano intorno allo stesso periodo di tempo. L'applicazione dello stesso approccio quando si utilizza offre anche vantaggi in termini di `join` prestazioni riducendo il numero di record da controllare.
    
    La query seguente controlla la presenza di eventi di accesso entro 30 minuti dalla ricezione di un file dannoso:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Applicare filtri** tempo su entrambi i lati: anche se non si sta analizzando un intervallo di tempo specifico, l'applicazione di filtri tempo sulle tabelle sinistra e destra può ridurre il numero di record per controllare e migliorare le `join` prestazioni. La query seguente si applica a entrambe le tabelle in modo da unire solo i `Timestamp > ago(1h)` record dell'ultima ora:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Usa suggerimenti per le prestazioni:** usa i suggerimenti con l'operatore per indicare al back-end di distribuire il carico durante l'esecuzione di operazioni che richiedono un utilizzo `join` intensivo delle risorse. [Altre informazioni sui suggerimenti per l'aggiunta](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    L'hint **[shuffle,](/azure/data-explorer/kusto/query/shufflequery)** ad esempio, consente di migliorare le prestazioni delle query quando si uniscono tabelle utilizzando una chiave con cardinalità elevata, ovvero una chiave con molti valori univoci, ad esempio la `AccountObjectId` query seguente:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    **[L'hint di](/azure/data-explorer/kusto/query/broadcastjoin)** trasmissione è utile quando la tabella sinistra è piccola (fino a 100.000 record) e la tabella destra è estremamente grande. Ad esempio, la query seguente sta tentando di unire  alcuni messaggi di posta elettronica con soggetti specifici con tutti i messaggi contenenti collegamenti nella `EmailUrlInfo` tabella:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Ottimizzare `summarize` l'operatore
[L'operatore](/azure/data-explorer/kusto/query/summarizeoperator) summarize aggrega il contenuto di una tabella. Applicare questi suggerimenti per ottimizzare le query che utilizzano questo operatore.

- **Trovare valori distinti:** in generale, utilizzare `summarize` per trovare valori distinti che possono essere ripetitivi. Può non essere necessario utilizzarlo per aggregare colonne che non hanno valori ripetitivi.

    Anche se un singolo messaggio di posta elettronica  può essere parte di più eventi, l'esempio seguente non è un utilizzo efficiente perché un ID messaggio di rete per un singolo messaggio di posta elettronica viene sempre fornito con un indirizzo mittente `summarize` univoco.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    `summarize`L'operatore può essere sostituito facilmente con , producendo potenzialmente `project` gli stessi risultati consumando meno risorse:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    L'esempio seguente è un utilizzo più efficiente perché possono essere presenti più istanze distinte di un indirizzo mittente che invia messaggi di posta elettronica `summarize` allo stesso indirizzo del destinatario. Tali combinazioni sono meno distinte e probabilmente hanno duplicati.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Eseguire la sequenza casuale** della query. Sebbene sia meglio utilizzare colonne con valori ripetitivi, le stesse colonne possono anche avere una cardinalità elevata o un numero elevato `summarize` di valori  univoci. Come l'operatore, è anche possibile applicare l'hint casuale con per distribuire il carico di elaborazione e potenzialmente migliorare le prestazioni quando si opera su colonne con `join` [](/azure/data-explorer/kusto/query/shufflequery) `summarize` cardinalità elevata.

    La query seguente utilizza per contare l'indirizzo di posta elettronica del destinatario distinto, che può essere `summarize` eseguito nelle centinaia di migliaia nelle organizzazioni di grandi dimensioni. Per migliorare le prestazioni, `hint.shufflekey` include:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Scenari di query

### <a name="identify-unique-processes-with-process-ids"></a>Identificare processi univoci con ID processo
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

### <a name="query-command-lines"></a>Righe di comando query
Esistono diversi modi per creare una riga di comando per eseguire un'attività. Ad esempio, un utente malintenzionato potrebbe fare riferimento a un file di immagine senza percorso, senza estensione di file, utilizzando variabili di ambiente o tra virgolette. L'autore dell'attacco potrebbe anche modificare l'ordine dei parametri o aggiungere più virgolette e spazi.

Per creare query più durevoli intorno alle righe di comando, applicare le procedure seguenti:

- Identificare i processi noti, ad esempio *net.exe* o *psexec.exe*, in base alla corrispondenza nei campi dei nomi di file, anziché applicare filtri alla riga di comando stessa.
- Analizzare le sezioni della riga di comando [utilizzando la funzione parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) 
- Quando si eseguono query per gli argomenti della riga di comando, non cercare una corrispondenza esatta su più argomenti non correlati in un determinato ordine. Usare invece espressioni regolari o utilizzare più operatori distinti.
- Usare corrispondenza maiuscole/minuscole. Ad esempio, utilizzare `=~` , e invece di , e `in~` `contains` `==` `in` `contains_cs` .
- Per ridurre le tecniche di offuscamento della riga di comando, è consigliabile rimuovere le virgolette, sostituire le virgole con spazi e sostituire più spazi consecutivi con uno spazio singolo. Esistono tecniche di offuscamento più complesse che richiedono altri approcci, ma queste modifiche possono aiutare a risolvere quelle comuni.

Negli esempi seguenti vengono illustrati vari modi per creare una query che cerca il file *net.exe* arrestare il servizio firewall "MpsSvc":

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

### <a name="ingest-data-from-external-sources"></a>Inserire dati da origini esterne
Per incorporare elenchi lunghi o tabelle di grandi dimensioni nella query, utilizzare [l'operatore externaldata](/azure/data-explorer/kusto/query/externaldata-operator) per inserire i dati da un URI specificato. È possibile ottenere dati da file in formato TXT, CSV, JSON [o in altri formati.](/azure/data-explorer/ingestion-supported-formats) L'esempio seguente mostra come utilizzare l'elenco completo di hash SHA-256 di malware forniti da MalwareBazaar (abuse.ch) per controllare gli allegati nei messaggi di posta elettronica:

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
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a>Analizzare stringhe
Esistono diverse funzioni che è possibile utilizzare per gestire in modo efficiente le stringhe che necessitano di analisi o conversione. 

| Stringa | Funzione | Esempio di utilizzo |
|--|--|--|
| Righe di comando | [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) | Estrarre il comando e tutti gli argomenti. | 
| Percorsi | [parse_path()](/azure/data-explorer/kusto/query/parsepathfunction) | Estrarre le sezioni di un file o di un percorso di cartella. |
| Numeri di versione | [parse_version()](/azure/data-explorer/kusto/query/parse-versionfunction) | Decostruire un numero di versione con un massimo di quattro sezioni e fino a otto caratteri per sezione. Usa i dati analizzati per confrontare il periodo di validità della versione. |
| Indirizzi IPv4 | [parse_ipv4()](/azure/data-explorer/kusto/query/parse-ipv4function) | Convertire un indirizzo IPv4 in un numero intero lungo. Per confrontare gli indirizzi IPv4 senza convertirli, [utilizzare ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| Indirizzi IPv6 | [parse_ipv6()](/azure/data-explorer/kusto/query/parse-ipv6function)  | Convertire un indirizzo IPv4 o IPv6 nella notazione IPv6 canonica. Per confrontare gli indirizzi IPv6, [utilizzare ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Per informazioni su tutte le funzioni di analisi supportate, [vedere Funzioni stringa Kusto.](/azure/data-explorer/kusto/query/scalarfunctions#string-functions) 

## <a name="related-topics"></a>Argomenti correlati
- [Documentazione del linguaggio di query Kusto](/azure/data-explorer/kusto/query/)
- [Quote e parametri di utilizzo](advanced-hunting-limits.md)
- [Gestire gli errori di ricerca avanzata](advanced-hunting-errors.md)
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)