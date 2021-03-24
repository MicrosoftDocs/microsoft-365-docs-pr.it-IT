---
title: Procedure consigliate per le query per la ricerca avanzata
description: Come creare query di ricerca delle minacce veloci, efficienti e senza errori quando in Ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, rilevamenti personalizzati, schema, kusto, evitare timeout, righe di comando, ID processo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6259ac1c5804b244c825a1bb54401640fdefaf34
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064394"
---
# <a name="advanced-hunting-query-best-practices"></a><span data-ttu-id="a99c0-104">Procedure consigliate per query in Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="a99c0-104">Advanced hunting query best practices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a99c0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a99c0-105">**Applies to:**</span></span>
- [<span data-ttu-id="a99c0-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a99c0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="a99c0-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a99c0-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a99c0-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a99c0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a><span data-ttu-id="a99c0-109">Ottimizzare le prestazioni delle query</span><span class="sxs-lookup"><span data-stu-id="a99c0-109">Optimize query performance</span></span>

<span data-ttu-id="a99c0-110">Applicare questi suggerimenti per ottenere risultati più veloci ed evitare timeout durante l'esecuzione di query complesse.</span><span class="sxs-lookup"><span data-stu-id="a99c0-110">Apply these recommendations to get results faster and avoid timeouts while running complex queries.</span></span>

- <span data-ttu-id="a99c0-111">Quando si provano nuove query, usare sempre `limit` per evitare set di risultati molto grandi.</span><span class="sxs-lookup"><span data-stu-id="a99c0-111">When trying new queries, always use `limit` to avoid extremely large result sets.</span></span> <span data-ttu-id="a99c0-112">È anche possibile determinare all'inizio le dimensioni del set di risultati usando `count`.</span><span class="sxs-lookup"><span data-stu-id="a99c0-112">You can also initially assess the size of the result set using `count`.</span></span>
- <span data-ttu-id="a99c0-113">Usare prima i filtri del periodo.</span><span class="sxs-lookup"><span data-stu-id="a99c0-113">Use time filters first.</span></span> <span data-ttu-id="a99c0-114">Idealmente, limitare le query a sette giorni.</span><span class="sxs-lookup"><span data-stu-id="a99c0-114">Ideally, limit your queries to seven days.</span></span>
- <span data-ttu-id="a99c0-115">Inserire i filtri che si prevede rimuovano la maggior parte dei dati all'inizio della query, subito dopo il filtro del periodo.</span><span class="sxs-lookup"><span data-stu-id="a99c0-115">Put filters that are expected to remove most of the data in the beginning of the query, right after the time filter.</span></span>
- <span data-ttu-id="a99c0-116">Usare l'operatore `has` su `contains` quando si cercano token completi.</span><span class="sxs-lookup"><span data-stu-id="a99c0-116">Use the `has` operator over `contains` when looking for full tokens.</span></span>
- <span data-ttu-id="a99c0-117">Individuare una colonna specifica invece di eseguire le ricerche in tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="a99c0-117">Look in a specific column rather than running full text searches across all columns.</span></span>
- <span data-ttu-id="a99c0-118">Quando si uniscono le tabelle, specificare prima la tabella con meno righe.</span><span class="sxs-lookup"><span data-stu-id="a99c0-118">When joining tables, specify the table with fewer rows first.</span></span>
- <span data-ttu-id="a99c0-119">`project` solo le colonne necessarie dalle tabelle che sono state unite.</span><span class="sxs-lookup"><span data-stu-id="a99c0-119">`project` only the necessary columns from tables you've joined.</span></span>

>[!TIP]
><span data-ttu-id="a99c0-120">Per altre informazioni su come migliorare le prestazioni della query, vedere [procedure consigliate per le query di Esplora dati](https://docs.microsoft.com/azure/kusto/query/best-practices).</span><span class="sxs-lookup"><span data-stu-id="a99c0-120">For more guidance on improving query performance, read [Kusto query best practices](https://docs.microsoft.com/azure/kusto/query/best-practices).</span></span>

## <a name="query-tips-and-pitfalls"></a><span data-ttu-id="a99c0-121">Suggerimenti e insidie per le query</span><span class="sxs-lookup"><span data-stu-id="a99c0-121">Query tips and pitfalls</span></span>

### <a name="queries-with-process-ids"></a><span data-ttu-id="a99c0-122">Query con ID processo</span><span class="sxs-lookup"><span data-stu-id="a99c0-122">Queries with process IDs</span></span>

<span data-ttu-id="a99c0-123">Gli ID processo (PID) sono riciclati in Windows e riutilizzati per i nuovi processi.</span><span class="sxs-lookup"><span data-stu-id="a99c0-123">Process IDs (PIDs) are recycled in Windows and reused for new processes.</span></span> <span data-ttu-id="a99c0-124">Di per sé, non possono servire come identificatori univoci per processi specifici.</span><span class="sxs-lookup"><span data-stu-id="a99c0-124">On their own, they can't serve as unique identifiers for specific processes.</span></span> <span data-ttu-id="a99c0-125">Per ottenere un identificatore univoco per un processo in un dispositivo specifico, usa l'ID processo insieme al tempo di creazione del processo.</span><span class="sxs-lookup"><span data-stu-id="a99c0-125">To get a unique identifier for a process on a specific device, use the process ID together with the process creation time.</span></span> <span data-ttu-id="a99c0-126">Quando si uniscono o riepilogano i dati relativi ai processi, includere colonne per l'identificatore del dispositivo (o ), l'ID processo ( o ) e il tempo di creazione `DeviceId` del processo ( o `DeviceName` `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` ).</span><span class="sxs-lookup"><span data-stu-id="a99c0-126">When you join or summarize data around processes, include columns for the device identifier (either `DeviceId` or `DeviceName`), the process ID (`ProcessId` or `InitiatingProcessId`), and the process creation time (`ProcessCreationTime` or `InitiatingProcessCreationTime`).</span></span>

<span data-ttu-id="a99c0-127">La seguente query di esempio trova i processi che accedono a più di 10 indirizzi IP dalla porta 445 (SMB), possibilmente analizzando le condivisioni file.</span><span class="sxs-lookup"><span data-stu-id="a99c0-127">The following example query finds processes that access more than 10 IP addresses over port 445 (SMB), possibly scanning for file shares.</span></span>

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

<span data-ttu-id="a99c0-128">La query riepiloga sia `InitiatingProcessId` che `InitiatingProcessCreationTime` in modo da visualizzare un singolo processo, senza combinare più processi con lo stesso ID processo.</span><span class="sxs-lookup"><span data-stu-id="a99c0-128">The query summarizes by both `InitiatingProcessId` and `InitiatingProcessCreationTime` so that it looks at a single process, without mixing multiple processes with the same process ID.</span></span>

### <a name="queries-with-command-lines"></a><span data-ttu-id="a99c0-129">Query con righe di comando</span><span class="sxs-lookup"><span data-stu-id="a99c0-129">Queries with command lines</span></span>

<span data-ttu-id="a99c0-130">Le righe di comando possono variare.</span><span class="sxs-lookup"><span data-stu-id="a99c0-130">Command lines can vary.</span></span> <span data-ttu-id="a99c0-131">Se applicabile, filtrare i nomi dei file ed eseguire una corrispondenza fuzzy.</span><span class="sxs-lookup"><span data-stu-id="a99c0-131">When applicable, filter on file names and do fuzzy matching.</span></span>

<span data-ttu-id="a99c0-132">Esistono diversi modi per creare una riga di comando per eseguire un'attività.</span><span class="sxs-lookup"><span data-stu-id="a99c0-132">There are numerous ways to construct a command line to accomplish a task.</span></span> <span data-ttu-id="a99c0-133">Ad esempio, un utente malintenzionato può fare riferimento a un file di immagine con o senza un percorso, senza un'estensione di file, con variabili di ambiente o con virgolette.</span><span class="sxs-lookup"><span data-stu-id="a99c0-133">For example, an attacker could reference an image file with or without a path, without a file extension, using environment variables, or with quotes.</span></span> <span data-ttu-id="a99c0-134">Inoltre, l'utente malintenzionato può anche cambiare l'ordine dei parametri o aggiungere più citazioni e spazi.</span><span class="sxs-lookup"><span data-stu-id="a99c0-134">In addition, the attacker could also change the order of parameters or add multiple quotes and spaces.</span></span>

<span data-ttu-id="a99c0-135">Per creare query più durevoli usando le righe di comando, applicare le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="a99c0-135">To create more durable queries using command lines, apply the following practices:</span></span>

- <span data-ttu-id="a99c0-136">Identificare i processi noti (ad esempio *NET. exe* o *psexec. exe*) confrontando i campi filename (nome file), anziché filtrare nel campo della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a99c0-136">Identify the known processes (such as *net.exe* or *psexec.exe*) by matching on the filename fields, instead of filtering on the command-line field.</span></span>
- <span data-ttu-id="a99c0-137">Quando si eseguono query per gli argomenti della riga di comando, non cercare una corrispondenza esatta su più argomenti non correlati in un determinato ordine.</span><span class="sxs-lookup"><span data-stu-id="a99c0-137">When querying for command-line arguments, don't look for an exact match on multiple unrelated arguments in a certain order.</span></span> <span data-ttu-id="a99c0-138">Usare invece espressioni regolari o utilizzare più operatori distinti.</span><span class="sxs-lookup"><span data-stu-id="a99c0-138">Instead, use regular expressions or use multiple separate contains operators.</span></span>
- <span data-ttu-id="a99c0-139">Usare corrispondenza maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="a99c0-139">Use case insensitive matches.</span></span> <span data-ttu-id="a99c0-140">Ad esempio, utilizzare `=~` , , e invece di , `in~` `contains` `==` `in` e `contains_cs`</span><span class="sxs-lookup"><span data-stu-id="a99c0-140">For example, use `=~`, `in~`, and `contains` instead of `==`, `in` and `contains_cs`</span></span>
- <span data-ttu-id="a99c0-141">Per migrare tecniche di offuscamento di linee di domando DOS, provare a rimuovere virgolette, sostituire virgole con spazi e sostituire doppi spazi con uno spazio singolo.</span><span class="sxs-lookup"><span data-stu-id="a99c0-141">To mitigate DOS command-line obfuscation techniques, consider removing quotes, replacing commas with spaces, and replacing multiple consecutive spaces with a single space.</span></span> <span data-ttu-id="a99c0-142">Tenere presente che esistono tecniche di offuscamento DOS ancora più complesse che richiedono altri approcci, tuttavia queste possono aiutare a gestire i casi più comuni.</span><span class="sxs-lookup"><span data-stu-id="a99c0-142">Note that there are more complex DOS obfuscation techniques that require other approaches, but these can help address the most common ones.</span></span>

<span data-ttu-id="a99c0-143">I seguenti esempi mostrano diversi modi di creare una query per cercare il file *net.exe* che blocca il servizio Windows Defender Firewall:</span><span class="sxs-lookup"><span data-stu-id="a99c0-143">The following examples show various ways to construct a query that looks for the file *net.exe* to stop the Windows Defender Firewall service:</span></span>

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

> <span data-ttu-id="a99c0-144">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a99c0-144">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a99c0-145">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a99c0-145">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="a99c0-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a99c0-146">Related topics</span></span>

- [<span data-ttu-id="a99c0-147">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="a99c0-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a99c0-148">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="a99c0-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a99c0-149">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="a99c0-149">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="a99c0-150">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="a99c0-150">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="a99c0-151">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="a99c0-151">Custom detections overview</span></span>](overview-custom-detections.md)
