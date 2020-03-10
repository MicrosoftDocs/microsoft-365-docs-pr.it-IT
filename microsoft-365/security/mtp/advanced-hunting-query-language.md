---
title: Il linguaggio delle query in Ricerca avanzata in Microsoft Threat Protection
description: Creare una prima query di ricerca delle minacce, conoscere gli operatori più comuni e altri aspetti del linguaggio di query di Ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, language, Learn, First query, telemetria, eventi, telemetria, rilevamenti personalizzati, schema, kusto, operatori, tipi di dati, PowerShell Download, esempio di query
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
ms.openlocfilehash: 7f2cf7f62060774343354467d27b76456f6581fc
ms.sourcegitcommit: cc3b64a91e16ccdaa9c338b9a9056dbe3963ba9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2020
ms.locfileid: "42567031"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="a045e-104">Scoprire il linguaggio delle query in Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="a045e-104">Learn the advanced hunting query language</span></span>

<span data-ttu-id="a045e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a045e-105">**Applies to:**</span></span>
- <span data-ttu-id="a045e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a045e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a045e-107">Ricerca avanzata si basa sul [linguaggio delle query in Esplora dati](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="a045e-107">Advanced hunting is based on the [Kusto query language](https://docs.microsoft.com/azure/kusto/query/).</span></span> <span data-ttu-id="a045e-108">È possibile usare la sintassi e gli operatori di Esplora dati per creare query che individuano informazioni nello [schema](advanced-hunting-schema-tables.md) specificamente strutturate per Ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="a045e-108">You can use Kusto syntax and operators to construct queries that locate information in the [schema](advanced-hunting-schema-tables.md) specifically structured for advanced hunting.</span></span> <span data-ttu-id="a045e-109">Per comprendere meglio questi concetti, eseguire la prima query.</span><span class="sxs-lookup"><span data-stu-id="a045e-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="a045e-110">Provare la prima query</span><span class="sxs-lookup"><span data-stu-id="a045e-110">Try your first query</span></span>

<span data-ttu-id="a045e-111">In Microsoft 365 Security Center, andare a **caccia** per eseguire la prima query.</span><span class="sxs-lookup"><span data-stu-id="a045e-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="a045e-112">Usare l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a045e-112">Use the following example:</span></span>

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="a045e-113">Questo è come apparirà in Ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="a045e-113">This is how it will look like in advanced hunting.</span></span>

![Immagine della query di ricerca avanzata di Microsoft Threat Protection](../../media/advanced-hunting-query-example.png)

<span data-ttu-id="a045e-115">All'inizio della query è stato aggiunto un breve commento per descrivere il relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="a045e-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="a045e-116">Ciò aiuta se in seguito si decide di salvare la query e condividerla con altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a045e-116">This helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="a045e-117">La query viene in genere avviata con un nome di tabella seguito da una serie di elementi avviati da una pipe (`|`).</span><span class="sxs-lookup"><span data-stu-id="a045e-117">The query itself will typically start with a table name followed by a series of elements started by a pipe (`|`).</span></span> <span data-ttu-id="a045e-118">In questo esempio viene avviata la creazione di un'Unione di due tabelle `DeviceProcessEvents` e `DeviceNetworkEvents`, quindi, vengono aggiunti gli elementi reindirizzati in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="a045e-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
<span data-ttu-id="a045e-119">Il primo elemento con pipe è un filtro temporale che ha come ambito i sette giorni precedenti.</span><span class="sxs-lookup"><span data-stu-id="a045e-119">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="a045e-120">Il mantenimento dell'intervallo di tempo il più possibile ravvicinato assicura che le query vengano eseguite bene, che restituiscano risultati gestibili e che non scadano.</span><span class="sxs-lookup"><span data-stu-id="a045e-120">Keeping the time range as narrow as possible ensures that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

<span data-ttu-id="a045e-121">L'intervallo di tempo è subito seguito da una ricerca dei nomi dei file di processo che rappresentano l'applicazione PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a045e-121">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

<span data-ttu-id="a045e-122">Successivamente, la query Cerca stringhe nelle righe di comando che vengono in genere utilizzate per scaricare i file tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a045e-122">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
```
<span data-ttu-id="a045e-123">Ora che la query identifica chiaramente i dati da individuare, è possibile aggiungere elementi che definiscono come appaiono i risultati.</span><span class="sxs-lookup"><span data-stu-id="a045e-123">Now that your query clearly identifies the data you want to locate, you can add elements that define what the results look like.</span></span> <span data-ttu-id="a045e-124">`project`restituisce colonne specifiche e `top` limita il numero di risultati, contribuendo a garantire che i risultati siano ben formattati e ragionevolmente grandi e facili da elaborare.</span><span class="sxs-lookup"><span data-stu-id="a045e-124">`project` returns specific columns and `top` limits the number of results, helping ensure the results well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="a045e-125">Fare clic su **Esegui query** per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="a045e-125">Click **Run query** to see the results.</span></span> <span data-ttu-id="a045e-126">Selezionare l'icona Espandi nell'angolo superiore destro dell'editor di query per concentrarsi sulla query di caccia e sui risultati.</span><span class="sxs-lookup"><span data-stu-id="a045e-126">Select the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span>

![Immagine del controllo Espandi nell'editor di query di ricerca avanzata](../../media/advanced-hunting-expand.png)

## <a name="learn-common-query-operators-for-advanced-hunting"></a><span data-ttu-id="a045e-128">Informazioni sugli operatori di query più comuni per la Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="a045e-128">Learn common query operators for advanced hunting</span></span>

<span data-ttu-id="a045e-129">Ora che è stata eseguita la prima query e si ha un'idea generale dei relativi componenti, è il momento di tornare indietro e imparare alcune nozioni di base.</span><span class="sxs-lookup"><span data-stu-id="a045e-129">Now that you've run your first query and have a general idea of its components, it's time to backtrack a little bit and learn some basics.</span></span> <span data-ttu-id="a045e-130">Il linguaggio delle query di Esplora dati usato in Ricerca avanzata supporta una serie di operatori, di seguito sono elencati i più comuni.</span><span class="sxs-lookup"><span data-stu-id="a045e-130">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="a045e-131">Operatore</span><span class="sxs-lookup"><span data-stu-id="a045e-131">Operator</span></span> | <span data-ttu-id="a045e-132">Descrizione e utilizzo</span><span class="sxs-lookup"><span data-stu-id="a045e-132">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="a045e-133">Filtrare una tabella nel sottoinsieme di righe che soddisfano un predicato.</span><span class="sxs-lookup"><span data-stu-id="a045e-133">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="a045e-134">Creare una tabella che aggrega il contenuto della tabella di input.</span><span class="sxs-lookup"><span data-stu-id="a045e-134">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="a045e-135">Unire le righe di due tabelle per creare una nuova tabella in base ai valori corrispondenti delle colonne specificate di ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="a045e-135">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="a045e-136">Restituire il numero di record nel set di record di input.</span><span class="sxs-lookup"><span data-stu-id="a045e-136">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="a045e-137">Restituire i primi N record ordinati in base alle colonne specificate.</span><span class="sxs-lookup"><span data-stu-id="a045e-137">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="a045e-138">Tornare al numero specificato di righe.</span><span class="sxs-lookup"><span data-stu-id="a045e-138">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="a045e-139">Selezionare le colonne da includere, rinominare o rilasciare e inserire nuove colonne calcolate.</span><span class="sxs-lookup"><span data-stu-id="a045e-139">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="a045e-140">Creare colonne calcolate e accodarle al set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a045e-140">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="a045e-141">Restituire una matrice dinamica (JSON) del set di valori distinti che Expr accetta nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="a045e-141">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="a045e-142">Trovare le righe che corrispondono a un predicato in un set di tabelle.</span><span class="sxs-lookup"><span data-stu-id="a045e-142">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="a045e-143">Per vedere un esempio pratico di questi operatori, eseguirli nella sezione **Introduzione** in Ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="a045e-143">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types-and-their-query-syntax-implications"></a><span data-ttu-id="a045e-144">Informazioni sui tipi di dati e sulle implicazioni della sintassi delle query</span><span class="sxs-lookup"><span data-stu-id="a045e-144">Understand data types and their query syntax implications</span></span>

<span data-ttu-id="a045e-145">I dati nelle tabelle di Ricerca avanzata sono generalmente classificati nei seguenti tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="a045e-145">Data in advanced hunting tables are generally classified into the following data types.</span></span>

| <span data-ttu-id="a045e-146">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a045e-146">Data type</span></span> | <span data-ttu-id="a045e-147">Descrizione e implicazioni delle query</span><span class="sxs-lookup"><span data-stu-id="a045e-147">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="a045e-148">Informazioni sui dati e sull'ora che rappresentano in genere timestamp dell'evento</span><span class="sxs-lookup"><span data-stu-id="a045e-148">Data and time information typically representing event timestamps</span></span> |
| `string` | <span data-ttu-id="a045e-149">Stringa di caratteri</span><span class="sxs-lookup"><span data-stu-id="a045e-149">Character string</span></span> |
| `bool` | <span data-ttu-id="a045e-150">True o False</span><span class="sxs-lookup"><span data-stu-id="a045e-150">True or false</span></span> |
| `int` | <span data-ttu-id="a045e-151">Valore numerico 32 bit</span><span class="sxs-lookup"><span data-stu-id="a045e-151">32-bit numeric value</span></span>  |
| `long` | <span data-ttu-id="a045e-152">Valore numerico 64 bit</span><span class="sxs-lookup"><span data-stu-id="a045e-152">64-bit numeric value</span></span> |

## <a name="use-sample-queries"></a><span data-ttu-id="a045e-153">Usare query di esempio</span><span class="sxs-lookup"><span data-stu-id="a045e-153">Use sample queries</span></span>

<span data-ttu-id="a045e-154">La sezione **Introduzione** presenta alcune semplici query che impiegano operatori di uso comune.</span><span class="sxs-lookup"><span data-stu-id="a045e-154">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="a045e-155">Provare a eseguire queste query e apportare piccole modifiche.</span><span class="sxs-lookup"><span data-stu-id="a045e-155">Try running these queries and making small modifications to them.</span></span>

![Immagine della finestra di Ricerca avanzata](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="a045e-157">Oltre agli esempi di query di base, è anche possibile accedere [query condivise](advanced-hunting-shared-queries.md) per specifici scenari di ricerca delle minacce.</span><span class="sxs-lookup"><span data-stu-id="a045e-157">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="a045e-158">Esplorare le query condivise sul lato sinistro della pagina o sul repository di query GitHub.</span><span class="sxs-lookup"><span data-stu-id="a045e-158">Explore the shared queries on the left side of the page or the GitHub query repository.</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="a045e-159">Documentazione sulle query</span><span class="sxs-lookup"><span data-stu-id="a045e-159">Access query language documentation</span></span>

<span data-ttu-id="a045e-160">Per altre informazioni sul linguaggio delle query di Esplora dati e sugli operatori supportati, vedere [Documentazione sul linguaggio delle query di Esplora dati](https://docs.microsoft.com/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="a045e-160">For more information on Kusto query language and supported operators, see [Kusto query language documentation](https://docs.microsoft.com/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a045e-161">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a045e-161">Related topics</span></span>
- [<span data-ttu-id="a045e-162">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="a045e-162">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a045e-163">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="a045e-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a045e-164">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="a045e-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a045e-165">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="a045e-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a045e-166">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="a045e-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
