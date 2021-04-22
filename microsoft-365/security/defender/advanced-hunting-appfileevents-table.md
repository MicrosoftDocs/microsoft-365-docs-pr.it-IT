---
title: Tabella AppFileEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi correlati ai file associati alle app e ai servizi cloud nella tabella AppFileEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca di minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 861a04eb168190f2bb64bbb0258de6767c619e1b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934718"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La tabella nello schema di ricerca avanzata contiene informazioni sulle attività correlate ai file nelle app cloud e nei servizi `AppFileEvents` monitorati da Microsoft Cloud App Security. [](advanced-hunting-overview.md) Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!WARNING]
>Questa tabella verrà ritirata a breve. A partire dal 7 marzo 2021, la tabella non `AppFileEvents` registra più i record. Gli utenti che ricercano le attività correlate ai file nei servizi cloud oltre e oltre la data specificata dovrebbero usare invece la [tabella CloudAppEvents.](advanced-hunting-cloudappevents-table.md) <br><br>Assicurarsi di cercare query e regole di rilevamento personalizzate che ancora usano la tabella e `AppFileEvents` modificarle per utilizzare la `CloudAppEvents` tabella. Altre indicazioni sulla conversione delle query interessate sono disponibili in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)


Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento. Per informazioni [dettagliate, vedere](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) informazioni di riferimento sullo schema nel portale |
| `Application` | stringa | Applicazione che ha eseguito l'azione registrata |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FolderPath` | stringa | Cartella contenente il file a cui è stata applicata l'azione registrata |
| `PreviousFileName` | stringa | Nome originale del file rinominato in seguito all'azione |
| `PreviousFolderPath` | stringa | Cartella originale contenente il file prima dell'applicazione dell'azione registrata |
| `Protocol` | stringa | Protocollo di rete utilizzato |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountSid` | stringa | Identificatore di sicurezza (SID) dell'account |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco dell'account in Azure AD |
| `AccountDisplayName` | stringa | Nome dell'utente dell'account visualizzato nella rubrica. In genere una combinazione di un nome o di un dato nome, un'iniziazione intermedia e un cognome o un cognome. |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo |
| `DeviceType` | stringa | Tipo di dispositivo | 
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. |
| `IPAddress` | stringa | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate |
| `Port` | stringa | Porta TCP utilizzata durante la comunicazione  |
| `DestinationDeviceName` | stringa | Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `DestinationIPAddress` | stringa | Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `DestinationPort` | stringa | Porta di destinazione delle comunicazioni di rete correlate |
| `Location` | stringa | Città, paese o altra posizione geografica associata all'evento |
| `Isp` | stringa | Provider di servizi Internet (ISP) associato all'indirizzo IP dell'endpoint |
| `ReportId` | long | Identificatore univoco dell'evento |
| `AdditionalFields` | stringa | Informazioni aggiuntive sull'entità o sull'evento |

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza.


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
