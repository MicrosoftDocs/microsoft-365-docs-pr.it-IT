---
title: Tabella CloudAppEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi da app e servizi cloud nella tabella CloudAppEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca di minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, CloudAppEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 2aa592e70bce7bb469f851bedc542ee58cac0037
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498670"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La tabella nello schema di ricerca avanzata contiene informazioni sulle attività in varie app e servizi cloud trattati da Microsoft Cloud App Security, in particolare `CloudAppEvents` Dropbox, Exchange Online, [](advanced-hunting-overview.md) OneDrive, Microsoft Teams e SharePoint. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!IMPORTANT]
>In questa tabella sono incluse le informazioni disponibili nella `AppFileEvents` tabella. A partire dal 7 marzo 2021, gli utenti che ricercano le attività correlate ai file nei servizi cloud entro e oltre questa data devono utilizzare la `CloudAppEvents` tabella. <br><br>Assicurarsi di cercare query e regole di rilevamento personalizzate che ancora usano la tabella e `AppFileEvents` modificarle per utilizzare la `CloudAppEvents` tabella. Altre indicazioni sulla conversione delle query interessate sono disponibili in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)


Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento |
| `Application` | stringa | Applicazione che ha eseguito l'azione registrata |
| `ApplicationId` | stringa | Identificatore univoco dell'applicazione |
| `AccountObjectId` | stringa | Identificatore univoco dell'account in Azure Active Directory |
| `AccountDisplayName` | stringa | Nome dell'utente dell'account visualizzato nella rubrica. In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome. |
| `IsAdminOperation` | stringa | Indica se l'attività è stata eseguita da un amministratore |
| `DeviceType` | stringa | Tipo di dispositivo basato su scopo e funzionalità, ad esempio "Dispositivo di rete", "Workstation", "Server", "Mobile", "Console di gioco" o "Stampante" | 
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Questa colonna indica sistemi operativi specifici, incluse le varianti della stessa famiglia, ad esempio Windows 10 e Windows 7. |
| `IPAddress` | stringa | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate |
| `IsAnonymousProxy` | stringa | Indica se l'indirizzo IP appartiene a un proxy anonimo noto |
| `CountryCode` | stringa | Codice di due lettere che indica il paese in cui l'indirizzo IP del client è geolocale |
| `City` | stringa | Città in cui l'indirizzo IP del client è geolocato |
| `Isp` | stringa | Provider di servizi Internet (ISP) associato all'indirizzo IP |
| `UserAgent` | stringa | Informazioni agente utente dal Web browser o da un'altra applicazione client |
| `ActivityType` | stringa | Tipo di attività che ha attivato l'evento |
| `ActivityObjects` | stringa | Elenco di oggetti, ad esempio file o cartelle, coinvolti nell'attività registrata |
| `ObjectName` | stringa | Nome dell'oggetto a cui è stata applicata l'azione registrata |
| `ObjectType` | stringa | Tipo di oggetto, ad esempio un file o una cartella, a cui è stata applicata l'azione registrata |
| `ObjectId` | stringa | Identificatore univoco dell'oggetto a cui è stata applicata l'azione registrata |
| `ReportId` | stringa | Identificatore univoco dell'evento |
| `RawEventData` | stringa | Informazioni sugli eventi non elaborati dall'applicazione o dal servizio di origine in formato JSON |
| `AdditionalFields` | stringa | Informazioni aggiuntive sull'entità o sull'evento |


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
