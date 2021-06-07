---
title: Flusso di Microsoft 365 Defender
description: Informazioni su come configurare Microsoft 365 Defender per trasmettere eventi di ricerca avanzata agli hub eventi o all'account di archiviazione di Azure
keywords: esportazione di dati non elaborati, API di streaming, API, hub eventi, archiviazione di Azure, account di archiviazione, Ricerca avanzata, condivisione di dati non elaborati
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fad3dd64c9acf079bd8da778d417240c44031569
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772471"
---
# <a name="streaming-api"></a><span data-ttu-id="70f65-104">Streaming API</span><span class="sxs-lookup"><span data-stu-id="70f65-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="70f65-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="70f65-105">**Applies to:**</span></span>
- [<span data-ttu-id="70f65-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70f65-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="70f65-107">Trasmettere gli eventi di ricerca avanzata agli hub eventi e/o all'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="70f65-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="70f65-108">Microsoft 365 Defender supporta lo streaming di tutti gli eventi disponibili tramite [Advanced Hunting](../defender/advanced-hunting-overview.md) a un [hub eventi](/azure/event-hubs/) e/o a un account di archiviazione [di Azure.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="70f65-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="70f65-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="70f65-109">In this section</span></span>

<span data-ttu-id="70f65-110">Argomento</span><span class="sxs-lookup"><span data-stu-id="70f65-110">Topic</span></span> | <span data-ttu-id="70f65-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70f65-111">Description</span></span>
:---|:---
[<span data-ttu-id="70f65-112">Trasmettere eventi agli hub eventi di Azure</span><span class="sxs-lookup"><span data-stu-id="70f65-112">Stream events to Azure Event Hubs</span></span>](streaming-api-event-hub.md)| <span data-ttu-id="70f65-113">Scopri come abilitare l'API di streaming nel tenant e configurare Microsoft 365 Defender per trasmettere la ricerca [avanzata](../defender/advanced-hunting-overview.md) agli hub eventi.</span><span class="sxs-lookup"><span data-stu-id="70f65-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="70f65-114">Trasmettere eventi all'account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="70f65-114">Stream events to your Azure storage account</span></span>](streaming-api-storage.md)| <span data-ttu-id="70f65-115">Informazioni sull'abilitazione dell'API di streaming nel tenant e configurare Microsoft 365 Defender per trasmettere [ricerca avanzata](advanced-hunting-overview.md) al tuo account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="70f65-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="70f65-116">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="70f65-116">Related topics</span></span>
- [<span data-ttu-id="70f65-117">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="70f65-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="70f65-118">Documentazione di Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="70f65-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="70f65-119">Archiviazione di Azure Documentazione dell'account</span><span class="sxs-lookup"><span data-stu-id="70f65-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
