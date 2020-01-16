---
title: Tabella EmailUrlInfo nello schema per Ricerca avanzata
description: Informazioni sugli URL o sui collegamenti nella tabella EmailUrlInfo dello schema per Ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento dello schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailUrlInfo, ID messaggio di rete, URL, collegamento
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
ms.openlocfilehash: 42b7d1734c5925ba493f647268852637072fc4a3
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210331"
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