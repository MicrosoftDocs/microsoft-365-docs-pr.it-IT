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
ms.openlocfilehash: ee14dcc1c2ae0a2bc6fa3c094d757441515f00de
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807015"
---
# <a name="alertevents"></a>AlertEvents

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La tabella `AlertEvents` nello schema per [Ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli avvisi di Microsoft Defender Advanced Threat Protection. Utilizzare questo riferimento per creare query che forniscano informazioni da questa tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `AlertId` | stringa | Identificatore univoco dell'avviso |
| `Timestamp` | datetime | Data e ora in cui è stato registrato l’evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `Severity` | stringa | Indica il potenziale impatto (alto, medio o basso) dell'indicatore di minaccia o della violazione identificata dall'avviso |
| `Category` | stringa | Tipo di indicatore di minaccia o di attività di violazione identificate dall'avviso |
| `Title` | stringa | Titolo dell'avviso |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `RemoteUrl` | stringa | URL o nome di dominio completo (FQDN) connesso a |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp. |
| `Table` | stringa | Tabella che contiene i dettagli dell'evento |

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e email](advanced-hunting-query-emails-devices.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
- [Applicazione delle procedure consigliate per le query](advanced-hunting-best-practices.md)
