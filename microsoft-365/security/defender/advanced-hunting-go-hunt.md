---
title: Ottenere informazioni pertinenti su un'entità con go hunt
description: Informazioni su come usare lo strumento di ricerca avanzata per eseguire rapidamente query per informazioni pertinenti su un'entità o un evento tramite la ricerca avanzata.
keywords: ricerca avanzata, incidente, pivot, entità, andare a caccia, eventi rilevanti, ricerca delle minacce, ricerca di minacce informatiche, ricerca, query, telemetria, Microsoft 365, Microsoft 365 Defender
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
ms.openlocfilehash: a78f37d8c1fed1063095e25f19136f0362f17db7
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952657"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="6192e-104">Ricerca rapida di informazioni su entità o eventi con go hunt</span><span class="sxs-lookup"><span data-stu-id="6192e-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6192e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6192e-105">**Applies to:**</span></span>
- <span data-ttu-id="6192e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6192e-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="6192e-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6192e-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="6192e-108">Con *l'azione di ricerca* vai, puoi analizzare rapidamente eventi e vari tipi di entità usando potenti funzionalità avanzate [di ricerca basate su](advanced-hunting-overview.md) query.</span><span class="sxs-lookup"><span data-stu-id="6192e-108">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="6192e-109">Questa azione esegue automaticamente una query di ricerca avanzata per trovare informazioni rilevanti sull'evento o sull'entità selezionata.</span><span class="sxs-lookup"><span data-stu-id="6192e-109">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="6192e-110">*L'azione di risposta* vai è disponibile in varie sezioni del Centro sicurezza ogni volta che vengono visualizzati i dettagli dell'evento o dell'entità.</span><span class="sxs-lookup"><span data-stu-id="6192e-110">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="6192e-111">Ad esempio, è possibile utilizzare *go hunt* dalle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6192e-111">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="6192e-112">Nella pagina [dell'evento](investigate-incidents.md#summary)imprevisto è possibile esaminare i dettagli relativi a utenti, dispositivi e molte altre entità associate a un evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="6192e-112">In the [incident page](investigate-incidents.md#summary), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="6192e-113">Quando si seleziona un'entità, si ottengono informazioni aggiuntive e varie azioni che è possibile eseguire su tale entità.</span><span class="sxs-lookup"><span data-stu-id="6192e-113">As you select an entity, you get additional information as well as various actions you could take on that entity.</span></span> <span data-ttu-id="6192e-114">Nell'esempio seguente viene selezionata una cassetta postale, che mostra i dettagli sulla cassetta postale e l'opzione per cercare ulteriori informazioni sulla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="6192e-114">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Immagine che mostra i dettagli della cassetta postale con l'opzione di risposta go](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="6192e-116">Nella pagina dell'evento imprevisto puoi anche accedere a un elenco di entità nella scheda evidenza. La selezione di una di queste entità offre un'opzione per cercare rapidamente informazioni su tale entità.</span><span class="sxs-lookup"><span data-stu-id="6192e-116">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Immagine che mostra il file selezionato con l'opzione vai a risposta nella scheda Prova](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="6192e-118">Quando visualizzi la sequenza temporale di un dispositivo, puoi selezionare un evento nella sequenza temporale per visualizzare informazioni aggiuntive su tale evento.</span><span class="sxs-lookup"><span data-stu-id="6192e-118">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="6192e-119">Dopo aver selezionato un evento, puoi scegliere di cercare altri eventi rilevanti nella ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="6192e-119">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Immagine che mostra i dettagli dell'evento con l'opzione vai a risposta](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="6192e-121">Se **si seleziona Vai a** risposta o Cerca per gli eventi correlati, vengono passate query diverse, a seconda che sia stata selezionata un'entità o un evento. </span><span class="sxs-lookup"><span data-stu-id="6192e-121">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="6192e-122">Query per informazioni sulle entità</span><span class="sxs-lookup"><span data-stu-id="6192e-122">Query for entity information</span></span>
<span data-ttu-id="6192e-123">Quando si *utilizza go hunt* per eseguire una query per ottenere informazioni su un utente, un dispositivo o qualsiasi altro tipo di entità, la query controlla tutte le tabelle dello schema pertinenti per eventuali eventi che coinvolgono tale entità.</span><span class="sxs-lookup"><span data-stu-id="6192e-123">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="6192e-124">Per mantenere gestibili i risultati, l'ambito della query è intorno allo stesso periodo di tempo della prima attività degli ultimi 30 giorni che coinvolge l'entità ed è associata all'evento imprevisto.</span><span class="sxs-lookup"><span data-stu-id="6192e-124">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="6192e-125">Ecco un esempio della query di risposta go per un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6192e-125">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="6192e-126">Tipi di entità supportati</span><span class="sxs-lookup"><span data-stu-id="6192e-126">Supported entity types</span></span>
<span data-ttu-id="6192e-127">Puoi usare *vai a risposta* dopo aver selezionato uno di questi tipi di entità:</span><span class="sxs-lookup"><span data-stu-id="6192e-127">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="6192e-128">File</span><span class="sxs-lookup"><span data-stu-id="6192e-128">Files</span></span>
- <span data-ttu-id="6192e-129">Messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6192e-129">Emails</span></span>
- <span data-ttu-id="6192e-130">Cluster di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6192e-130">Email clusters</span></span>
- <span data-ttu-id="6192e-131">Cassette postali</span><span class="sxs-lookup"><span data-stu-id="6192e-131">Mailboxes</span></span>
- <span data-ttu-id="6192e-132">Utenti</span><span class="sxs-lookup"><span data-stu-id="6192e-132">Users</span></span>
- <span data-ttu-id="6192e-133">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="6192e-133">Devices</span></span>
- <span data-ttu-id="6192e-134">Indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="6192e-134">IP addresses</span></span>
- <span data-ttu-id="6192e-135">URL</span><span class="sxs-lookup"><span data-stu-id="6192e-135">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="6192e-136">Query per informazioni sull'evento</span><span class="sxs-lookup"><span data-stu-id="6192e-136">Query for event information</span></span>
<span data-ttu-id="6192e-137">Quando si *utilizza go hunt* per eseguire una query per ottenere informazioni su un evento della sequenza temporale, la query verifica la presenza di altri eventi in tutte le tabelle dello schema rilevanti al momento dell'evento selezionato.</span><span class="sxs-lookup"><span data-stu-id="6192e-137">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="6192e-138">Ad esempio, la query seguente elenca gli eventi in diverse tabelle dello schema che si sono verificati nello stesso periodo di tempo nello stesso dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6192e-138">For example, the following query lists events in various schema tables that occurred around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="6192e-139">Modificare la query</span><span class="sxs-lookup"><span data-stu-id="6192e-139">Adjust the query</span></span>
<span data-ttu-id="6192e-140">Con una certa conoscenza del [linguaggio di query,](advanced-hunting-query-language.md)è possibile modificare la query in base alle proprie preferenze.</span><span class="sxs-lookup"><span data-stu-id="6192e-140">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="6192e-141">Ad esempio, puoi regolare questa linea, che determina le dimensioni dell'intervallo di tempo:</span><span class="sxs-lookup"><span data-stu-id="6192e-141">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="6192e-142">Oltre a modificare la query per ottenere risultati più rilevanti, è anche possibile:</span><span class="sxs-lookup"><span data-stu-id="6192e-142">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="6192e-143">Visualizzare i risultati come grafici</span><span class="sxs-lookup"><span data-stu-id="6192e-143">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="6192e-144">Creare una regola di rilevamento personalizzata</span><span class="sxs-lookup"><span data-stu-id="6192e-144">Create a custom detection rule</span></span>](custom-detection-rules.md)

>[!NOTE]
><span data-ttu-id="6192e-145">Alcune tabelle di questo articolo potrebbero non essere disponibili in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6192e-145">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6192e-146">[Attivare Microsoft 365 Defender per](m365d-enable.md) cercare minacce che usano più origini dati.</span><span class="sxs-lookup"><span data-stu-id="6192e-146">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="6192e-147">Puoi spostare i flussi di lavoro di ricerca avanzata da Microsoft Defender per Endpoint a Microsoft 365 Defender seguendo la procedura descritta in Eseguire la migrazione di query di ricerca avanzate da [Microsoft Defender per Endpoint.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="6192e-147">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6192e-148">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6192e-148">Related topics</span></span>
- [<span data-ttu-id="6192e-149">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="6192e-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6192e-150">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="6192e-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6192e-151">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="6192e-151">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="6192e-152">Regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="6192e-152">Custom detection rules</span></span>](custom-detection-rules.md)
