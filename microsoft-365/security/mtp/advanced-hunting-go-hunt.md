---
title: Ottenere informazioni rilevanti su un'entità con Go Hunt
description: Informazioni su come utilizzare lo strumento "Vai a caccia" su per eseguire una query rapida per ottenere notizie rilevanti su un'entità o su un evento utilizzando la ricerca avanzata.
keywords: Advanced Hunting, Incident, pivot, Entity, Go Hunt, eventi rilevanti, Threat Hunting, Cyber Threat Hunting, Search, query, telemetria, Microsoft 365, Microsoft Threat Protection
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 4abbedc34b6d77e785c2096d9f334000f9ffb02f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430468"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a><span data-ttu-id="4f6d5-104">Cercare rapidamente informazioni su entità o eventi con Go Hunt</span><span class="sxs-lookup"><span data-stu-id="4f6d5-104">Quickly hunt for entity or event information with go hunt</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4f6d5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4f6d5-105">**Applies to:**</span></span>
- <span data-ttu-id="4f6d5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4f6d5-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4f6d5-107">Con l'azione *Go Hunt* , è possibile esaminare rapidamente gli eventi e i vari tipi di entità utilizzando potenti funzionalità di [caccia avanzate](advanced-hunting-overview.md) basate su query.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-107">With the *go hunt* action, you can quickly investigate events and various entity types using powerful query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span> <span data-ttu-id="4f6d5-108">Questa azione esegue automaticamente una query di ricerca avanzata per trovare informazioni rilevanti sull'evento o l'entità selezionata.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-108">This action automatically runs an advanced hunting query to find relevant information about the selected event or entity.</span></span>

<span data-ttu-id="4f6d5-109">L'azione *Go Hunt* è disponibile in diverse sezioni del Centro sicurezza ogni volta che vengono visualizzati i dettagli dell'evento o dell'entità.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-109">The *go hunt* action is available in various sections of the security center whenever event or entity details are displayed.</span></span> <span data-ttu-id="4f6d5-110">Ad esempio, è possibile utilizzare *Go Hunt* dalle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f6d5-110">For example, you can use *go hunt* from the following sections:</span></span>

