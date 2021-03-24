---
title: Flusso dell'evento Microsoft Defender for Endpoint
description: Informazioni su come configurare Microsoft Defender ATP per trasmettere eventi di ricerca avanzata agli hub eventi o all'account di archiviazione di Azure
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
ms.openlocfilehash: 22f4e4c974b60e291273eb9bebfa34583f4e2fb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063845"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="64bac-104">Raw Data Streaming API</span><span class="sxs-lookup"><span data-stu-id="64bac-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64bac-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="64bac-105">**Applies to:**</span></span>
- [<span data-ttu-id="64bac-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="64bac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="64bac-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="64bac-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64bac-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="64bac-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="64bac-109">Trasmettere gli eventi di ricerca avanzata agli hub eventi e/o all'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="64bac-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="64bac-110">Defender for Endpoint supporta lo streaming di tutti gli eventi disponibili tramite [Advanced Hunting](advanced-hunting-overview.md) a un [hub eventi](https://docs.microsoft.com/azure/event-hubs/) e/o a un account di archiviazione [di Azure.](https://docs.microsoft.com/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="64bac-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) and/or [Azure storage account](https://docs.microsoft.com/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="64bac-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="64bac-111">In this section</span></span>

<span data-ttu-id="64bac-112">Argomento</span><span class="sxs-lookup"><span data-stu-id="64bac-112">Topic</span></span> | <span data-ttu-id="64bac-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64bac-113">Description</span></span>
:---|:---
[<span data-ttu-id="64bac-114">Trasmettere gli eventi di Microsoft Defender for Endpoint agli hub eventi di Azure</span><span class="sxs-lookup"><span data-stu-id="64bac-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="64bac-115">Scopri come abilitare l'API di streaming nel tenant e configurare Defender per Endpoint per trasmettere [la ricerca avanzata](advanced-hunting-overview.md) agli hub eventi.</span><span class="sxs-lookup"><span data-stu-id="64bac-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="64bac-116">Stream Defender for Endpoint events to your Azure storage account</span><span class="sxs-lookup"><span data-stu-id="64bac-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="64bac-117">Informazioni sull'abilitazione dell'API di streaming nel tenant e sulla configurazione di Defender per Endpoint per la trasmissione [di Ricerca avanzata](advanced-hunting-overview.md) al tuo account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="64bac-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="64bac-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="64bac-118">Related topics</span></span>
- [<span data-ttu-id="64bac-119">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="64bac-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="64bac-120">Documentazione di Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="64bac-120">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="64bac-121">Documentazione relativa all'account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="64bac-121">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
