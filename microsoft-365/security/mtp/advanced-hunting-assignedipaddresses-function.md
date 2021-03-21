---
title: Funzione AssignedIPAddresses() nella ricerca avanzata per Microsoft 365 Defender
description: Informazioni su come usare la funzione AssignedIPAddresses() per ottenere gli indirizzi IP più recenti assegnati a un dispositivo
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, FileProfile, profilo file, funzione, arricchimento
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
ms.openlocfilehash: c52f7b8bf5a93a75b3330a3377f3fab34b8e7837
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922921"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="4eda8-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="4eda8-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4eda8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4eda8-105">**Applies to:**</span></span>
- <span data-ttu-id="4eda8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eda8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4eda8-107">Usa la funzione nelle query di ricerca avanzate per ottenere rapidamente gli indirizzi IP più recenti assegnati `AssignedIPAddresses()` a un dispositivo. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4eda8-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="4eda8-108">Se si specifica un argomento timestamp, questa funzione ottiene gli indirizzi IP più recenti al momento specificato.</span><span class="sxs-lookup"><span data-stu-id="4eda8-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="4eda8-109">Questa funzione restituisce una tabella con le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="4eda8-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="4eda8-110">Colonna</span><span class="sxs-lookup"><span data-stu-id="4eda8-110">Column</span></span> | <span data-ttu-id="4eda8-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="4eda8-111">Data type</span></span> | <span data-ttu-id="4eda8-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4eda8-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="4eda8-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4eda8-113">datetime</span></span> | <span data-ttu-id="4eda8-114">Ora dell'ultima volta in cui il dispositivo è stato osservato usando l'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="4eda8-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="4eda8-115">stringa</span><span class="sxs-lookup"><span data-stu-id="4eda8-115">string</span></span> | <span data-ttu-id="4eda8-116">Indirizzo IP utilizzato dal dispositivo</span><span class="sxs-lookup"><span data-stu-id="4eda8-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="4eda8-117">stringa</span><span class="sxs-lookup"><span data-stu-id="4eda8-117">string</span></span> | <span data-ttu-id="4eda8-118">Indica se l'indirizzo IP è pubblico o privato</span><span class="sxs-lookup"><span data-stu-id="4eda8-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="4eda8-119">int</span><span class="sxs-lookup"><span data-stu-id="4eda8-119">int</span></span> | <span data-ttu-id="4eda8-120">Tipo di scheda di rete utilizzata dal dispositivo a cui è stato assegnato l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="4eda8-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="4eda8-121">Per i valori possibili, fare riferimento a [questa enumerazione](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="4eda8-121">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="4eda8-122">int</span><span class="sxs-lookup"><span data-stu-id="4eda8-122">int</span></span> | <span data-ttu-id="4eda8-123">Reti a cui è connessa la scheda con l'indirizzo IP assegnato.</span><span class="sxs-lookup"><span data-stu-id="4eda8-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="4eda8-124">Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o dominio), una descrizione e un flag che indica se è connesso pubblicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="4eda8-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="4eda8-125">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4eda8-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="4eda8-126">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4eda8-126">Arguments</span></span>

- <span data-ttu-id="4eda8-127">**x**— `DeviceId` o valore che identifica il `DeviceName` dispositivo</span><span class="sxs-lookup"><span data-stu-id="4eda8-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="4eda8-128">**y**— Valore (datetime) che indica alla funzione di ottenere gli indirizzi IP assegnati più di recente `Timestamp` da un'ora specifica.</span><span class="sxs-lookup"><span data-stu-id="4eda8-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="4eda8-129">Se non specificato, la funzione restituisce gli indirizzi IP più recenti.</span><span class="sxs-lookup"><span data-stu-id="4eda8-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="4eda8-130">Esempi</span><span class="sxs-lookup"><span data-stu-id="4eda8-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="4eda8-131">Ottenere l'elenco degli indirizzi IP usati da un dispositivo 24 ore fa</span><span class="sxs-lookup"><span data-stu-id="4eda8-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="4eda8-132">Ottenere gli indirizzi IP usati da un dispositivo e trovare i dispositivi che comunicano con esso</span><span class="sxs-lookup"><span data-stu-id="4eda8-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="4eda8-133">Questa query utilizza la funzione per ottenere gli indirizzi IP assegnati per il dispositivo ( ) in una data specifica o prima `AssignedIPAddresses()` `example-device-name` di ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="4eda8-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="4eda8-134">Usa quindi gli indirizzi IP per trovare le connessioni al dispositivo avviate da altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4eda8-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="4eda8-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4eda8-135">Related topics</span></span>
- [<span data-ttu-id="4eda8-136">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="4eda8-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4eda8-137">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="4eda8-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4eda8-138">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="4eda8-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)