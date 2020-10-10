---
title: Funzione AssignedIPAddresses () in Advanced Hunting for Microsoft Threat Protection
description: Informazioni su come utilizzare la funzione AssignedIPAddresses () per ottenere gli indirizzi IP più recenti assegnati a un dispositivo
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, fileprofile, profilo file, funzione, arricchimento
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
ms.openlocfilehash: 7f0b479051c46fe35ec9aea84b23ca0c4937fbfe
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412323"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="72472-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="72472-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="72472-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="72472-105">**Applies to:**</span></span>
- <span data-ttu-id="72472-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="72472-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="72472-107">Utilizzare la `AssignedIPAddresses()` funzione nelle query di [caccia avanzate](advanced-hunting-overview.md) per ottenere rapidamente gli indirizzi IP più recenti che sono stati assegnati a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="72472-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="72472-108">Se si specifica un argomento timestamp, questa funzione otterrà gli indirizzi IP più recenti al momento specificato.</span><span class="sxs-lookup"><span data-stu-id="72472-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="72472-109">Questa funzione restituisce una tabella con le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="72472-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="72472-110">Colonna</span><span class="sxs-lookup"><span data-stu-id="72472-110">Column</span></span> | <span data-ttu-id="72472-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="72472-111">Data type</span></span> | <span data-ttu-id="72472-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72472-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="72472-113">datetime</span><span class="sxs-lookup"><span data-stu-id="72472-113">datetime</span></span> | <span data-ttu-id="72472-114">Ora più recente in cui il dispositivo è stato osservato utilizzando l'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="72472-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="72472-115">stringa</span><span class="sxs-lookup"><span data-stu-id="72472-115">string</span></span> | <span data-ttu-id="72472-116">Indirizzo IP utilizzato dal dispositivo</span><span class="sxs-lookup"><span data-stu-id="72472-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="72472-117">stringa</span><span class="sxs-lookup"><span data-stu-id="72472-117">string</span></span> | <span data-ttu-id="72472-118">Indica se l'indirizzo IP è un indirizzo pubblico o privato</span><span class="sxs-lookup"><span data-stu-id="72472-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="72472-119">int</span><span class="sxs-lookup"><span data-stu-id="72472-119">int</span></span> | <span data-ttu-id="72472-120">Tipo di scheda di rete utilizzato dal dispositivo a cui è stato assegnato l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="72472-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="72472-121">Per i valori possibili, fare riferimento a [Questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="72472-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="72472-122">int</span><span class="sxs-lookup"><span data-stu-id="72472-122">int</span></span> | <span data-ttu-id="72472-123">Reti a cui è connessa la scheda con l'indirizzo IP assegnato.</span><span class="sxs-lookup"><span data-stu-id="72472-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="72472-124">Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o di dominio), una descrizione e un contrassegno che indica se è connesso pubblicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="72472-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="72472-125">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72472-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="72472-126">Argomenti</span><span class="sxs-lookup"><span data-stu-id="72472-126">Arguments</span></span>

- <span data-ttu-id="72472-127">**x**- `DeviceId` o `DeviceName` valore che identifica il dispositivo</span><span class="sxs-lookup"><span data-stu-id="72472-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="72472-128">**y**- `Timestamp` valore (DateTime) che indica alla funzione di ottenere gli indirizzi IP assegnati più recenti da un determinato intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="72472-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="72472-129">Se non specificato, la funzione restituirà gli indirizzi IP più recenti.</span><span class="sxs-lookup"><span data-stu-id="72472-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="72472-130">Esempi</span><span class="sxs-lookup"><span data-stu-id="72472-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="72472-131">Ottenere l'elenco di indirizzi IP utilizzati da un dispositivo 24 ore fa</span><span class="sxs-lookup"><span data-stu-id="72472-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="72472-132">Ottenere gli indirizzi IP utilizzati da un dispositivo e individuare i dispositivi che comunicano con esso</span><span class="sxs-lookup"><span data-stu-id="72472-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="72472-133">Questa query utilizza la `AssignedIPAddresses()` funzione per ottenere gli indirizzi IP assegnati per il dispositivo ( `example-device-name` ) in o prima di una data specifica ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="72472-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="72472-134">Vengono quindi utilizzati gli indirizzi IP per individuare le connessioni al dispositivo avviato da altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="72472-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a><span data-ttu-id="72472-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="72472-135">Related topics</span></span>
- [<span data-ttu-id="72472-136">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="72472-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="72472-137">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="72472-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="72472-138">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="72472-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
