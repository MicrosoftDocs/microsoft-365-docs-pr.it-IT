---
title: Tabella AlertEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi di generazione di avvisi nella tabella AlertEvents dello schema per Ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, ricerche, query, telemetria, schema di riferimento, esplora dati, tabella, colonna, tipo di dati, descrizione, alertevents, avviso, gravità, categoria
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
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911230"
---
# <a name="alertevents"></a>AlertEvents

**Si applica a:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

La tabella `AlertEvents` nello schema per [Ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli avvisi di Microsoft Defender Advanced Threat Protection. Utilizzare questo riferimento per creare query che forniscano informazioni da questa tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `AlertId` | stringa | Identificatore univoco dell'avviso |
| `EventTime` | datetime | Data e ora in cui è stato registrato l’evento |
| `MachineId` | stringa | Identificatore univoco per il computer nel servizio |
| `ComputerName` | stringa | Nome di dominio completo (FQDN) del computer |
| `Severity` | stringa | Indica il potenziale impatto (alto, medio o basso) dell'indicatore di minaccia o della violazione identificata dall'avviso |
| `Category` | stringa | Tipo di indicatore di minaccia o di attività di violazione identificate dall'avviso |
| `Title` | stringa | Titolo dell'avviso |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `RemoteUrl` | stringa | URL o nome di dominio completo (FQDN) connesso a |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare eventi univoci, questa colonna deve essere usata in combinazione con le colonne ComputerName ed EventTime |
| `Table` | stringa | Tabella che contiene i dettagli dell'evento |

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e email](advanced-hunting-query-emails-devices.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
- [Applicazione delle procedure consigliate per le query](advanced-hunting-best-practices.md)
