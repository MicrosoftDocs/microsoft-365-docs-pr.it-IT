---
title: Informazioni sul linguaggio di query di ricerca avanzata in Microsoft 365 Defender
description: Creare una prima query di ricerca delle minacce, conoscere gli operatori più comuni e altri aspetti del linguaggio di query di Ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, lingua, imparare, prima query, telemetria, eventi, telemetria, rilevamenti personalizzati, schema, kusto, operatori, tipi di dati, download di powershell, esempio di query
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f996cd00cc2f7a1f1de2540f1d6686d26431c4f4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904080"
---
# <a name="learn-the-advanced-hunting-query-language"></a><span data-ttu-id="0311c-104">Scoprire il linguaggio delle query in Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="0311c-104">Learn the advanced hunting query language</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0311c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0311c-105">**Applies to:**</span></span>
- <span data-ttu-id="0311c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0311c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0311c-107">Ricerca avanzata si basa sul [linguaggio delle query in Esplora dati](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="0311c-107">Advanced hunting is based on the [Kusto query language](/azure/kusto/query/).</span></span> <span data-ttu-id="0311c-108">È possibile utilizzare gli operatori e le istruzioni Kusto per creare query che individuano informazioni in uno [schema specializzato.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="0311c-108">You can use Kusto operators and statements to construct queries that locate information in a specialized [schema](advanced-hunting-schema-tables.md).</span></span> <span data-ttu-id="0311c-109">Per comprendere meglio questi concetti, eseguire la prima query.</span><span class="sxs-lookup"><span data-stu-id="0311c-109">To understand these concepts better, run your first query.</span></span>

## <a name="try-your-first-query"></a><span data-ttu-id="0311c-110">Provare la prima query</span><span class="sxs-lookup"><span data-stu-id="0311c-110">Try your first query</span></span>

<span data-ttu-id="0311c-111">Nel Centro sicurezza Microsoft 365 passare a **Ricerca per** eseguire la prima query.</span><span class="sxs-lookup"><span data-stu-id="0311c-111">In Microsoft 365 security center, go to **Hunting** to run your first query.</span></span> <span data-ttu-id="0311c-112">Usare l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0311c-112">Use the following example:</span></span>

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

<span data-ttu-id="0311c-113">**[Eseguire questa query nella ricerca avanzata](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span><span class="sxs-lookup"><span data-stu-id="0311c-113">**[Run this query in advanced hunting](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**</span></span>

### <a name="describe-the-query-and-specify-the-tables-to-search"></a><span data-ttu-id="0311c-114">Descrivere la query e specificare le tabelle in cui eseguire la ricerca</span><span class="sxs-lookup"><span data-stu-id="0311c-114">Describe the query and specify the tables to search</span></span>
<span data-ttu-id="0311c-115">All'inizio della query è stato aggiunto un breve commento per descriverlo.</span><span class="sxs-lookup"><span data-stu-id="0311c-115">A short comment has been added to the beginning of the query to describe what it is for.</span></span> <span data-ttu-id="0311c-116">Questo commento è utile se successivamente si decide di salvare la query e condividerla con altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0311c-116">This comment helps if you later decide to save the query and share it with others in your organization.</span></span> 

```kusto
// Finds PowerShell execution events that could involve a download
```

<span data-ttu-id="0311c-117">La query stessa inizierà in genere con un nome di tabella seguito da diversi elementi che iniziano con una pipe ( `|` ).</span><span class="sxs-lookup"><span data-stu-id="0311c-117">The query itself will typically start with a table name followed by several elements that start with a pipe (`|`).</span></span> <span data-ttu-id="0311c-118">In questo esempio si inizia creando un'unione di due tabelle e e si aggiungono elementi  `DeviceProcessEvents` tramite pipe in base alle `DeviceNetworkEvents` esigenze.</span><span class="sxs-lookup"><span data-stu-id="0311c-118">In this example, we start by creating a union of two tables,  `DeviceProcessEvents` and `DeviceNetworkEvents`, and add piped elements as needed.</span></span>

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a><span data-ttu-id="0311c-119">Impostare l'intervallo di tempo</span><span class="sxs-lookup"><span data-stu-id="0311c-119">Set the time range</span></span>
<span data-ttu-id="0311c-120">Il primo elemento con pipe è un filtro temporale con ambito per i sette giorni precedenti.</span><span class="sxs-lookup"><span data-stu-id="0311c-120">The first piped element is a time filter scoped to the previous seven days.</span></span> <span data-ttu-id="0311c-121">La limitazione dell'intervallo di tempo garantisce che le query funzionino bene, restituiscono risultati gestibili e non si esercitino timeout.</span><span class="sxs-lookup"><span data-stu-id="0311c-121">Limiting the time range helps ensure that queries perform well, return manageable results, and don't time out.</span></span>

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a><span data-ttu-id="0311c-122">Controllare processi specifici</span><span class="sxs-lookup"><span data-stu-id="0311c-122">Check specific processes</span></span>
<span data-ttu-id="0311c-123">L'intervallo di tempo è immediatamente seguito da una ricerca di nomi di file di processo che rappresentano l'applicazione PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0311c-123">The time range is immediately followed by a search for process file names representing the PowerShell application.</span></span>

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a><span data-ttu-id="0311c-124">Cercare stringhe di comando specifiche</span><span class="sxs-lookup"><span data-stu-id="0311c-124">Search for specific command strings</span></span>
<span data-ttu-id="0311c-125">In seguito, la query cerca le stringhe nelle righe di comando che in genere vengono usate per scaricare i file tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0311c-125">Afterwards, the query looks for strings in command lines that are typically used to download files using PowerShell.</span></span>

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

### <a name="customize-result-columns-and-length"></a><span data-ttu-id="0311c-126">Personalizzare le colonne dei risultati e la lunghezza</span><span class="sxs-lookup"><span data-stu-id="0311c-126">Customize result columns and length</span></span> 
<span data-ttu-id="0311c-127">Ora che la query identifica chiaramente i dati che si desidera individuare, è possibile definire l'aspetto dei risultati.</span><span class="sxs-lookup"><span data-stu-id="0311c-127">Now that your query clearly identifies the data you want to locate, you can define what the results look like.</span></span> <span data-ttu-id="0311c-128">`project` restituisce colonne specifiche e `top` limita il numero di risultati.</span><span class="sxs-lookup"><span data-stu-id="0311c-128">`project` returns specific columns, and `top` limits the number of results.</span></span> <span data-ttu-id="0311c-129">Questi operatori assicurano che i risultati siano ben formattati e ragionevolmente grandi e facili da elaborare.</span><span class="sxs-lookup"><span data-stu-id="0311c-129">These operators help ensure the results are well-formatted and reasonably large and easy to process.</span></span>

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

<span data-ttu-id="0311c-130">Selezionare **Esegui query** per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0311c-130">Select **Run query** to see the results.</span></span> <span data-ttu-id="0311c-131">Utilizzare l'icona di espansione nella parte superiore destra dell'editor di query per concentrarsi sulla query di ricerca e sui risultati.</span><span class="sxs-lookup"><span data-stu-id="0311c-131">Use the expand icon at the top right of the query editor to focus on your hunting query and the results.</span></span> 

![Immagine del controllo Expand nell'editor di query di ricerca avanzata](../../media/advanced-hunting-expand.png)

>[!TIP]
><span data-ttu-id="0311c-133">È possibile visualizzare i risultati delle query come grafici e regolare rapidamente i filtri.</span><span class="sxs-lookup"><span data-stu-id="0311c-133">You can view query results as charts and quickly adjust filters.</span></span> <span data-ttu-id="0311c-134">Per informazioni dettagliate, [vedere Utilizzo dei risultati delle query](advanced-hunting-query-results.md)</span><span class="sxs-lookup"><span data-stu-id="0311c-134">For guidance, [read about working with query results](advanced-hunting-query-results.md)</span></span>

## <a name="learn-common-query-operators"></a><span data-ttu-id="0311c-135">Informazioni su operatori di query comuni</span><span class="sxs-lookup"><span data-stu-id="0311c-135">Learn common query operators</span></span>

<span data-ttu-id="0311c-136">È stata appena eseguita la prima query e si ha un'idea generale dei relativi componenti.</span><span class="sxs-lookup"><span data-stu-id="0311c-136">You've just run your first query and have a general idea of its components.</span></span> <span data-ttu-id="0311c-137">È il momento di eseguire il backtracking leggermente e apprendere alcune nozioni di base.</span><span class="sxs-lookup"><span data-stu-id="0311c-137">It's time to backtrack slightly and learn some basics.</span></span> <span data-ttu-id="0311c-138">Il linguaggio delle query di Esplora dati usato in Ricerca avanzata supporta una serie di operatori, di seguito sono elencati i più comuni.</span><span class="sxs-lookup"><span data-stu-id="0311c-138">The Kusto query language used by advanced hunting supports a range of operators, including the following common ones.</span></span>

| <span data-ttu-id="0311c-139">Operatore</span><span class="sxs-lookup"><span data-stu-id="0311c-139">Operator</span></span> | <span data-ttu-id="0311c-140">Descrizione e utilizzo</span><span class="sxs-lookup"><span data-stu-id="0311c-140">Description and usage</span></span> |
|--|--|
| `where` | <span data-ttu-id="0311c-141">Filtrare una tabella nel sottoinsieme di righe che soddisfano un predicato.</span><span class="sxs-lookup"><span data-stu-id="0311c-141">Filter a table to the subset of rows that satisfy a predicate.</span></span> |
| `summarize` | <span data-ttu-id="0311c-142">Creare una tabella che aggrega il contenuto della tabella di input.</span><span class="sxs-lookup"><span data-stu-id="0311c-142">Produce a table that aggregates the content of the input table.</span></span> |
| `join` | <span data-ttu-id="0311c-143">Unire le righe di due tabelle per creare una nuova tabella in base ai valori corrispondenti delle colonne specificate di ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="0311c-143">Merge the rows of two tables to form a new table by matching values of the specified column(s) from each table.</span></span> |
| `count` | <span data-ttu-id="0311c-144">Restituire il numero di record nel set di record di input.</span><span class="sxs-lookup"><span data-stu-id="0311c-144">Return the number of records in the input record set.</span></span> |
| `top` | <span data-ttu-id="0311c-145">Restituire i primi N record ordinati in base alle colonne specificate.</span><span class="sxs-lookup"><span data-stu-id="0311c-145">Return the first N records sorted by the specified columns.</span></span> |
| `limit` | <span data-ttu-id="0311c-146">Tornare al numero specificato di righe.</span><span class="sxs-lookup"><span data-stu-id="0311c-146">Return up to the specified number of rows.</span></span> |
| `project` | <span data-ttu-id="0311c-147">Selezionare le colonne da includere, rinominare o rilasciare e inserire nuove colonne calcolate.</span><span class="sxs-lookup"><span data-stu-id="0311c-147">Select the columns to include, rename or drop, and insert new computed columns.</span></span> |
| `extend` | <span data-ttu-id="0311c-148">Creare colonne calcolate e accodarle al set di risultati.</span><span class="sxs-lookup"><span data-stu-id="0311c-148">Create calculated columns and append them to the result set.</span></span> |
| `makeset` |  <span data-ttu-id="0311c-149">Restituire una matrice dinamica (JSON) del set di valori distinti che Expr accetta nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="0311c-149">Return a dynamic (JSON) array of the set of distinct values that Expr takes in the group.</span></span> |
| `find` | <span data-ttu-id="0311c-150">Trovare le righe che corrispondono a un predicato in un set di tabelle.</span><span class="sxs-lookup"><span data-stu-id="0311c-150">Find rows that match a predicate across a set of tables.</span></span> |

<span data-ttu-id="0311c-151">Per vedere un esempio pratico di questi operatori, eseguirli nella sezione **Introduzione** in Ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="0311c-151">To see a live example of these operators, run them from the **Get started** section in advanced hunting.</span></span>

## <a name="understand-data-types"></a><span data-ttu-id="0311c-152">Informazioni sui tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0311c-152">Understand data types</span></span>

<span data-ttu-id="0311c-153">La ricerca avanzata supporta i tipi di dati Kusto, inclusi i tipi comuni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0311c-153">Advanced hunting supports Kusto data types, including the following common types:</span></span>

| <span data-ttu-id="0311c-154">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0311c-154">Data type</span></span> | <span data-ttu-id="0311c-155">Descrizione e implicazioni delle query</span><span class="sxs-lookup"><span data-stu-id="0311c-155">Description and query implications</span></span> |
|--|--|
| `datetime` | <span data-ttu-id="0311c-156">Informazioni sui dati e sull'ora che in genere rappresentano i timestamp degli eventi.</span><span class="sxs-lookup"><span data-stu-id="0311c-156">Data and time information typically representing event timestamps.</span></span> [<span data-ttu-id="0311c-157">Vedere formati di datetime supportati</span><span class="sxs-lookup"><span data-stu-id="0311c-157">See supported datetime formats</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | <span data-ttu-id="0311c-158">Stringa di caratteri in FORMATO UTF-8 racchiusa tra virgolette singole ( ) o `'` doppie ( `"` ).</span><span class="sxs-lookup"><span data-stu-id="0311c-158">Character string in UTF-8 enclosed in single quotes (`'`) or double quotes (`"`).</span></span> [<span data-ttu-id="0311c-159">Altre informazioni sulle stringhe</span><span class="sxs-lookup"><span data-stu-id="0311c-159">Read more about strings</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | <span data-ttu-id="0311c-160">Questo tipo di dati supporta `true` o `false` gli stati.</span><span class="sxs-lookup"><span data-stu-id="0311c-160">This data type supports `true` or `false` states.</span></span> [<span data-ttu-id="0311c-161">Vedere operatori e valori letterali supportati</span><span class="sxs-lookup"><span data-stu-id="0311c-161">See supported literals and operators</span></span>](/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | <span data-ttu-id="0311c-162">Numero intero a 32 bit</span><span class="sxs-lookup"><span data-stu-id="0311c-162">32-bit integer</span></span>  |
| `long` | <span data-ttu-id="0311c-163">Numero intero a 64 bit</span><span class="sxs-lookup"><span data-stu-id="0311c-163">64-bit integer</span></span> |

<span data-ttu-id="0311c-164">Per ulteriori informazioni su questi tipi di dati, [vedere Kusto scalar data types](/azure/data-explorer/kusto/query/scalar-data-types/).</span><span class="sxs-lookup"><span data-stu-id="0311c-164">To learn more about these data types, [read about Kusto scalar data types](/azure/data-explorer/kusto/query/scalar-data-types/).</span></span>

## <a name="get-help-as-you-write-queries"></a><span data-ttu-id="0311c-165">Ottenere assistenza nella scrittura delle query</span><span class="sxs-lookup"><span data-stu-id="0311c-165">Get help as you write queries</span></span>
<span data-ttu-id="0311c-166">Trarre vantaggio dalle seguenti funzionalità per scrivere query più velocemente:</span><span class="sxs-lookup"><span data-stu-id="0311c-166">Take advantage of the following functionality to write queries faster:</span></span>
- <span data-ttu-id="0311c-167">**Autosuggest:** quando si scrivono query, la ricerca avanzata fornisce suggerimenti da IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="0311c-167">**Autosuggest**—as you write queries, advanced hunting provides suggestions from IntelliSense.</span></span> 
- <span data-ttu-id="0311c-168">**Albero dello** schema: una rappresentazione dello schema che include l'elenco di tabelle e le relative colonne viene fornita accanto all'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0311c-168">**Schema tree**—a schema representation that includes the list of tables and their columns is provided next to your working area.</span></span> <span data-ttu-id="0311c-169">Per altre informazioni, passare il puntatore su un elemento.</span><span class="sxs-lookup"><span data-stu-id="0311c-169">For more information, hover over an item.</span></span> <span data-ttu-id="0311c-170">Fare doppio clic su un elemento per inserirlo nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="0311c-170">Double-click an item to insert it to the query editor.</span></span>
- <span data-ttu-id="0311c-171">**[Riferimento allo](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** schema: riferimento nel portale con descrizioni di tabelle e colonne, tipi di eventi supportati (valori) `ActionType` e query di esempio</span><span class="sxs-lookup"><span data-stu-id="0311c-171">**[Schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**—in-portal reference with table and column descriptions as well as supported event types (`ActionType` values) and sample queries</span></span>

## <a name="work-with-multiple-queries-in-the-editor"></a><span data-ttu-id="0311c-172">Utilizzare più query nell'editor</span><span class="sxs-lookup"><span data-stu-id="0311c-172">Work with multiple queries in the editor</span></span>
<span data-ttu-id="0311c-173">È possibile utilizzare l'editor di query per sperimentare più query.</span><span class="sxs-lookup"><span data-stu-id="0311c-173">You can use the query editor to experiment with multiple queries.</span></span> <span data-ttu-id="0311c-174">Per utilizzare più query:</span><span class="sxs-lookup"><span data-stu-id="0311c-174">To use multiple queries:</span></span>

- <span data-ttu-id="0311c-175">Separare ogni query con una riga vuota.</span><span class="sxs-lookup"><span data-stu-id="0311c-175">Separate each query with an empty line.</span></span>
- <span data-ttu-id="0311c-176">Posizionare il cursore su qualsiasi parte di una query per selezionarla prima di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="0311c-176">Place the cursor on any part of a query to select that query before running it.</span></span> <span data-ttu-id="0311c-177">Verrà eseguita solo la query selezionata.</span><span class="sxs-lookup"><span data-stu-id="0311c-177">This will run only the selected query.</span></span> <span data-ttu-id="0311c-178">Per eseguire un'altra query, spostare il cursore di conseguenza e selezionare **Esegui query**.</span><span class="sxs-lookup"><span data-stu-id="0311c-178">To run another query, move the cursor accordingly and select **Run query**.</span></span>

![Immagine dell'editor di query con più query](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a><span data-ttu-id="0311c-180">Usare query di esempio</span><span class="sxs-lookup"><span data-stu-id="0311c-180">Use sample queries</span></span>

<span data-ttu-id="0311c-181">La sezione **Introduzione** presenta alcune semplici query che impiegano operatori di uso comune.</span><span class="sxs-lookup"><span data-stu-id="0311c-181">The **Get started** section provides a few simple queries using commonly used operators.</span></span> <span data-ttu-id="0311c-182">Provare a eseguire queste query e apportare piccole modifiche.</span><span class="sxs-lookup"><span data-stu-id="0311c-182">Try running these queries and making small modifications to them.</span></span>

![Immagine della finestra di Ricerca avanzata](../../media/advanced-hunting-get-started.png)

>[!NOTE]
><span data-ttu-id="0311c-184">Oltre agli esempi di query di base, è anche possibile accedere [query condivise](advanced-hunting-shared-queries.md) per specifici scenari di ricerca delle minacce.</span><span class="sxs-lookup"><span data-stu-id="0311c-184">Apart from the basic query samples, you can also access [shared queries](advanced-hunting-shared-queries.md) for specific threat hunting scenarios.</span></span> <span data-ttu-id="0311c-185">Esplorare le query condivise sul lato sinistro della pagina o [nell'archivio di query GitHub.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="0311c-185">Explore the shared queries on the left side of the page or the [GitHub query repository](https://aka.ms/hunting-queries).</span></span>

## <a name="access-query-language-documentation"></a><span data-ttu-id="0311c-186">Documentazione sulle query</span><span class="sxs-lookup"><span data-stu-id="0311c-186">Access query language documentation</span></span>

<span data-ttu-id="0311c-187">Per altre informazioni sul linguaggio delle query di Esplora dati e sugli operatori supportati, vedere [Documentazione sul linguaggio delle query di Esplora dati](/azure/kusto/query/).</span><span class="sxs-lookup"><span data-stu-id="0311c-187">For more information on Kusto query language and supported operators, see [Kusto query language documentation](/azure/kusto/query/).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0311c-188">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0311c-188">Related topics</span></span>
- [<span data-ttu-id="0311c-189">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="0311c-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0311c-190">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="0311c-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="0311c-191">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="0311c-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0311c-192">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="0311c-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0311c-193">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="0311c-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0311c-194">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="0311c-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)