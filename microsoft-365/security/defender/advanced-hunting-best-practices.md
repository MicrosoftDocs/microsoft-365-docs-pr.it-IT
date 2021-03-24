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
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 53ec8146080e88b913de1f58d16750ffa766a1b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063589"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="7ebd3-104">Procedure consigliate per query in Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7ebd3-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7ebd3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7ebd3-105">**Applies to:**</span></span>
- <span data-ttu-id="7ebd3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ebd3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7ebd3-107">Applicare questi suggerimenti per ottenere risultati più veloci ed evitare timeout durante l'esecuzione di query complesse.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="7ebd3-108">Per altre informazioni su come migliorare le prestazioni della query, vedere [procedure consigliate per le query di Esplora dati](/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="7ebd3-108">For more guidance on improving query performance, read [Kusto query best practices](/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-quotas"></a><span data-ttu-id="7ebd3-109">Informazioni sulle quote delle risorse CPU</span><span class="sxs-lookup"><span data-stu-id="7ebd3-109">Understand CPU resource quotas</span></span>
<span data-ttu-id="7ebd3-110">A seconda delle dimensioni, ogni tenant ha accesso a una quantità impostata di risorse CPU allocate per l'esecuzione di query di ricerca avanzate.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="7ebd3-111">Per informazioni dettagliate sui vari limiti del servizio, vedere informazioni sulle quote di ricerca [avanzate e sui parametri di utilizzo.](advanced-hunting-limits.md)</span><span class="sxs-lookup"><span data-stu-id="7ebd3-111">For detailed information about various service limits, [read about advanced hunting quotas and usage parameters](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="7ebd3-112">I clienti che eseguono più query regolarmente devono tenere traccia del consumo e applicare le linee guida per l'ottimizzazione in questo articolo per ridurre al minimo le interruzioni derivanti dal superamento di quote o parametri di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding quotas or usage parameters.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="7ebd3-113">Suggerimenti generali per l'ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="7ebd3-113">General optimization tips</span></span>

