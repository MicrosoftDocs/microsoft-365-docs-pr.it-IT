---
title: Funzione AssignedIPAddresses() nella ricerca avanzata di Microsoft Defender per Endpoint
description: Informazioni su come usare la funzione AssignedIPAddresses() per ottenere gli indirizzi IP più recenti assegnati a un dispositivo
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection, ricerca, query, telemetria, riferimento allo schema, kusto, FileProfile, profilo file, funzione, arricchimento
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
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 08ab7ff5bac917a027e4380a46ab1cb2cf0a1312
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064397"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="aef37-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="aef37-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

><span data-ttu-id="aef37-105">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="aef37-105">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aef37-106">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="aef37-106">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="aef37-107">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="aef37-107">**Applies to:**</span></span>
- [<span data-ttu-id="aef37-108">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="aef37-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="aef37-109">Usa la funzione nelle query di ricerca avanzate per ottenere rapidamente gli indirizzi IP più recenti assegnati `AssignedIPAddresses()` a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aef37-109">Use the `AssignedIPAddresses()` function in your advanced hunting queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="aef37-110">Se si specifica un argomento timestamp, questa funzione ottiene gli indirizzi IP più recenti al momento specificato.</span><span class="sxs-lookup"><span data-stu-id="aef37-110">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span>

<span data-ttu-id="aef37-111">Questa funzione restituisce una tabella con le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="aef37-111">This function returns a table with the following columns:</span></span>

<span data-ttu-id="aef37-112">Colonna</span><span class="sxs-lookup"><span data-stu-id="aef37-112">Column</span></span> | <span data-ttu-id="aef37-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="aef37-113">Data type</span></span> | <span data-ttu-id="aef37-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aef37-114">Description</span></span>
-|-|-
`Timestamp` | <span data-ttu-id="aef37-115">datetime</span><span class="sxs-lookup"><span data-stu-id="aef37-115">datetime</span></span> | <span data-ttu-id="aef37-116">Ora dell'ultima volta in cui il dispositivo è stato osservato usando l'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="aef37-116">Latest time when the device was observed using the IP address</span></span>
`IPAddress` | <span data-ttu-id="aef37-117">stringa</span><span class="sxs-lookup"><span data-stu-id="aef37-117">string</span></span> | <span data-ttu-id="aef37-118">Indirizzo IP utilizzato dal dispositivo</span><span class="sxs-lookup"><span data-stu-id="aef37-118">IP address used by the device</span></span>
`IPType` | <span data-ttu-id="aef37-119">stringa</span><span class="sxs-lookup"><span data-stu-id="aef37-119">string</span></span> | <span data-ttu-id="aef37-120">Indica se l'indirizzo IP è pubblico o privato</span><span class="sxs-lookup"><span data-stu-id="aef37-120">Indicates whether the IP address is a public or private address</span></span>
`NetworkAdapterType` | <span data-ttu-id="aef37-121">int</span><span class="sxs-lookup"><span data-stu-id="aef37-121">int</span></span> | <span data-ttu-id="aef37-122">Tipo di scheda di rete utilizzata dal dispositivo a cui è stato assegnato l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="aef37-122">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="aef37-123">Per i valori possibili, fare riferimento a [questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="aef37-123">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span>
`ConnectedNetworks` | <span data-ttu-id="aef37-124">int</span><span class="sxs-lookup"><span data-stu-id="aef37-124">int</span></span> | <span data-ttu-id="aef37-125">Reti a cui è connessa la scheda con l'indirizzo IP assegnato.</span><span class="sxs-lookup"><span data-stu-id="aef37-125">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="aef37-126">Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o dominio), una descrizione e un flag che indica se è connesso pubblicamente a Internet</span><span class="sxs-lookup"><span data-stu-id="aef37-126">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span>

## <a name="syntax"></a><span data-ttu-id="aef37-127">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aef37-127">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="aef37-128">Argomenti</span><span class="sxs-lookup"><span data-stu-id="aef37-128">Arguments</span></span>

- <span data-ttu-id="aef37-129">**x**— `DeviceId` o valore che identifica il `DeviceName` dispositivo</span><span class="sxs-lookup"><span data-stu-id="aef37-129">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="aef37-130">**y**— Valore (datetime) che indica alla funzione di ottenere gli indirizzi IP assegnati più di recente `Timestamp` da un'ora specifica.</span><span class="sxs-lookup"><span data-stu-id="aef37-130">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="aef37-131">Se non specificato, la funzione restituisce gli indirizzi IP più recenti.</span><span class="sxs-lookup"><span data-stu-id="aef37-131">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="aef37-132">Esempi</span><span class="sxs-lookup"><span data-stu-id="aef37-132">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="aef37-133">Ottenere l'elenco degli indirizzi IP usati da un dispositivo 24 ore fa</span><span class="sxs-lookup"><span data-stu-id="aef37-133">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="aef37-134">Ottenere gli indirizzi IP usati da un dispositivo e trovare i dispositivi che comunicano con esso</span><span class="sxs-lookup"><span data-stu-id="aef37-134">Get IP addresses used by a device and find devices communicating with it</span></span>

<span data-ttu-id="aef37-135">Questa query utilizza la funzione per ottenere gli indirizzi IP assegnati per il dispositivo ( ) in una data specifica o prima `AssignedIPAddresses()` `example-device-name` di ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="aef37-135">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="aef37-136">Usa quindi gli indirizzi IP per trovare le connessioni al dispositivo avviate da altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="aef37-136">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="aef37-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="aef37-137">Related topics</span></span>

- [<span data-ttu-id="aef37-138">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="aef37-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="aef37-139">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="aef37-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="aef37-140">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="aef37-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
