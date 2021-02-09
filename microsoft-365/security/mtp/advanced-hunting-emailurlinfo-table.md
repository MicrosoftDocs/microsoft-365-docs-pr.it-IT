---
title: Tabella EmailUrlInfo nello schema per Ricerca avanzata
description: Informazioni sugli URL o sui collegamenti nella tabella EmailUrlInfo dello schema per Ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, EmailUrlInfo, ID messaggio di rete, url, collegamento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 76a2389eace73ee9d21962c8c618e0dac9994de0
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145464"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La tabella nello schema di ricerca avanzata contiene informazioni sugli URL nei messaggi di posta elettronica e negli allegati elaborati `EmailUrlInfo` da Microsoft Defender per Office 365. [](advanced-hunting-overview.md) Usare questo riferimento per creare query che restituiscono informazioni dalla tabella. 

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `NetworkMessageId` | stringa | Identificatore univoco del messaggio di posta elettronica, generato da Microsoft 365 |
| `Url` | stringa | URL completo nell'oggetto, nel corpo o nell'allegato del messaggio di posta elettronica |
| `UrlDomain` | stringa | Nome di dominio o nome host dell'URL |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare eventi univoci, questa colonna deve essere usata insieme alle colonne DeviceName e Timestamp |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
