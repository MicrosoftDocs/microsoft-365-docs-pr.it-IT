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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794232"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="d6872-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="d6872-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="d6872-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d6872-105">**Applies to:**</span></span>
- <span data-ttu-id="d6872-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d6872-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d6872-107">Utilizzare la `AssignedIPAddresses()` funzione per ottenere rapidamente gli indirizzi IP più recenti che sono stati assegnati a un dispositivo o gli indirizzi IP più recenti da un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="d6872-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span> <span data-ttu-id="d6872-108">Questa funzione restituisce una tabella con le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6872-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="d6872-109">Colonna</span><span class="sxs-lookup"><span data-stu-id="d6872-109">Column</span></span> | <span data-ttu-id="d6872-110">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="d6872-110">Data type</span></span> | <span data-ttu-id="d6872-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6872-111">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="d6872-112">Timestamp</span><span class="sxs-lookup"><span data-stu-id="d6872-112">Timestamp</span></span> | <span data-ttu-id="d6872-113">datetime</span><span class="sxs-lookup"><span data-stu-id="d6872-113">datetime</span></span> | <span data-ttu-id="d6872-114">Ora più recente in cui il dispositivo è stato osservato utilizzando l'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="d6872-114">Latest time when the device was observed using the IP address</span></span> |
| <span data-ttu-id="d6872-115">IPAddress</span><span class="sxs-lookup"><span data-stu-id="d6872-115">IPAddress</span></span> | <span data-ttu-id="d6872-116">stringa</span><span class="sxs-lookup"><span data-stu-id="d6872-116">string</span></span> | <span data-ttu-id="d6872-117">Indirizzo IP utilizzato dal dispositivo</span><span class="sxs-lookup"><span data-stu-id="d6872-117">IP address used by the device</span></span> |
| <span data-ttu-id="d6872-118">IPType</span><span class="sxs-lookup"><span data-stu-id="d6872-118">IPType</span></span> | <span data-ttu-id="d6872-119">stringa</span><span class="sxs-lookup"><span data-stu-id="d6872-119">string</span></span> | <span data-ttu-id="d6872-120">Indica se l'indirizzo IP è un indirizzo pubblico o privato</span><span class="sxs-lookup"><span data-stu-id="d6872-120">Indicates whether the IP address is a public or private address</span></span> |
| <span data-ttu-id="d6872-121">NetworkAdapterType</span><span class="sxs-lookup"><span data-stu-id="d6872-121">NetworkAdapterType</span></span> | <span data-ttu-id="d6872-122">int</span><span class="sxs-lookup"><span data-stu-id="d6872-122">int</span></span> | <span data-ttu-id="d6872-123">Tipo di scheda di rete utilizzato dal dispositivo a cui è stato assegnato l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="d6872-123">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="d6872-124">Per i valori possibili, fare riferimento a [Questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="d6872-124">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span>  |
| <span data-ttu-id="d6872-125">ConnectedNetworks</span><span class="sxs-lookup"><span data-stu-id="d6872-125">ConnectedNetworks</span></span> | <span data-ttu-id="d6872-126">int</span><span class="sxs-lookup"><span data-stu-id="d6872-126">int</span></span> | <span data-ttu-id="d6872-127">Reti a cui è connessa la scheda con l'indirizzo IP assegnato.</span><span class="sxs-lookup"><span data-stu-id="d6872-127">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="d6872-128">Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o di dominio), una descrizione e un contrassegno che indica se è connesso pubblicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="d6872-128">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |


## <a name="syntax"></a><span data-ttu-id="d6872-129">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6872-129">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="d6872-130">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d6872-130">Arguments</span></span>

- <span data-ttu-id="d6872-131">**x** - `DeviceId` o `DeviceName` valore che identifica il dispositivo</span><span class="sxs-lookup"><span data-stu-id="d6872-131">**x** — `DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="d6872-132">**y** - `Timestamp` (DateTime) valore che indica il momento specifico in cui ottenere gli indirizzi IP più recenti.</span><span class="sxs-lookup"><span data-stu-id="d6872-132">**y** — `Timestamp` (datetime) value indicating the specific point in time where to get the most recent IP addresses.</span></span> <span data-ttu-id="d6872-133">Se non specificato, la funzione restituirà gli indirizzi IP più recenti.</span><span class="sxs-lookup"><span data-stu-id="d6872-133">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="d6872-134">Esempi</span><span class="sxs-lookup"><span data-stu-id="d6872-134">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a><span data-ttu-id="d6872-135">Ottenere l'elenco di indirizzi IP utilizzati da un dispositivo fino a 24 ore fa</span><span class="sxs-lookup"><span data-stu-id="d6872-135">Get the list of IP addresses used by a device as of 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="d6872-136">Ottenere gli indirizzi IP utilizzati da un dispositivo e individuare i dispositivi che comunicano con esso</span><span class="sxs-lookup"><span data-stu-id="d6872-136">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="d6872-137">Questa query utilizza la `AssignedIPAddresses()` funzione per ottenere gli indirizzi IP assegnati per il dispositivo ( `example-device-name` ) in o prima di una data specifica ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="d6872-137">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="d6872-138">Vengono quindi utilizzati gli indirizzi IP per individuare le connessioni al dispositivo avviato da altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d6872-138">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="d6872-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d6872-139">Related topics</span></span>
- [<span data-ttu-id="d6872-140">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="d6872-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d6872-141">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="d6872-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d6872-142">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="d6872-142">Understand the schema</span></span>](advanced-hunting-schema-tables.md)