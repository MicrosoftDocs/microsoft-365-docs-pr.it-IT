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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: af9579b94314375aa786782ea477bb11b0cd9c0b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198212"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="219ef-104">Procedure consigliate per query in Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="219ef-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="219ef-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="219ef-105">**Applies to:**</span></span>
- <span data-ttu-id="219ef-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="219ef-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="219ef-107">Applicare questi suggerimenti per ottenere risultati più velocemente ed evitare timeout durante l'esecuzione di query complesse.</span><span class="sxs-lookup"><span data-stu-id="219ef-107">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span> <span data-ttu-id="219ef-108">Per altre informazioni su come migliorare le prestazioni della query, vedere [procedure consigliate per le query di Esplora dati](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="219ef-108">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="understand-cpu-resource-limits"></a><span data-ttu-id="219ef-109">Informazioni sui limiti relativi alle risorse della CPU</span><span class="sxs-lookup"><span data-stu-id="219ef-109">Understand CPU resource limits</span></span>
<span data-ttu-id="219ef-110">A seconda delle dimensioni, ogni tenant ha accesso a una quantità di risorse della CPU allocata per l'esecuzione di query di ricerca avanzate.</span><span class="sxs-lookup"><span data-stu-id="219ef-110">Depending on its size, each tenant has access to a set amount of CPU resources allocated for running advanced hunting queries.</span></span> <span data-ttu-id="219ef-111">Per informazioni dettagliate sui vari limiti di servizio, [vedere informazioni sui limiti di caccia avanzati](advanced-hunting-limits.md).</span><span class="sxs-lookup"><span data-stu-id="219ef-111">For detailed information about various service limits, [read about advanced hunting limits](advanced-hunting-limits.md).</span></span>

<span data-ttu-id="219ef-112">I clienti che eseguono più query regolarmente devono tenere conto dei consumi e applicare le indicazioni di ottimizzazione in questo articolo per ridurre al minimo le interruzioni derivanti dal superamento dei limiti.</span><span class="sxs-lookup"><span data-stu-id="219ef-112">Customers who run multiple queries regularly should track consumption and apply the optimization guidance in this article to minimize disruption resulting from exceeding the limits.</span></span>

## <a name="general-optimization-tips"></a><span data-ttu-id="219ef-113">Suggerimenti per l'ottimizzazione generale</span><span class="sxs-lookup"><span data-stu-id="219ef-113">General optimization tips</span></span>