- <span data-ttu-id="7ebd3-114">**Ridimensionare le nuove query:** se si sospetta che una query restituirà un set di risultati di grandi dimensioni, valutarla innanzitutto utilizzando l'operatore [count](/azure/data-explorer/kusto/query/countoperator).</span><span class="sxs-lookup"><span data-stu-id="7ebd3-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="7ebd3-115">Utilizzare [limit](/azure/data-explorer/kusto/query/limitoperator) o il relativo sinonimo `take` per evitare set di risultati di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-115">Use [limit](/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="7ebd3-116">**Applica i** filtri in anticipo: applica filtri tempo e altri filtri per ridurre il set di dati, in particolare prima di utilizzare le funzioni di trasformazione e analisi, ad esempio [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction)o [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="7ebd3-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](/azure/data-explorer/kusto/query/substringfunction), [replace()](/azure/data-explorer/kusto/query/replacefunction), [trim()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="7ebd3-117">Nell'esempio seguente viene utilizzata la funzione di analisi [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) dopo che gli operatori di filtro hanno ridotto il numero di record.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-117">In the example below, the parsing function [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="7ebd3-118">**Contiene battiti:** per evitare di cercare sottostringhe all'interno di parole inutilmente, utilizzare `has` l'operatore invece di `contains` .</span><span class="sxs-lookup"><span data-stu-id="7ebd3-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="7ebd3-119">Informazioni sugli operatori stringa</span><span class="sxs-lookup"><span data-stu-id="7ebd3-119">Learn about string operators</span></span>](/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="7ebd3-120">**Cercare in colonne specifiche:** cercare in una colonna specifica anziché eseguire ricerche full-text in tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="7ebd3-121">Non utilizzare per `*` controllare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="7ebd3-122">**Distinzione tra maiuscole e** minuscole per la velocità: le ricerche con distinzione tra maiuscole e minuscole sono più specifiche e generalmente più performanti.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="7ebd3-123">I nomi degli operatori stringa con [distinzione tra maiuscole e](/azure/data-explorer/kusto/query/datatypes-string-operators)minuscole, `has_cs` ad esempio e , in genere `contains_cs` terminano con `_cs` .</span><span class="sxs-lookup"><span data-stu-id="7ebd3-123">Names of case-sensitive [string operators](/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="7ebd3-124">È inoltre possibile utilizzare l'operatore uguale a distinzione tra maiuscole e minuscole `==` anziché `=~` .</span><span class="sxs-lookup"><span data-stu-id="7ebd3-124">You can also use the case-sensitive equals operator `==` instead of `=~`.</span></span>
- <span data-ttu-id="7ebd3-125">**Analizza, non estrarre:** se possibile, usa [l'operatore di](/azure/data-explorer/kusto/query/parseoperator) analisi o una funzione di analisi come [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="7ebd3-125">**Parse, don't extract**—Whenever possible, use the [parse operator](/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="7ebd3-126">Evitare `matches regex` l'operatore stringa o la [funzione extract(),](/azure/data-explorer/kusto/query/extractfunction)che utilizzano entrambe l'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-126">Avoid the `matches regex` string operator or the [extract() function](/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="7ebd3-127">Riservare l'uso dell'espressione regolare per scenari più complessi.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="7ebd3-128">Altre informazioni sulle funzioni di analisi</span><span class="sxs-lookup"><span data-stu-id="7ebd3-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="7ebd3-129">**Filtra tabelle non espressioni:** non filtrare in base a una colonna calcolata se è possibile filtrare in base a una colonna di tabella.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="7ebd3-130">**Nessun termine di tre caratteri:** evita di confrontare o filtrare usando termini con un massimo di tre caratteri.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="7ebd3-131">Questi termini non sono indicizzati e la corrispondenza richiederà più risorse.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="7ebd3-132">**Progetto in modo** selettivo: semplifica la comprensione dei risultati proiettando solo le colonne necessarie.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="7ebd3-133">L'esecuzione di colonne specifiche prima dell'esecuzione di [operazioni di join](/azure/data-explorer/kusto/query/joinoperator) o simili consente inoltre di migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-133">Projecting specific columns prior to running [join](/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="7ebd3-134">Ottimizzare `join` l'operatore</span><span class="sxs-lookup"><span data-stu-id="7ebd3-134">Optimize the `join` operator</span></span>
<span data-ttu-id="7ebd3-135">[L'operatore join](/azure/data-explorer/kusto/query/joinoperator) unisce le righe di due tabelle in base ai valori corrispondenti nelle colonne specificate.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-135">The [join operator](/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="7ebd3-136">Applicare questi suggerimenti per ottimizzare le query che utilizzano questo operatore.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="7ebd3-137">**Tabella più piccola a sinistra:** l'operatore genera una corrispondenza tra i record della tabella a sinistra dell'istruzione di join e `join` i record a destra.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="7ebd3-138">Con la tabella più piccola a sinistra, sarà necessario trovare una corrispondenza con un numero minore di record, velocizzando così la query.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="7ebd3-139">Nella tabella seguente riduciamo la tabella sinistra in modo da coprire solo tre dispositivi specifici prima di `DeviceLogonEvents` unirla `IdentityLogonEvents` con i SID dell'account.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="7ebd3-140">Use the **inner-join flavor**— The default [join flavor](/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-140">**Use the inner-join flavor**—The default [join flavor](/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="7ebd3-141">Se nella tabella sinistra sono presenti più righe con lo stesso valore per la chiave, tali righe verranno deduplicate in modo da lasciare una singola riga casuale `join` per ogni valore univoco.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="7ebd3-142">Questo comportamento predefinito può osare informazioni importanti dalla tabella a sinistra che possono fornire informazioni utili.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="7ebd3-143">Ad esempio, la query seguente mostrerà solo un messaggio di posta elettronica contenente un allegato specifico, anche se lo stesso allegato è stato inviato utilizzando più messaggi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="7ebd3-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="7ebd3-144">Per risolvere questa limitazione, viene applicato [l'inner join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) specificando di visualizzare tutte le righe della tabella sinistra con i valori `kind=inner` corrispondenti a destra:</span><span class="sxs-lookup"><span data-stu-id="7ebd3-144">To address this limitation, we apply the [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="7ebd3-145">**Unire i record da un intervallo di tempo:** quando si analizzano gli eventi di sicurezza, gli analisti ricercano gli eventi correlati che si verificano intorno allo stesso periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="7ebd3-146">L'applicazione dello stesso approccio quando si utilizza offre anche vantaggi in termini di `join` prestazioni riducendo il numero di record da controllare.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="7ebd3-147">La query seguente controlla la presenza di eventi di accesso entro 30 minuti dalla ricezione di un file dannoso:</span><span class="sxs-lookup"><span data-stu-id="7ebd3-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="7ebd3-148">**Applicare filtri** tempo su entrambi i lati: anche se non si sta analizzando un intervallo di tempo specifico, l'applicazione di filtri tempo sulle tabelle sinistra e destra può ridurre il numero di record per controllare e migliorare le `join` prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="7ebd3-149">La query seguente si applica a entrambe le tabelle in modo da unire solo i `Timestamp > ago(1h)` record dell'ultima ora:</span><span class="sxs-lookup"><span data-stu-id="7ebd3-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="7ebd3-150">**Usa suggerimenti per le prestazioni:** usa i suggerimenti con l'operatore per indicare al back-end di distribuire il carico durante l'esecuzione di operazioni che richiedono un utilizzo `join` intensivo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="7ebd3-151">Altre informazioni sui suggerimenti per l'aggiunta</span><span class="sxs-lookup"><span data-stu-id="7ebd3-151">Learn more about join hints</span></span>](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="7ebd3-152">L'hint **[shuffle,](/azure/data-explorer/kusto/query/shufflequery)** ad esempio, consente di migliorare le prestazioni delle query quando si uniscono tabelle utilizzando una chiave con cardinalità elevata, ovvero una chiave con molti valori univoci, ad esempio la `AccountObjectId` query seguente:</span><span class="sxs-lookup"><span data-stu-id="7ebd3-152">For example, the **[shuffle hint](/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="7ebd3-153">**[L'hint di](/azure/data-explorer/kusto/query/broadcastjoin)** trasmissione è utile quando la tabella sinistra è piccola (fino a 100.000 record) e la tabella destra è estremamente grande.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-153">The **[broadcast hint](/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="7ebd3-154">Ad esempio, la query seguente sta tentando di unire  alcuni messaggi di posta elettronica con soggetti specifici con tutti i messaggi contenenti collegamenti nella `EmailUrlInfo` tabella:</span><span class="sxs-lookup"><span data-stu-id="7ebd3-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="7ebd3-155">Ottimizzare `summarize` l'operatore</span><span class="sxs-lookup"><span data-stu-id="7ebd3-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="7ebd3-156">[L'operatore](/azure/data-explorer/kusto/query/summarizeoperator) summarize aggrega il contenuto di una tabella.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-156">The [summarize operator](/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="7ebd3-157">Applicare questi suggerimenti per ottimizzare le query che utilizzano questo operatore.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="7ebd3-158">**Trovare valori distinti:** in generale, utilizzare `summarize` per trovare valori distinti che possono essere ripetitivi.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="7ebd3-159">Può non essere necessario utilizzarlo per aggregare colonne che non hanno valori ripetitivi.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="7ebd3-160">Anche se un singolo messaggio di posta elettronica  può essere parte di più eventi, l'esempio seguente non è un utilizzo efficiente perché un ID messaggio di rete per un singolo messaggio di posta elettronica viene sempre fornito con un indirizzo mittente `summarize` univoco.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="7ebd3-161">`summarize`L'operatore può essere sostituito facilmente con , producendo potenzialmente `project` gli stessi risultati consumando meno risorse:</span><span class="sxs-lookup"><span data-stu-id="7ebd3-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="7ebd3-162">L'esempio seguente è un utilizzo più efficiente perché possono essere presenti più istanze distinte di un indirizzo mittente che invia messaggi di posta elettronica `summarize` allo stesso indirizzo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="7ebd3-163">Tali combinazioni sono meno distinte e probabilmente hanno duplicati.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="7ebd3-164">**Eseguire la sequenza casuale** della query. Sebbene sia meglio utilizzare colonne con valori ripetitivi, le stesse colonne possono anche avere una cardinalità elevata o un numero elevato `summarize` di valori  univoci.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="7ebd3-165">Come l'operatore, è anche possibile applicare l'hint casuale con per distribuire il carico di elaborazione e potenzialmente migliorare le prestazioni quando si opera su colonne con `join` [](/azure/data-explorer/kusto/query/shufflequery) `summarize` cardinalità elevata.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-165">Like the `join` operator, you can also apply the [shuffle hint](/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="7ebd3-166">La query seguente utilizza per contare l'indirizzo di posta elettronica del destinatario distinto, che può essere `summarize` eseguito nelle centinaia di migliaia nelle organizzazioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="7ebd3-167">Per migliorare le prestazioni, `hint.shufflekey` include:</span><span class="sxs-lookup"><span data-stu-id="7ebd3-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="7ebd3-168">Scenari di query</span><span class="sxs-lookup"><span data-stu-id="7ebd3-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="7ebd3-169">Identificare processi univoci con ID processo</span><span class="sxs-lookup"><span data-stu-id="7ebd3-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="7ebd3-170">Gli ID processo (PID) sono riciclati in Windows e riutilizzati per i nuovi processi.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="7ebd3-171">Di per sé, non possono servire come identificatori univoci per processi specifici.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="7ebd3-172">Per ottenere un identificatore univoco per un computer specifico, usare l'ID processo insieme all'ora di creazione del processo.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="7ebd3-173">Quando si uniscono o si riepilogano i dati relativi a processi, includere le colonne per l'identificatore del computer (`DeviceId` o `DeviceName`), l'ID processo (`ProcessId` o `InitiatingProcessId`) e l'ora di creazione del processo (`ProcessCreationTime` o `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="7ebd3-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="7ebd3-174">La seguente query di esempio trova i processi che accedono a più di 10 indirizzi IP dalla porta 445 (SMB), possibilmente analizzando le condivisioni file.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="7ebd3-175">Query di esempio:</span><span class="sxs-lookup"><span data-stu-id="7ebd3-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="7ebd3-176">La query riepiloga sia `InitiatingProcessId` che `InitiatingProcessCreationTime` in modo da visualizzare un singolo processo, senza combinare più processi con lo stesso ID processo.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="7ebd3-177">Righe di comando query</span><span class="sxs-lookup"><span data-stu-id="7ebd3-177">Query command lines</span></span>
<span data-ttu-id="7ebd3-178">Esistono diversi modi per creare una riga di comando per eseguire un'attività.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="7ebd3-179">Ad esempio, un utente malintenzionato potrebbe fare riferimento a un file di immagine senza percorso, senza estensione di file, utilizzando variabili di ambiente o tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="7ebd3-180">L'autore dell'attacco potrebbe anche modificare l'ordine dei parametri o aggiungere più virgolette e spazi.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="7ebd3-181">Per creare query più durevoli intorno alle righe di comando, applicare le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ebd3-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="7ebd3-182">Identificare i processi noti, ad esempio *net.exe* o *psexec.exe*, in base alla corrispondenza nei campi dei nomi di file, anziché applicare filtri alla riga di comando stessa.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="7ebd3-183">Analizzare le sezioni della riga di comando [utilizzando la funzione parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="7ebd3-183">Parse command-line sections using the [parse_command_line() function](/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="7ebd3-184">Quando si eseguono query per gli argomenti della riga di comando, non cercare una corrispondenza esatta su più argomenti non correlati in un determinato ordine.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="7ebd3-185">Usare invece espressioni regolari o utilizzare più operatori distinti.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="7ebd3-186">Usare corrispondenza maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-186">Use case insensitive matches.</span></span> <span data-ttu-id="7ebd3-187">Ad esempio, utilizzare `=~` , e invece di , e `in~` `contains` `==` `in` `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="7ebd3-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="7ebd3-188">Per ridurre le tecniche di offuscamento della riga di comando, è consigliabile rimuovere le virgolette, sostituire le virgole con spazi e sostituire più spazi consecutivi con uno spazio singolo.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="7ebd3-189">Esistono tecniche di offuscamento più complesse che richiedono altri approcci, ma queste modifiche possono aiutare a risolvere quelle comuni.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="7ebd3-190">Negli esempi seguenti vengono illustrati vari modi per creare una query che cerca il file *net.exe* arrestare il servizio firewall "MpsSvc":</span><span class="sxs-lookup"><span data-stu-id="7ebd3-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="7ebd3-191">Inserire dati da origini esterne</span><span class="sxs-lookup"><span data-stu-id="7ebd3-191">Ingest data from external sources</span></span>
<span data-ttu-id="7ebd3-192">Per incorporare elenchi lunghi o tabelle di grandi dimensioni nella query, utilizzare [l'operatore externaldata](/azure/data-explorer/kusto/query/externaldata-operator) per inserire i dati da un URI specificato.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-192">To incorporate long lists or large tables into your query, use the [externaldata operator](/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="7ebd3-193">È possibile ottenere dati da file in formato TXT, CSV, JSON [o in altri formati.](/azure/data-explorer/ingestion-supported-formats)</span><span class="sxs-lookup"><span data-stu-id="7ebd3-193">You can get data from files in TXT, CSV, JSON, or [other formats](/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="7ebd3-194">L'esempio seguente mostra come utilizzare l'elenco completo di hash SHA-256 di malware forniti da MalwareBazaar (abuse.ch) per controllare gli allegati nei messaggi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="7ebd3-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="7ebd3-195">Analizzare stringhe</span><span class="sxs-lookup"><span data-stu-id="7ebd3-195">Parse strings</span></span>
<span data-ttu-id="7ebd3-196">Esistono diverse funzioni che è possibile utilizzare per gestire in modo efficiente le stringhe che necessitano di analisi o conversione.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="7ebd3-197">Stringa</span><span class="sxs-lookup"><span data-stu-id="7ebd3-197">String</span></span> | <span data-ttu-id="7ebd3-198">Funzione</span><span class="sxs-lookup"><span data-stu-id="7ebd3-198">Function</span></span> | <span data-ttu-id="7ebd3-199">Esempio di utilizzo</span><span class="sxs-lookup"><span data-stu-id="7ebd3-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="7ebd3-200">Righe di comando</span><span class="sxs-lookup"><span data-stu-id="7ebd3-200">Command-lines</span></span> | [<span data-ttu-id="7ebd3-201">parse_command_line()</span><span class="sxs-lookup"><span data-stu-id="7ebd3-201">parse_command_line()</span></span>](/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="7ebd3-202">Estrarre il comando e tutti gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="7ebd3-203">Percorsi</span><span class="sxs-lookup"><span data-stu-id="7ebd3-203">Paths</span></span> | [<span data-ttu-id="7ebd3-204">parse_path()</span><span class="sxs-lookup"><span data-stu-id="7ebd3-204">parse_path()</span></span>](/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="7ebd3-205">Estrarre le sezioni di un file o di un percorso di cartella.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="7ebd3-206">Numeri di versione</span><span class="sxs-lookup"><span data-stu-id="7ebd3-206">Version numbers</span></span> | [<span data-ttu-id="7ebd3-207">parse_version()</span><span class="sxs-lookup"><span data-stu-id="7ebd3-207">parse_version()</span></span>](/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="7ebd3-208">Decostruire un numero di versione con un massimo di quattro sezioni e fino a otto caratteri per sezione.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="7ebd3-209">Usa i dati analizzati per confrontare il periodo di validità della versione.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="7ebd3-210">Indirizzi IPv4</span><span class="sxs-lookup"><span data-stu-id="7ebd3-210">IPv4 addresses</span></span> | [<span data-ttu-id="7ebd3-211">parse_ipv4()</span><span class="sxs-lookup"><span data-stu-id="7ebd3-211">parse_ipv4()</span></span>](/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="7ebd3-212">Convertire un indirizzo IPv4 in un numero intero lungo.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="7ebd3-213">Per confrontare gli indirizzi IPv4 senza convertirli, [utilizzare ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="7ebd3-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="7ebd3-214">Indirizzi IPv6</span><span class="sxs-lookup"><span data-stu-id="7ebd3-214">IPv6 addresses</span></span> | [<span data-ttu-id="7ebd3-215">parse_ipv6()</span><span class="sxs-lookup"><span data-stu-id="7ebd3-215">parse_ipv6()</span></span>](/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="7ebd3-216">Convertire un indirizzo IPv4 o IPv6 nella notazione IPv6 canonica.</span><span class="sxs-lookup"><span data-stu-id="7ebd3-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="7ebd3-217">Per confrontare gli indirizzi IPv6, [utilizzare ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="7ebd3-217">To compare IPv6 addresses, use [ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="7ebd3-218">Per informazioni su tutte le funzioni di analisi supportate, [vedere Funzioni stringa Kusto.](/azure/data-explorer/kusto/query/scalarfunctions#string-functions)</span><span class="sxs-lookup"><span data-stu-id="7ebd3-218">To learn about all supported parsing functions, [read about Kusto string functions](/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="7ebd3-219">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7ebd3-219">Related topics</span></span>
- [<span data-ttu-id="7ebd3-220">Documentazione del linguaggio di query Kusto</span><span class="sxs-lookup"><span data-stu-id="7ebd3-220">Kusto query language documentation</span></span>](/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="7ebd3-221">Quote e parametri di utilizzo</span><span class="sxs-lookup"><span data-stu-id="7ebd3-221">Quotas and usage parameters</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="7ebd3-222">Gestire gli errori di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7ebd3-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="7ebd3-223">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7ebd3-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7ebd3-224">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="7ebd3-224">Learn the query language</span></span>](advanced-hunting-query-language.md)