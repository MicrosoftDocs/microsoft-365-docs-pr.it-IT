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
ms.openlocfilehash: 971cc757dcbd0a190917d2a5f11eb7f68b758008
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778198"
---
# <a name="streaming-api"></a>Streaming API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Trasmettere gli eventi di ricerca avanzata agli hub eventi e/o all'account di archiviazione di Azure.

Microsoft 365 Defender supporta lo streaming di tutti gli eventi disponibili tramite [Advanced Hunting](../defender/advanced-hunting-overview.md) a un [hub eventi](/azure/event-hubs/) e/o a un account di archiviazione [di Azure.](/azure/event-hubs/)



## <a name="in-this-section"></a>Contenuto della sezione

Argomento | Descrizione
:---|:---
[Trasmettere eventi agli hub eventi di Azure](raw-data-export-event-hub.md)| Scopri come abilitare l'API di streaming nel tenant e configurare Microsoft 365 Defender per trasmettere la ricerca [avanzata](../defender/advanced-hunting-overview.md) agli hub eventi.
[Trasmettere eventi all'account di archiviazione di Azure](raw-data-export-storage.md)| Informazioni sull'abilitazione dell'API di streaming nel tenant e configurare Microsoft 365 Defender per trasmettere [ricerca avanzata](../defender/advanced-hunting-overview.md) al tuo account di archiviazione di Azure.


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](../defender/advanced-hunting-overview.md)
- [Documentazione di Azure Event Hubs](/azure/event-hubs/)
- [Archiviazione di Azure Documentazione dell'account](/azure/storage/common/storage-account-overview)
