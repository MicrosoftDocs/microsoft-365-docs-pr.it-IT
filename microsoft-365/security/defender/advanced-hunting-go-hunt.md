---
title: Ottenere informazioni pertinenti su un'entità con go hunt
description: Informazioni su come usare lo strumento di ricerca avanzata per eseguire rapidamente query per informazioni pertinenti su un'entità o un evento tramite la ricerca avanzata.
keywords: ricerca avanzata, incidente, pivot, entità, andare a caccia, eventi rilevanti, ricerca delle minacce, ricerca di minacce informatiche, ricerca, query, telemetria, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 392db06aa517e3e970f85ccc971c3a6a6bc6e548
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498285"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="81576-104">Ricerca rapida di informazioni su entità o eventi con go hunt</span><span class="sxs-lookup"><span data-stu-id="81576-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="81576-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="81576-105">**Applies to:**</span></span>
- <span data-ttu-id="81576-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81576-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="81576-107">Con *l'azione di ricerca* vai, puoi analizzare rapidamente eventi e vari tipi di entità usando potenti funzionalità avanzate [di ricerca basate su](advanced-hunting-overview.md) query.</span><span class="sxs-lookup"><span data-stu-id="81576-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="81576-108">Questa azione esegue automaticamente una query di ricerca avanzata per trovare informazioni rilevanti sull'evento o sull'entità selezionata.</span><span class="sxs-lookup"><span data-stu-id="81576-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="81576-109">*L'azione di risposta* vai è disponibile in varie sezioni del Centro sicurezza ogni volta che vengono visualizzati i dettagli dell'evento o dell'entità.</span><span class="sxs-lookup"><span data-stu-id="81576-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="81576-110">Ad esempio, è possibile utilizzare *go hunt* dalle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="81576-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="81576-111">Nella pagina [dell'evento](investigate-incidents.md#incident-overview)imprevisto è possibile esaminare i dettagli relativi a utenti, dispositivi e molte altre entità associate a un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="81576-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="81576-112">Quando si seleziona un'entità, si ottengono informazioni aggiuntive e varie azioni che è possibile eseguire su tale entità.</span><span class="sxs-lookup"><span data-stu-id="81576-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="81576-113">Nell'esempio seguente viene selezionata una cassetta postale, che mostra i dettagli sulla cassetta postale e l'opzione per cercare ulteriori informazioni sulla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="81576-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Immagine che mostra i dettagli della cassetta postale con l'opzione di risposta go](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="81576-115">Nella pagina dell'evento imprevisto puoi anche accedere a un elenco di entità nella scheda evidenza. La selezione di una di queste entità offre un'opzione per cercare rapidamente informazioni su tale entità.</span><span class="sxs-lookup"><span data-stu-id="81576-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Immagine che mostra il file selezionato con l'opzione vai a risposta nella scheda Prova](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="81576-117">Quando visualizzi la sequenza temporale di un dispositivo, puoi selezionare un evento nella sequenza temporale per visualizzare informazioni aggiuntive su tale evento.</span><span class="sxs-lookup"><span data-stu-id="81576-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="81576-118">Dopo aver selezionato un evento, puoi scegliere di cercare altri eventi rilevanti nella ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="81576-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Immagine che mostra i dettagli dell'evento con l'opzione vai a risposta](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="81576-120">Se **si seleziona Vai a** risposta o Cerca per gli eventi correlati, vengono passate query diverse, a seconda che sia stata selezionata un'entità o un evento. </span><span class="sxs-lookup"><span data-stu-id="81576-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="81576-121">Query per informazioni sulle entità</span><span class="sxs-lookup"><span data-stu-id="81576-121">Query for entity information</span></span>
<span data-ttu-id="81576-122">Quando si *utilizza go hunt* per eseguire una query per ottenere informazioni su un utente, un dispositivo o qualsiasi altro tipo di entità, la query controlla tutte le tabelle dello schema pertinenti per eventuali eventi che coinvolgono tale entità.</span><span class="sxs-lookup"><span data-stu-id="81576-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="81576-123">Per mantenere gestibili i risultati, l'ambito della query è intorno allo stesso periodo di tempo della prima attività degli ultimi 30 giorni che coinvolge l'entità ed è associata all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="81576-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="81576-124">Ecco un esempio della query di risposta go per un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="81576-124">Here is an example of the go hunt query for a device:</span></span>

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a><span data-ttu-id="81576-125">Tipi di entità supportati</span><span class="sxs-lookup"><span data-stu-id="81576-125">Supported entity types</span></span>
<span data-ttu-id="81576-126">Puoi usare *vai a risposta* dopo aver selezionato uno di questi tipi di entità:</span><span class="sxs-lookup"><span data-stu-id="81576-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="81576-127">File</span><span class="sxs-lookup"><span data-stu-id="81576-127">Files</span></span>
- <span data-ttu-id="81576-128">Messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="81576-128">Emails</span></span>
- <span data-ttu-id="81576-129">Cluster di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="81576-129">Email clusters</span></span>
- <span data-ttu-id="81576-130">Cassette postali</span><span class="sxs-lookup"><span data-stu-id="81576-130">Mailboxes</span></span>
- <span data-ttu-id="81576-131">Utenti</span><span class="sxs-lookup"><span data-stu-id="81576-131">Users</span></span>
- <span data-ttu-id="81576-132">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="81576-132">Devices</span></span>
- <span data-ttu-id="81576-133">Indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="81576-133">IP addresses</span></span>
- <span data-ttu-id="81576-134">URL</span><span class="sxs-lookup"><span data-stu-id="81576-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="81576-135">Query per informazioni sull'evento</span><span class="sxs-lookup"><span data-stu-id="81576-135">Query for event information</span></span>
<span data-ttu-id="81576-136">Quando si *utilizza go hunt* per eseguire una query per ottenere informazioni su un evento della sequenza temporale, la query verifica la presenza di altri eventi in tutte le tabelle dello schema rilevanti al momento dell'evento selezionato.</span><span class="sxs-lookup"><span data-stu-id="81576-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="81576-137">Ad esempio, la query seguente elenca gli eventi in diverse tabelle dello schema che si sono verificati nello stesso periodo di tempo nello stesso dispositivo:</span><span class="sxs-lookup"><span data-stu-id="81576-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a><span data-ttu-id="81576-138">Modificare la query</span><span class="sxs-lookup"><span data-stu-id="81576-138">Adjust the query</span></span>
<span data-ttu-id="81576-139">Con una certa conoscenza del [linguaggio di query,](advanced-hunting-query-language.md)è possibile modificare la query in base alle proprie preferenze.</span><span class="sxs-lookup"><span data-stu-id="81576-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="81576-140">Ad esempio, puoi regolare questa linea, che determina le dimensioni dell'intervallo di tempo:</span><span class="sxs-lookup"><span data-stu-id="81576-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="81576-141">Oltre a modificare la query per ottenere risultati più rilevanti, è anche possibile:</span><span class="sxs-lookup"><span data-stu-id="81576-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="81576-142">Visualizzare i risultati come grafici</span><span class="sxs-lookup"><span data-stu-id="81576-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="81576-143">Creare una regola di rilevamento personalizzata</span><span class="sxs-lookup"><span data-stu-id="81576-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="81576-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="81576-144">Related topics</span></span>
- [<span data-ttu-id="81576-145">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="81576-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="81576-146">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="81576-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="81576-147">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="81576-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="81576-148">Regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="81576-148">Custom detection rules</span></span>](custom-detection-rules.md)
