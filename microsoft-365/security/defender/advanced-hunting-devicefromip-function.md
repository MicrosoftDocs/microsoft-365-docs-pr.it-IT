---
title: Funzione DeviceFromIP() nella ricerca avanzata per Microsoft 365 Defender
description: Informazioni su come usare la funzione DeviceFromIP() per ottenere i dispositivi a cui è stato assegnato un indirizzo IP specifico
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, dispositivo, devicefromIP, funzione, arricchimento
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
ms.openlocfilehash: 3ea951e35555721a989001b2a5235df5b89a8a55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933182"
---
# <a name="devicefromip"></a><span data-ttu-id="5e371-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="5e371-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5e371-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5e371-105">**Applies to:**</span></span>
- <span data-ttu-id="5e371-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e371-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="5e371-107">Usa la funzione nelle query di ricerca avanzate per ottenere rapidamente l'elenco dei dispositivi assegnati a un determinato indirizzo `DeviceFromIP()` IP in un determinato momento. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5e371-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="5e371-108">Questa funzione restituisce una tabella con le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e371-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="5e371-109">Colonna</span><span class="sxs-lookup"><span data-stu-id="5e371-109">Column</span></span> | <span data-ttu-id="5e371-110">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5e371-110">Data type</span></span> | <span data-ttu-id="5e371-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e371-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="5e371-112">stringa</span><span class="sxs-lookup"><span data-stu-id="5e371-112">string</span></span> | <span data-ttu-id="5e371-113">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="5e371-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="5e371-114">stringa</span><span class="sxs-lookup"><span data-stu-id="5e371-114">string</span></span> | <span data-ttu-id="5e371-115">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="5e371-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="5e371-116">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e371-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="5e371-117">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5e371-117">Arguments</span></span>

<span data-ttu-id="5e371-118">Questa funzione viene richiamata come parte di una query.</span><span class="sxs-lookup"><span data-stu-id="5e371-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="5e371-119">**x**: il primo parametro è in genere già una colonna nella query.</span><span class="sxs-lookup"><span data-stu-id="5e371-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="5e371-120">In questo caso, è la colonna denominata , l'indirizzo IP per il quale si desidera visualizzare un elenco dei dispositivi a cui è `IP` stato assegnato.</span><span class="sxs-lookup"><span data-stu-id="5e371-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="5e371-121">Deve essere un indirizzo IP locale.</span><span class="sxs-lookup"><span data-stu-id="5e371-121">It should be a local IP address.</span></span> <span data-ttu-id="5e371-122">Gli indirizzi IP esterni non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="5e371-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="5e371-123">**y**- Un secondo parametro facoltativo è , che indica alla funzione di ottenere i dispositivi assegnati più recenti `Timestamp` da un momento specifico.</span><span class="sxs-lookup"><span data-stu-id="5e371-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="5e371-124">Se non viene specificato, la funzione restituisce gli ultimi record disponibili.</span><span class="sxs-lookup"><span data-stu-id="5e371-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="5e371-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e371-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="5e371-126">Ottenere i dispositivi più recenti a cui sono stati assegnati indirizzi IP specifici</span><span class="sxs-lookup"><span data-stu-id="5e371-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="5e371-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5e371-127">Related topics</span></span>
- [<span data-ttu-id="5e371-128">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="5e371-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5e371-129">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="5e371-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5e371-130">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="5e371-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