- <span data-ttu-id="219ef-114">**Dimensione nuove query**: se si ritiene che una query restituirà un set di risultati di grandi dimensioni, valutarla prima utilizzando l' [operatore Count](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span><span class="sxs-lookup"><span data-stu-id="219ef-114">**Size new queries**—If you suspect that a query will return a large result set, assess it first using the [count operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator).</span></span> <span data-ttu-id="219ef-115">Utilizzare [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) o il relativo sinonimo `take` per evitare set di risultati di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="219ef-115">Use [limit](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) or its synonym `take` to avoid large result sets.</span></span>
- <span data-ttu-id="219ef-116">**Applicare i filtri all'inizio**: applicare filtri temporali e altri filtri per ridurre il set di dati, soprattutto prima di utilizzare le funzioni di trasformazione e analisi, ad esempio [substring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [Replace ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [Trim ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [ToUpper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)o [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="219ef-116">**Apply filters early**—Apply time filters and other filters to reduce the data set, especially before using transformation and parsing functions, such as [substring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [replace()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [trim()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction), or [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="219ef-117">Nell'esempio riportato di seguito, la funzione di analisi [extractjson ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) viene utilizzata dopo che gli operatori del filtro hanno ridotto il numero di record.</span><span class="sxs-lookup"><span data-stu-id="219ef-117">In the example below, the parsing function [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) is used after filtering operators have reduced the number of records.</span></span>

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- <span data-ttu-id="219ef-118">**Contiene i battimenti**: per evitare che le sottostringhe vengano cercate inutilmente nelle parole, utilizzare l' `has` operatore anziché `contains` .</span><span class="sxs-lookup"><span data-stu-id="219ef-118">**Has beats contains**—To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains`.</span></span> [<span data-ttu-id="219ef-119">Informazioni sugli operatori di stringa</span><span class="sxs-lookup"><span data-stu-id="219ef-119">Learn about string operators</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- <span data-ttu-id="219ef-120">**Cerca in colonne specifiche**: cercare in una colonna specifica invece di eseguire ricerche full-text su tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="219ef-120">**Look in specific columns**—Look in a specific column rather than running full text searches across all columns.</span></span> <span data-ttu-id="219ef-121">Non utilizzare `*` per controllare tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="219ef-121">Don't use `*` to check all columns.</span></span>
- <span data-ttu-id="219ef-122">**Distinzione tra maiuscole**e minuscole per velocità: le ricerche con distinzione tra maiuscole e minuscole sono più specifiche e generalmente più performanti.</span><span class="sxs-lookup"><span data-stu-id="219ef-122">**Case-sensitive for speed**—Case-sensitive searches are more specific and generally more performant.</span></span> <span data-ttu-id="219ef-123">Nomi di [operatori stringa](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)con distinzione tra maiuscole e minuscole, ad esempio `has_cs` e `contains_cs` , in genere terminano con `_cs` .</span><span class="sxs-lookup"><span data-stu-id="219ef-123">Names of case-sensitive [string operators](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), such as `has_cs` and `contains_cs`, generally end with `_cs`.</span></span> <span data-ttu-id="219ef-124">È inoltre possibile utilizzare l'operatore Equals con distinzione tra maiuscole e minuscole `==` anziché `~=` .</span><span class="sxs-lookup"><span data-stu-id="219ef-124">You can also use the case-sensitive equals operator `==` instead of `~=`.</span></span>
- <span data-ttu-id="219ef-125">**Parse, non estrarre**: quando possibile, utilizzare l' [operatore parse](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) o una funzione di analisi come [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span><span class="sxs-lookup"><span data-stu-id="219ef-125">**Parse, don't extract**—Whenever possible, use the [parse operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) or a parsing function like [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction).</span></span> <span data-ttu-id="219ef-126">Evitare l' `matches regex` operatore stringa o la [funzione Extract ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), che utilizzano entrambe le espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="219ef-126">Avoid the `matches regex` string operator or the [extract() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), both of which use regular expression.</span></span> <span data-ttu-id="219ef-127">Riservare l'utilizzo dell'espressione regolare per scenari più complessi.</span><span class="sxs-lookup"><span data-stu-id="219ef-127">Reserve the use of regular expression for more complex scenarios.</span></span> [<span data-ttu-id="219ef-128">Altre informazioni sulle funzioni di analisi</span><span class="sxs-lookup"><span data-stu-id="219ef-128">Read more about parsing functions</span></span>](#parse-strings)
- <span data-ttu-id="219ef-129">**Filtro tabelle non espressioni**: non filtrare su una colonna calcolata se è possibile filtrare in una colonna di tabella.</span><span class="sxs-lookup"><span data-stu-id="219ef-129">**Filter tables not expressions**—Don't filter on a calculated column if you can filter on a table column.</span></span>
- <span data-ttu-id="219ef-130">**N. tre caratteri termini**: evitare il confronto o il filtraggio utilizzando termini con tre caratteri o meno.</span><span class="sxs-lookup"><span data-stu-id="219ef-130">**No three-character terms**—Avoid comparing or filtering using terms with three characters or fewer.</span></span> <span data-ttu-id="219ef-131">Questi termini non sono indicizzati e la loro corrispondenza richiederà più risorse.</span><span class="sxs-lookup"><span data-stu-id="219ef-131">These terms are not indexed and matching them will require more resources.</span></span>
- <span data-ttu-id="219ef-132">**Progetto in modo selettivo**: rendere i risultati più facili da comprendere proiettando solo le colonne necessarie.</span><span class="sxs-lookup"><span data-stu-id="219ef-132">**Project selectively**—Make your results easier to understand by projecting only the columns you need.</span></span> <span data-ttu-id="219ef-133">La proiezione di colonne specifiche prima dell'esecuzione di [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) o operazioni simili consente inoltre di migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="219ef-133">Projecting specific columns prior to running [join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) or similar operations also helps improve performance.</span></span>

