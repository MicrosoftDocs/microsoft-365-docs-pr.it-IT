---
title: Flusso dell'evento Microsoft Defender for Endpoint
description: Informazioni su come configurare Microsoft Defender per Endpoint per trasmettere eventi di ricerca avanzata agli hub eventi o all'account di archiviazione di Azure
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
ms.openlocfilehash: 27d1b36f3e49112a2da95f9268c0e05fcaa72c89
ms.sourcegitcommit: f0118e61e490496cb23189cc5c73b23e2ba939be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52780142"
---
# <a name="raw-data-streaming-api"></a>Raw Data Streaming API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Trasmettere gli eventi di ricerca avanzata agli hub eventi e/o all'account di archiviazione di Azure.

Defender for Endpoint supporta lo streaming di tutti gli eventi disponibili tramite [Advanced Hunting](advanced-hunting-overview.md) a un [hub eventi](/azure/event-hubs/) e/o a un account di archiviazione [di Azure.](/azure/event-hubs/)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>Contenuto della sezione

Argomento | Descrizione
:---|:---
[Trasmettere gli eventi di Microsoft Defender for Endpoint agli hub eventi di Azure](raw-data-export-event-hub.md)| Scopri come abilitare l'API di streaming nel tenant e configurare Defender per Endpoint per trasmettere [la ricerca avanzata](advanced-hunting-overview.md) agli hub eventi.
[Stream Defender for Endpoint events to your Azure storage account](raw-data-export-storage.md)| Informazioni sull'abilitazione dell'API di streaming nel tenant e sulla configurazione di Defender per Endpoint per la trasmissione [di Ricerca avanzata](advanced-hunting-overview.md) al tuo account di archiviazione di Azure.


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Documentazione di Azure Event Hubs](/azure/event-hubs/)
- [Archiviazione di Azure Documentazione dell'account](/azure/storage/common/storage-account-overview)