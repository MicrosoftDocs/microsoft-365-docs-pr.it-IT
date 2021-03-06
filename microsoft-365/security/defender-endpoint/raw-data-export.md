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
ms.custom: api
ms.openlocfilehash: c8403dee11070dcf0825fad2502d8d21d54933fd
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782754"
---
# <a name="raw-data-streaming-api"></a>Raw Data Streaming API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Trasmettere gli eventi di ricerca avanzata agli hub eventi e/o all'account di archiviazione di Azure.


Microsoft Defender for Endpoint supporta gli eventi di streaming disponibili tramite [Advanced Hunting](../defender/advanced-hunting-overview.md) per un [hub eventi](/azure/event-hubs/) e/o un account di archiviazione [di Azure.](/azure/storage/common/storage-account-overview)

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