## <a name="optimize-the-join-operator"></a><span data-ttu-id="219ef-134">Ottimizzare l' `join` operatore</span><span class="sxs-lookup"><span data-stu-id="219ef-134">Optimize the `join` operator</span></span>
<span data-ttu-id="219ef-135">L' [operatore join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) unisce le righe di due tabelle eseguendo la corrispondenza dei valori nelle colonne specificate.</span><span class="sxs-lookup"><span data-stu-id="219ef-135">The [join operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) merges rows from two tables by matching values in specified columns.</span></span> <span data-ttu-id="219ef-136">Applicare questi suggerimenti per ottimizzare le query che utilizzano questo operatore.</span><span class="sxs-lookup"><span data-stu-id="219ef-136">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="219ef-137">**Tabella più piccola a sinistra**: l' `join` operatore corrisponde ai record nella tabella a sinistra dell'istruzione join nei record a destra.</span><span class="sxs-lookup"><span data-stu-id="219ef-137">**Smaller table to your left**—The `join` operator matches records in the table on the left side of your join statement to records on the right.</span></span> <span data-ttu-id="219ef-138">Se si utilizza la tabella più piccola a sinistra, sarà necessario un numero minore di record, velocizzando così la query.</span><span class="sxs-lookup"><span data-stu-id="219ef-138">By having the smaller table on the left, fewer records will need to be matched, thus speeding up the query.</span></span> 

    <span data-ttu-id="219ef-139">Nella tabella seguente è possibile ridurre la tabella a sinistra `DeviceLogonEvents` per coprire solo tre dispositivi specifici prima di aggiungerli ai `IdentityLogonEvents` SID account.</span><span class="sxs-lookup"><span data-stu-id="219ef-139">In the table below, we reduce the left table `DeviceLogonEvents` to cover only three specific devices before joining it with `IdentityLogonEvents` by account SIDs.</span></span>
 
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

