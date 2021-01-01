---
title: Funzione DeviceFromIP () in Advanced Hunting for Microsoft 365 Defender
description: Informazioni su come utilizzare la funzione DeviceFromIP () per ottenere i dispositivi a cui è stato assegnato un indirizzo IP specifico
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, dispositivo, devicefromIP, funzione, arricchimento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741109"
---
# <a name="devicefromip"></a><span data-ttu-id="696bd-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="696bd-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="696bd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="696bd-105">**Applies to:**</span></span>
- <span data-ttu-id="696bd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="696bd-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="696bd-107">Utilizzare la `DeviceFromIP()` funzione nelle query di [caccia avanzate](advanced-hunting-overview.md) per ottenere rapidamente l'elenco di dispositivi assegnati a un determinato indirizzo IP in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="696bd-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="696bd-108">Questa funzione restituisce una tabella con le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="696bd-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="696bd-109">Colonna</span><span class="sxs-lookup"><span data-stu-id="696bd-109">Column</span></span> | <span data-ttu-id="696bd-110">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="696bd-110">Data type</span></span> | <span data-ttu-id="696bd-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="696bd-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="696bd-112">stringa</span><span class="sxs-lookup"><span data-stu-id="696bd-112">string</span></span> | <span data-ttu-id="696bd-113">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="696bd-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="696bd-114">stringa</span><span class="sxs-lookup"><span data-stu-id="696bd-114">string</span></span> | <span data-ttu-id="696bd-115">Identificatore univoco per il dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="696bd-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="696bd-116">Sintassi</span><span class="sxs-lookup"><span data-stu-id="696bd-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="696bd-117">Argomenti</span><span class="sxs-lookup"><span data-stu-id="696bd-117">Arguments</span></span>

<span data-ttu-id="696bd-118">Questa funzione viene richiamata come parte di una query.</span><span class="sxs-lookup"><span data-stu-id="696bd-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="696bd-119">**x**: il primo parametro è in genere già una colonna della query.</span><span class="sxs-lookup"><span data-stu-id="696bd-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="696bd-120">In questo caso, è la colonna denominata `IP` , l'indirizzo IP per il quale si desidera visualizzare un elenco di dispositivi che sono stati assegnati.</span><span class="sxs-lookup"><span data-stu-id="696bd-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="696bd-121">Dovrebbe essere un indirizzo IP locale.</span><span class="sxs-lookup"><span data-stu-id="696bd-121">It should be a local IP address.</span></span> <span data-ttu-id="696bd-122">Gli indirizzi IP esterni non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="696bd-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="696bd-123">**y**-un secondo parametro facoltativo è il `Timestamp` , che indica alla funzione di ottenere i dispositivi assegnati più recenti da un determinato intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="696bd-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="696bd-124">Se non specificato, la funzione restituirà i record disponibili più recenti.</span><span class="sxs-lookup"><span data-stu-id="696bd-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="696bd-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="696bd-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="696bd-126">Ottenere i dispositivi più recenti a cui sono stati assegnati indirizzi IP specifici</span><span class="sxs-lookup"><span data-stu-id="696bd-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="696bd-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="696bd-127">Related topics</span></span>
- [<span data-ttu-id="696bd-128">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="696bd-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="696bd-129">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="696bd-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="696bd-130">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="696bd-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
