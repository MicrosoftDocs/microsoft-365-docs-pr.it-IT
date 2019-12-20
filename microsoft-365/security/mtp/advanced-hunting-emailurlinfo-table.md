---
title: Tabella EmailUrlInfo nello schema per Ricerca avanzata
description: Informazioni sugli URL o sui collegamenti nella tabella EmailUrlInfo dello schema per Ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca minacce informatiche, ricerca, eseguire una query, telemetria, riferimento dello schema, esplora dati, tabella, colonna, tipo di dati, descrizione, EmailUrlInfo, id messaggi di rete, url, collegamento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da9712d1f3465c28d2ba880997a52434723a297d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808671"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La tabella `EmailUrlInfo` nello schema per [Ricerca avanzata](advanced-hunting-overview.md) contiene informazioni riguardanti gli URL nei messaggi di posta elettronica e gli allegati elaborati da Office 365 ATP. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `UrlId` | stringa | Identificatore univoco per l'URL nell'oggetto, nel corpo o nell'allegato del messaggio di posta elettronica |
| `NetworkMessageId` | stringa | Identificatore univoco per la posta elettronica, generato da Office 365 |
| `Url` | stringa | URL completo nell'oggetto, nel corpo o nell'allegato del messaggio di posta elettronica |

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)