---
title: Tabella CloudAppEvents nello schema di caccia avanzato
description: Informazioni sugli eventi delle app e dei servizi cloud nella tabella CloudAppEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, CloudAppEvents, cloud app Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087767"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Attualmente disponibile in anteprima, la `CloudAppEvents` tabella nello schema di [caccia avanzato](advanced-hunting-overview.md) contiene informazioni sulle attività in diverse app e servizi cloud, in particolare Microsoft teams ed Exchange Online. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

La tabella verrà espansa per includere più attività monitorate da Microsoft cloud app Security. Alla fine, questa tabella includerà l'attività dei file attualmente archiviati nella tabella [AppFileEvents](advanced-hunting-appfileevents-table.md) . Microsoft fornirà indicazioni aggiuntive per spostare i dati in questa tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento |
| `Application` | stringa | Applicazione in cui è stata eseguita l'azione registrata |
| `ApplicationId` | stringa | Identificatore univoco per l'applicazione |
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure Active Directory |
| `AccountDisplayName` | stringa | Nome dell'account utente visualizzato nella rubrica. In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome. |
| `IsAdminOperation` | stringa | Indica se l'attività è stata eseguita da un amministratore |
| `DeviceType` | stringa | Tipo di dispositivo basato su scopo e funzionalità, ad esempio "Network Device", "workstation", "Server", "mobile", "Gaming Console" o "Printer" | 
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. In questa colonna sono indicati sistemi operativi specifici, tra cui le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7. |
| `IPAddress` | stringa | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate |
| `IsAnonymousProxy` | stringa | Indica se l'indirizzo IP appartiene a un proxy anonimo conosciuto |
| `CountryCode` | stringa | Codice di due lettere che indica il paese in cui l'indirizzo IP del client è Geolocated |
| `City` | stringa | Città in cui l'indirizzo IP del client è Geolocated |
| `Isp` | stringa | Provider di servizi Internet (ISP) associato all'indirizzo IP |
| `UserAgent` | stringa | Informazioni sull'agente utente dal Web browser o da un'altra applicazione client |
| `ActivityType` | stringa | Tipo di attività che ha attivato l'evento |
| `ActivityObjects` | stringa | Elenco di oggetti, ad esempio file o cartelle, che sono stati coinvolti nell'attività registrata |
| `ObjectName` | stringa | Nome dell'oggetto a cui è stata applicata l'azione registrata |
| `ObjectType` | stringa | Tipo di oggetto, ad esempio un file o una cartella, a cui è stata applicata l'azione registrata |
| `ObjectId` | stringa | Identificatore univoco dell'oggetto a cui è stata applicata l'azione registrata |
| `ReportId` | stringa | Identificatore univoco per l'evento |
| `RawEventData` | stringa | Informazioni sugli eventi RAW dall'applicazione o dal servizio di origine in formato JSON |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'entità o sull'evento |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