- <span data-ttu-id="4f6d5-111">Nella [pagina Incident](investigate-incidents.md#incident-overview)è possibile esaminare i dettagli relativi a utenti, dispositivi e molte altre entità associate a un evento Incident.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-111">In the [incident page](investigate-incidents.md#incident-overview), you can review details about users, devices, and many other entities associated with an incident.</span></span> <span data-ttu-id="4f6d5-112">Quando si seleziona un'entità, vengono fornite informazioni aggiuntive e diverse azioni che è possibile intraprendere su tale entitity.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-112">As you select an entity, you get additional information as well as various actions you could take on that entitity.</span></span> <span data-ttu-id="4f6d5-113">Nell'esempio seguente viene selezionata una cassetta postale, in cui vengono visualizzati i dettagli relativi alla cassetta postale e l'opzione di ricerca per ulteriori informazioni sulla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-113">In the example below, a mailbox is selected, showing details about the mailbox as well the option to hunt for more information about the mailbox.</span></span>

    ![Immagine che mostra i dettagli delle cassette postali con l'opzione Go Hunt](../../media/mtp-ah/go-hunt-email.png)

- <span data-ttu-id="4f6d5-115">Nella pagina Incident è inoltre possibile accedere a un elenco di entità nella scheda Evidence. Se si seleziona una di queste entità, viene fornita un'opzione per cercare rapidamente informazioni su tale entità.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-115">In the incident page, you can also access a list of entities under the evidence tab. Selecting one of those entities provides an option to quickly hunt for information about that entity.</span></span>

    ![Immagine che mostra il file selezionato con l'opzione Go Hunt nella scheda Evidence](../../media/mtp-ah/go-hunt-evidence-file.png)


- <span data-ttu-id="4f6d5-117">Quando si visualizza la sequenza temporale per un dispositivo, è possibile selezionare un evento nella sequenza temporale per visualizzare ulteriori informazioni su quell'evento.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-117">When viewing the timeline for a device, you can select an event in the timeline to view additional information about that event.</span></span> <span data-ttu-id="4f6d5-118">Dopo aver selezionato un evento, si ottiene la possibilità di cercare altri eventi rilevanti nella ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-118">Once an event is selected, you get the option to hunt for other relevant events in advanced hunting.</span></span>

    ![Immagine che mostra i dettagli degli eventi con l'opzione Go Hunt](../../media/mtp-ah/go-hunt-event.png)

<span data-ttu-id="4f6d5-120">Se si seleziona Vai o Cerca **per eventi correlati** , **vengono** passate diverse query, a seconda che sia stata selezionata un'entità o un evento.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-120">Selecting **Go hunt** or **Hunt for related events** passes different queries, depending on whether you've selected an entity or an event.</span></span>

## <a name="query-for-entity-information"></a><span data-ttu-id="4f6d5-121">Query per informazioni sulle entità</span><span class="sxs-lookup"><span data-stu-id="4f6d5-121">Query for entity information</span></span>
<span data-ttu-id="4f6d5-122">Quando si utilizza *Go Hunt* per eseguire una query per informazioni su un utente, un dispositivo o qualsiasi altro tipo di entità, la query verifica tutte le tabelle dello schema rilevanti per tutti gli eventi che interessano tale entità.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-122">When using *go hunt* to query for information about a user, device, or any other type of entity, the query checks all relevant schema tables for any events involving that entity.</span></span> <span data-ttu-id="4f6d5-123">Per garantire la gestione dei risultati, la query ha un ambito pari a circa lo stesso periodo di tempo della prima attività negli ultimi 30 giorni che coinvolge l'entità ed è associata all'evento Incident.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-123">To keep the results manageable, the query is scoped to around the same time period as the earliest activity in the past 30 days that involves the entity and is associated with the incident.</span></span>

<span data-ttu-id="4f6d5-124">Di seguito è riportato un esempio della query Go Hunt per un dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4f6d5-124">Here is an example of the go hunt query for a device:</span></span>

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
### <a name="supported-entity-types"></a><span data-ttu-id="4f6d5-125">Tipi di entità supportate</span><span class="sxs-lookup"><span data-stu-id="4f6d5-125">Supported entity types</span></span>
<span data-ttu-id="4f6d5-126">È possibile utilizzare *Go Hunt* dopo aver selezionato uno qualsiasi di questi tipi di entità:</span><span class="sxs-lookup"><span data-stu-id="4f6d5-126">You can use *go hunt* after selecting any of these entity types:</span></span>

- <span data-ttu-id="4f6d5-127">File</span><span class="sxs-lookup"><span data-stu-id="4f6d5-127">Files</span></span>
- <span data-ttu-id="4f6d5-128">Messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="4f6d5-128">Emails</span></span>
- <span data-ttu-id="4f6d5-129">Cluster di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="4f6d5-129">Email clusters</span></span>
- <span data-ttu-id="4f6d5-130">Cassette postali</span><span class="sxs-lookup"><span data-stu-id="4f6d5-130">Mailboxes</span></span>
- <span data-ttu-id="4f6d5-131">Utenti</span><span class="sxs-lookup"><span data-stu-id="4f6d5-131">Users</span></span>
- <span data-ttu-id="4f6d5-132">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="4f6d5-132">Devices</span></span>
- <span data-ttu-id="4f6d5-133">Indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="4f6d5-133">IP addresses</span></span>
- <span data-ttu-id="4f6d5-134">URL</span><span class="sxs-lookup"><span data-stu-id="4f6d5-134">URLs</span></span>

## <a name="query-for-event-information"></a><span data-ttu-id="4f6d5-135">Query per informazioni sugli eventi</span><span class="sxs-lookup"><span data-stu-id="4f6d5-135">Query for event information</span></span>
<span data-ttu-id="4f6d5-136">Quando si utilizza *Go Hunt* per eseguire una query per informazioni su un evento Timeline, la query verifica tutte le tabelle dello schema rilevanti per gli altri eventi che interessano il periodo dell'evento selezionato.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-136">When using *go hunt* to query for information about a timeline event, the query checks all relevant schema tables for other events around the time of the selected event.</span></span> <span data-ttu-id="4f6d5-137">Ad esempio, la query seguente elenca gli eventi in diverse tabelle dello schema che si sono verificati nello stesso periodo di tempo nello stesso dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4f6d5-137">For example, the following query lists events in various schema tables that occured around the same time period on the same device:</span></span>

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

## <a name="adjust-the-query"></a><span data-ttu-id="4f6d5-138">Modificare la query</span><span class="sxs-lookup"><span data-stu-id="4f6d5-138">Adjust the query</span></span>
<span data-ttu-id="4f6d5-139">Con una certa conoscenza del [linguaggio di query](advanced-hunting-query-language.md), è possibile modificare la query in base alle proprie preferenze.</span><span class="sxs-lookup"><span data-stu-id="4f6d5-139">With some knowledge of the [query language](advanced-hunting-query-language.md), you can adjust the query to your preference.</span></span> <span data-ttu-id="4f6d5-140">Ad esempio, è possibile modificare questa linea, che determina le dimensioni della finestra temporale:</span><span class="sxs-lookup"><span data-stu-id="4f6d5-140">For example, you can adjust this line, which determines the size of the time window:</span></span>

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

<span data-ttu-id="4f6d5-141">Oltre a modificare la query per ottenere risultati più rilevanti, è anche possibile:</span><span class="sxs-lookup"><span data-stu-id="4f6d5-141">In addition to modifying the query to get more relevant results, you can also:</span></span>
- [<span data-ttu-id="4f6d5-142">Visualizzare i risultati come grafici</span><span class="sxs-lookup"><span data-stu-id="4f6d5-142">View the results as charts</span></span>](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [<span data-ttu-id="4f6d5-143">Creare una regola di rilevamento personalizzata</span><span class="sxs-lookup"><span data-stu-id="4f6d5-143">Create a custom detection rule</span></span>](custom-detection-rules.md)

## <a name="related-topics"></a><span data-ttu-id="4f6d5-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4f6d5-144">Related topics</span></span>
- [<span data-ttu-id="4f6d5-145">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="4f6d5-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4f6d5-146">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="4f6d5-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4f6d5-147">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="4f6d5-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="4f6d5-148">Regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="4f6d5-148">Custom detection rules</span></span>](custom-detection-rules.md)