- <span data-ttu-id="219ef-140">**Utilizzare il sapore**di join interno: il [sapore di join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) predefinito o il [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplica le righe nella tabella sinistra per il join Key prima di restituire una riga per ogni corrispondenza alla tabella di destra.</span><span class="sxs-lookup"><span data-stu-id="219ef-140">**Use the inner-join flavor**—The default [join flavor](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) or the [innerunique-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicates rows in the left table by the join key before returning a row for each match to the right table.</span></span> <span data-ttu-id="219ef-141">Se nella tabella a sinistra sono presenti più righe con lo stesso valore per la `join` chiave, tali righe verranno deduplicate in modo da lasciare una singola riga casuale per ogni valore univoco.</span><span class="sxs-lookup"><span data-stu-id="219ef-141">If the left table has multiple rows with the same value for the `join` key, those rows will be deduplicated to leave a single random row for each unique value.</span></span>

    <span data-ttu-id="219ef-142">Questo comportamento predefinito può lasciare invariate le informazioni importanti dalla tabella di sinistra che può fornire utili Insight.</span><span class="sxs-lookup"><span data-stu-id="219ef-142">This default behavior can leave out important information from the left table that can provide useful insight.</span></span> <span data-ttu-id="219ef-143">Ad esempio, la query seguente mostrerà solo un messaggio di posta elettronica contenente un allegato specifico, anche se lo stesso allegato è stato inviato utilizzando più messaggi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="219ef-143">For example, the query below will only show one email containing a particular attachment, even if that same attachment was sent using multiple emails messages:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    <span data-ttu-id="219ef-144">Per risolvere questa limitazione, è possibile applicare il sapore del [join interno](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) specificando la `kind=inner` visualizzazione di tutte le righe nella tabella a sinistra con i valori corrispondenti nel lato destro:</span><span class="sxs-lookup"><span data-stu-id="219ef-144">To address this limitation, we apply the [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) flavor by specifying `kind=inner` to show all rows in the left table with matching values in the right:</span></span>
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- <span data-ttu-id="219ef-145">**Join Records from a time window**: quando si esaminano gli eventi di sicurezza, gli analisti cercano gli eventi correlati che si verificano nello stesso periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="219ef-145">**Join records from a time window**—When investigating security events, analysts look for related events that occur around the same time period.</span></span> <span data-ttu-id="219ef-146">Applicare lo stesso approccio quando `join` si utilizzano anche le prestazioni dei vantaggi riducendo il numero di record da controllare.</span><span class="sxs-lookup"><span data-stu-id="219ef-146">Applying the same approach when using `join` also benefits performance by reducing the number of records to check.</span></span>
    
    <span data-ttu-id="219ef-147">La query seguente consente di controllare gli eventi di accesso entro 30 minuti dalla ricezione di un file dannoso:</span><span class="sxs-lookup"><span data-stu-id="219ef-147">The query below checks for logon events within 30 minutes of receiving a malicious file:</span></span>

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
- <span data-ttu-id="219ef-148">**Applicare i filtri temporali su entrambi i lati**, anche se non si sta indagando su una finestra temporale specifica, l'applicazione dei filtri temporali nelle tabelle Left e Right può ridurre il numero di record da controllare e migliorare le `join` prestazioni.</span><span class="sxs-lookup"><span data-stu-id="219ef-148">**Apply time filters on both sides**—Even if you're not investigating a specific time window, applying time filters on both the left and right tables can reduce the number of records to check and improve `join` performance.</span></span> <span data-ttu-id="219ef-149">La query seguente si applica `Timestamp > ago(1h)` a entrambe le tabelle in modo che si unisca solo ai record dell'ultima ora:</span><span class="sxs-lookup"><span data-stu-id="219ef-149">The query below applies `Timestamp > ago(1h)` to both tables so that it joins only records from the past hour:</span></span>

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- <span data-ttu-id="219ef-150">**Utilizzo dei suggerimenti per le prestazioni**: utilizzare i suggerimenti con l' `join` operatore per indicare al backend di distribuire il carico quando eseguono operazioni con utilizzo intensivo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="219ef-150">**Use hints for performance**—Use hints with the `join` operator to instruct the backend to distribute load when running resource-intensive operations.</span></span> [<span data-ttu-id="219ef-151">Ulteriori informazioni sugli hint di join</span><span class="sxs-lookup"><span data-stu-id="219ef-151">Learn more about join hints</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    <span data-ttu-id="219ef-152">Ad esempio, il **[Suggerimento shuffle](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** consente di migliorare le prestazioni delle query quando si collegano tabelle utilizzando una chiave con una cardinalità elevata, ovvero una chiave con molti valori univoci, come `AccountObjectId` nella query seguente:</span><span class="sxs-lookup"><span data-stu-id="219ef-152">For example, the **[shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** helps improve query performance when joining tables using a key with high cardinality—a key with many unique values—such as the `AccountObjectId` in the query below:</span></span>

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    <span data-ttu-id="219ef-153">Il **[Suggerimento](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** per la trasmissione aiuta quando la tabella a sinistra è di dimensioni ridotte (fino a 100.000 record) e la tabella a destra è estremamente grande.</span><span class="sxs-lookup"><span data-stu-id="219ef-153">The **[broadcast hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** helps when the left table is small (up to 100,000 records) and the right table is extremely large.</span></span> <span data-ttu-id="219ef-154">Ad esempio, la query seguente sta tentando di aggiungere alcuni messaggi di posta elettronica che presentano argomenti specifici con _tutti_ i collegamenti contenuti nella `EmailUrlInfo` tabella:</span><span class="sxs-lookup"><span data-stu-id="219ef-154">For example, the query below is trying to join a few emails that have specific subjects with _all_ messages containing links in the `EmailUrlInfo` table:</span></span>

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a><span data-ttu-id="219ef-155">Ottimizzare l' `summarize` operatore</span><span class="sxs-lookup"><span data-stu-id="219ef-155">Optimize the `summarize` operator</span></span>
<span data-ttu-id="219ef-156">L' [operatore di riepilogo](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggrega il contenuto di una tabella.</span><span class="sxs-lookup"><span data-stu-id="219ef-156">The [summarize operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregates the contents of a table.</span></span> <span data-ttu-id="219ef-157">Applicare questi suggerimenti per ottimizzare le query che utilizzano questo operatore.</span><span class="sxs-lookup"><span data-stu-id="219ef-157">Apply these tips to optimize queries that use this operator.</span></span>

- <span data-ttu-id="219ef-158">**Individuare valori distinti**, in generale, `summarize` per individuare valori distinti che possono essere ripetitivi.</span><span class="sxs-lookup"><span data-stu-id="219ef-158">**Find distinct values**—In general, use `summarize` to find distinct values that can be repetitive.</span></span> <span data-ttu-id="219ef-159">Non è possibile utilizzarlo per aggregare colonne prive di valori ripetitivi.</span><span class="sxs-lookup"><span data-stu-id="219ef-159">It can be unnecessary to use it to aggregate columns that don't have repetitive values.</span></span>

    <span data-ttu-id="219ef-160">Anche se un singolo messaggio di posta elettronica può essere incluso in più eventi, l'esempio seguente _non_ è un utilizzo efficace `summarize` perché un ID di messaggi di rete per un singolo indirizzo di posta elettronica viene sempre fornito con un mittente univoco.</span><span class="sxs-lookup"><span data-stu-id="219ef-160">While a single email can be part of multiple events, the example below is _not_ an efficient use of `summarize` because a network message ID for an individual email always comes with a unique sender address.</span></span>
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="219ef-161">L' `summarize` operatore può essere facilmente sostituito con `project` , producendo potenzialmente gli stessi risultati, consumando meno risorse:</span><span class="sxs-lookup"><span data-stu-id="219ef-161">The `summarize` operator can be easily replaced with `project`, yielding potentially the same results while consuming fewer resources:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    <span data-ttu-id="219ef-162">Nell'esempio seguente viene utilizzato un utilizzo più efficiente `summarize` perché possono essere presenti più istanze distinte di un indirizzo mittente che invia messaggi di posta elettronica allo stesso indirizzo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="219ef-162">The following example is a more efficient use of `summarize` because there can be multiple distinct instances of a sender address sending email to the same recipient address.</span></span> <span data-ttu-id="219ef-163">Tali combinazioni sono meno distinte e probabilmente sono duplicate.</span><span class="sxs-lookup"><span data-stu-id="219ef-163">Such combinations are less distinct and are likely to have duplicates.</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- <span data-ttu-id="219ef-164">**Shuffle la query**, mentre `summarize` è meglio utilizzata nelle colonne con valori ripetitivi, le stesse colonne possono anche avere una _cardinalità elevata_ o un numero elevato di valori univoci.</span><span class="sxs-lookup"><span data-stu-id="219ef-164">**Shuffle the query**—While `summarize` is best used in columns with repetitive values, the same columns can also have _high cardinality_ or large numbers of unique values.</span></span> <span data-ttu-id="219ef-165">Analogamente all' `join` operatore, è anche possibile applicare l' [hint shuffle](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` a per distribuire il carico di elaborazione e potenzialmente migliorare le prestazioni quando si opera su colonne con alta cardinalità.</span><span class="sxs-lookup"><span data-stu-id="219ef-165">Like the `join` operator, you can also apply the [shuffle hint](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) with `summarize` to distribute processing load and potentially improve performance when operating on columns with high cardinality.</span></span>

    <span data-ttu-id="219ef-166">La query che segue utilizza `summarize` per contare l'indirizzo di posta elettronica del destinatario distinto, che può essere eseguito in centinaia di migliaia di organizzazioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="219ef-166">The query below uses `summarize` to count distinct recipient email address, which can run in the hundreds of thousands in large organizations.</span></span> <span data-ttu-id="219ef-167">Per migliorare le prestazioni, include `hint.shufflekey` :</span><span class="sxs-lookup"><span data-stu-id="219ef-167">To improve performance, it incorporates `hint.shufflekey`:</span></span>

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a><span data-ttu-id="219ef-168">Scenari di query</span><span class="sxs-lookup"><span data-stu-id="219ef-168">Query scenarios</span></span>

### <a name="identify-unique-processes-with-process-ids"></a><span data-ttu-id="219ef-169">Identificare i processi univoci con gli ID processo</span><span class="sxs-lookup"><span data-stu-id="219ef-169">Identify unique processes with process IDs</span></span>
<span data-ttu-id="219ef-170">Gli ID processo (PID) sono riciclati in Windows e riutilizzati per i nuovi processi.</span><span class="sxs-lookup"><span data-stu-id="219ef-170">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="219ef-171">Di per sé, non possono servire come identificatori univoci per processi specifici.</span><span class="sxs-lookup"><span data-stu-id="219ef-171">On their own, they can't serve as unique identifiers for specific processes.</span></span>

<span data-ttu-id="219ef-172">Per ottenere un identificatore univoco per un computer specifico, usare l'ID processo insieme all'ora di creazione del processo.</span><span class="sxs-lookup"><span data-stu-id="219ef-172">To get a unique identifier for a process on a specific machine, use the process ID together with the process creation time.</span></span> <span data-ttu-id="219ef-173">Quando si uniscono o si riepilogano i dati relativi a processi, includere le colonne per l'identificatore del computer (`DeviceId` o `DeviceName`), l'ID processo (`ProcessId` o `InitiatingProcessId`) e l'ora di creazione del processo (`ProcessCreationTime` o `InitiatingProcessCreationTime`)</span><span class="sxs-lookup"><span data-stu-id="219ef-173">When you join or summarize data around processes, include columns for the machine identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`)</span></span>

<span data-ttu-id="219ef-174">La seguente query di esempio trova i processi che accedono a più di 10 indirizzi IP dalla porta 445 (SMB), possibilmente analizzando le condivisioni file.</span><span class="sxs-lookup"><span data-stu-id="219ef-174">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

<span data-ttu-id="219ef-175">Query di esempio:</span><span class="sxs-lookup"><span data-stu-id="219ef-175">Example query:</span></span>
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="219ef-176">La query riepiloga sia `InitiatingProcessId` che `InitiatingProcessCreationTime` in modo da visualizzare un singolo processo, senza combinare più processi con lo stesso ID processo.</span><span class="sxs-lookup"><span data-stu-id="219ef-176">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="query-command-lines"></a><span data-ttu-id="219ef-177">Righe di comando di query</span><span class="sxs-lookup"><span data-stu-id="219ef-177">Query command lines</span></span>
<span data-ttu-id="219ef-178">Esistono diversi modi per creare una riga di comando per eseguire un'attività.</span><span class="sxs-lookup"><span data-stu-id="219ef-178">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="219ef-179">Ad esempio, un utente malintenzionato può fare riferimento a un file di immagine senza un percorso, senza un'estensione di file, utilizzando variabili di ambiente o con virgolette.</span><span class="sxs-lookup"><span data-stu-id="219ef-179">For example, an attacker could reference an image file without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="219ef-180">L'utente malintenzionato può anche modificare l'ordine dei parametri o aggiungere più virgolette e spazi.</span><span class="sxs-lookup"><span data-stu-id="219ef-180">The attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="219ef-181">Per creare query più durevoli sulle righe di comando, applicare le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="219ef-181">To create more durable queries around command lines, apply the following practices:</span></span>

- <span data-ttu-id="219ef-182">Identificare i processi noti, ad esempio *net.exe* o *psexec.exe*, in base ai campi del nome di file anziché filtrare nella riga di comando stessa.</span><span class="sxs-lookup"><span data-stu-id="219ef-182">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the file name fields, instead of filtering on the command-line itself.</span></span>
- <span data-ttu-id="219ef-183">Analizzare le sezioni della riga di comando utilizzando la [funzione parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span><span class="sxs-lookup"><span data-stu-id="219ef-183">Parse command-line sections using the [parse_command_line() function](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line)</span></span> 
- <span data-ttu-id="219ef-184">Quando si eseguono query per gli argomenti della riga di comando, non cercare una corrispondenza esatta su più argomenti non correlati in un determinato ordine.</span><span class="sxs-lookup"><span data-stu-id="219ef-184">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="219ef-185">Usare invece espressioni regolari o utilizzare più operatori distinti.</span><span class="sxs-lookup"><span data-stu-id="219ef-185">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="219ef-186">Usare corrispondenza maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="219ef-186">Use case insensitive matches.</span></span> <span data-ttu-id="219ef-187">Ad esempio, utilizzare `=~` , `in~` e `contains` invece di `==` , `in` e `contains_cs` .</span><span class="sxs-lookup"><span data-stu-id="219ef-187">For example, use `=~`, `in~`, and `contains` instead of `==`, `in`, and `contains_cs`.</span></span>
- <span data-ttu-id="219ef-188">Per attenuare le tecniche di offuscamento della riga di comando, valutare la possibilità di rimuovere le virgolette, sostituire le virgole con spazi e sostituire più spazi consecutivi con un singolo spazio.</span><span class="sxs-lookup"><span data-stu-id="219ef-188">To mitigate command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="219ef-189">Sono disponibili tecniche di offuscamento più complesse che richiedono altri approcci, ma queste modifiche possono essere utili per l'indirizzamento di quelle comuni.</span><span class="sxs-lookup"><span data-stu-id="219ef-189">There are more complex obfuscation techniques that require other approaches, but these tweaks can help address common ones.</span></span>

<span data-ttu-id="219ef-190">Negli esempi seguenti vengono illustrati diversi modi per creare una query che cerca il file *net.exe* per arrestare il servizio firewall "MPSSVC":</span><span class="sxs-lookup"><span data-stu-id="219ef-190">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the firewall service "MpsSvc":</span></span>

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

### <a name="ingest-data-from-external-sources"></a><span data-ttu-id="219ef-191">Ingestione dei dati da origini esterne</span><span class="sxs-lookup"><span data-stu-id="219ef-191">Ingest data from external sources</span></span>
<span data-ttu-id="219ef-192">Per incorporare elenchi lunghi o tabelle di grandi dimensioni nella query, utilizzare l' [operatore externaldata](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) per ingerire dati da un URI specificato.</span><span class="sxs-lookup"><span data-stu-id="219ef-192">To incorporate long lists or large tables into your query, use the [externaldata operator](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) to ingest data from a specified URI.</span></span> <span data-ttu-id="219ef-193">È possibile ottenere dati da file in formato TXT, CSV, JSON o in [altri formati](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span><span class="sxs-lookup"><span data-stu-id="219ef-193">You can get data from files in TXT, CSV, JSON, or [other formats](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats).</span></span> <span data-ttu-id="219ef-194">Nell'esempio seguente viene illustrato come utilizzare l'elenco completo degli hash SHA-256 di malware forniti da MalwareBazaar (abuse.ch) per controllare gli allegati nei messaggi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="219ef-194">The example below shows how you can utilize the extensive list of malware SHA-256  hashes provided by MalwareBazaar (abuse.ch) to check attachments on emails:</span></span>

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

### <a name="parse-strings"></a><span data-ttu-id="219ef-195">Stringhe di analisi</span><span class="sxs-lookup"><span data-stu-id="219ef-195">Parse strings</span></span>
<span data-ttu-id="219ef-196">Esistono diverse funzioni che è possibile utilizzare per gestire in modo efficiente le stringhe che richiedono l'analisi o la conversione.</span><span class="sxs-lookup"><span data-stu-id="219ef-196">There are various functions you can use to efficiently handle strings that need parsing or conversion.</span></span> 

| <span data-ttu-id="219ef-197">Stringa</span><span class="sxs-lookup"><span data-stu-id="219ef-197">String</span></span> | <span data-ttu-id="219ef-198">Funzione</span><span class="sxs-lookup"><span data-stu-id="219ef-198">Function</span></span> | <span data-ttu-id="219ef-199">Esempio di utilizzo</span><span class="sxs-lookup"><span data-stu-id="219ef-199">Usage example</span></span> |
|--|--|--|
| <span data-ttu-id="219ef-200">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="219ef-200">Command-lines</span></span> | [<span data-ttu-id="219ef-201">parse_command_line ()</span><span class="sxs-lookup"><span data-stu-id="219ef-201">parse_command_line()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | <span data-ttu-id="219ef-202">Estrarre il comando e tutti gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="219ef-202">Extract the command and all arguments.</span></span> | 
| <span data-ttu-id="219ef-203">Percorsi</span><span class="sxs-lookup"><span data-stu-id="219ef-203">Paths</span></span> | [<span data-ttu-id="219ef-204">parse_path ()</span><span class="sxs-lookup"><span data-stu-id="219ef-204">parse_path()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | <span data-ttu-id="219ef-205">Estrarre le sezioni di un percorso di file o cartella.</span><span class="sxs-lookup"><span data-stu-id="219ef-205">Extract the sections of a file or folder path.</span></span> |
| <span data-ttu-id="219ef-206">Numeri di versione</span><span class="sxs-lookup"><span data-stu-id="219ef-206">Version numbers</span></span> | [<span data-ttu-id="219ef-207">parse_version ()</span><span class="sxs-lookup"><span data-stu-id="219ef-207">parse_version()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | <span data-ttu-id="219ef-208">Deconstruct un numero di versione con un massimo di quattro sezioni e fino a otto caratteri per sezione.</span><span class="sxs-lookup"><span data-stu-id="219ef-208">Deconstruct a version number with up to four sections and up to eight characters per section.</span></span> <span data-ttu-id="219ef-209">Utilizzare i dati analizzati per confrontare la versione di Age.</span><span class="sxs-lookup"><span data-stu-id="219ef-209">Use the parsed data to compare version age.</span></span> |
| <span data-ttu-id="219ef-210">Indirizzi IPv4</span><span class="sxs-lookup"><span data-stu-id="219ef-210">IPv4 addresses</span></span> | [<span data-ttu-id="219ef-211">parse_ipv4 ()</span><span class="sxs-lookup"><span data-stu-id="219ef-211">parse_ipv4()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | <span data-ttu-id="219ef-212">Convertire un indirizzo IPv4 in un numero intero lungo.</span><span class="sxs-lookup"><span data-stu-id="219ef-212">Convert an IPv4 address to a long integer.</span></span> <span data-ttu-id="219ef-213">Per confrontare gli indirizzi IPv4 senza convertirli, utilizzare [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="219ef-213">To compare IPv4 addresses without converting them, use [ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction).</span></span> |
| <span data-ttu-id="219ef-214">Indirizzi IPv6</span><span class="sxs-lookup"><span data-stu-id="219ef-214">IPv6 addresses</span></span> | [<span data-ttu-id="219ef-215">parse_ipv6 ()</span><span class="sxs-lookup"><span data-stu-id="219ef-215">parse_ipv6()</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | <span data-ttu-id="219ef-216">Convertire un indirizzo IPv4 o IPv6 nella notazione IPv6 canonica.</span><span class="sxs-lookup"><span data-stu-id="219ef-216">Convert an IPv4 or IPv6 address to the canonical IPv6 notation.</span></span> <span data-ttu-id="219ef-217">Per confrontare gli indirizzi IPv6, utilizzare [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span><span class="sxs-lookup"><span data-stu-id="219ef-217">To compare IPv6 addresses, use [ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction).</span></span> |

<span data-ttu-id="219ef-218">Per informazioni su tutte le funzioni di analisi supportate, [vedere informazioni sulle funzioni di stringa di Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span><span class="sxs-lookup"><span data-stu-id="219ef-218">To learn about all supported parsing functions, [read about Kusto string functions](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="219ef-219">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="219ef-219">Related topics</span></span>
- [<span data-ttu-id="219ef-220">Documentazione relativa alla lingua di query di Kusto</span><span class="sxs-lookup"><span data-stu-id="219ef-220">Kusto query language documentation</span></span>](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [<span data-ttu-id="219ef-221">Limiti di servizio</span><span class="sxs-lookup"><span data-stu-id="219ef-221">Service limits</span></span>](advanced-hunting-limits.md)
- [<span data-ttu-id="219ef-222">Gestire gli errori di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="219ef-222">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="219ef-223">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="219ef-223">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="219ef-224">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="219ef-224">Learn the query language</span></span>](advanced-hunting-query-language.md)
