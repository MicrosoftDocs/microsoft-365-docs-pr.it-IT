---
title: Tabella CloudAppEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi dalle app e dai servizi cloud nella tabella CloudAppEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: a8ba1f94bc704a5fe99d54b77aa6570c5e43d3f7
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712487"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La tabella nello schema di ricerca avanzata contiene informazioni sulle attività in varie app cloud e servizi coperti da Microsoft Cloud App Security, in particolare `CloudAppEvents` Dropbox, Exchange Online, [](advanced-hunting-overview.md) OneDrive, Microsoft Teams e SharePoint. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!IMPORTANT]
>In questa tabella sono incluse le informazioni disponibili nella `AppFileEvents` tabella. A partire dal 7 marzo 2021, gli utenti possono eseguire la ricerca delle attività relative ai file nei servizi cloud in data successiva a questa `CloudAppEvents` data. <br><br>Assicurarsi di cercare query e regole di rilevamento personalizzate che ancora usano la tabella e `AppFileEvents` modificarle per l'utilizzo della `CloudAppEvents` tabella. Altre indicazioni sulla conversione delle query interessate sono disponibili in Hunt nelle attività dell'app cloud con La ricerca avanzata di [Microsoft 365 Defender.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)


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
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Questa colonna indica sistemi operativi specifici, incluse le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7. |
| `IPAddress` | stringa | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate |
| `IsAnonymousProxy` | stringa | Indica se l'indirizzo IP appartiene a un proxy anonimo noto |
| `CountryCode` | stringa | Codice di due lettere che indica il paese in cui l'indirizzo IP del client è geolocato |
| `City` | stringa | Città in cui l'indirizzo IP del client è geolocato |
| `Isp` | stringa | Provider di servizi Internet (ISP) associato all'indirizzo IP |
| `UserAgent` | stringa | Informazioni sull'agente utente dal Web browser o da un'altra applicazione client |
| `ActivityType` | stringa | Tipo di attività che ha attivato l'evento |
| `ActivityObjects` | stringa | Elenco di oggetti, ad esempio file o cartelle, coinvolti nell'attività registrata |
| `ObjectName` | stringa | Nome dell'oggetto a cui è stata applicata l'azione registrata |
| `ObjectType` | stringa | Tipo di oggetto, ad esempio un file o una cartella, a cui è stata applicata l'azione registrata |
| `ObjectId` | stringa | Identificatore univoco dell'oggetto a cui è stata applicata l'azione registrata |
| `ReportId` | stringa | Identificatore univoco dell'evento |
| `RawEventData` | stringa | Informazioni sugli eventi non elaborati dall'applicazione o dal servizio di origine in formato JSON |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'entità o sull'evento |


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
