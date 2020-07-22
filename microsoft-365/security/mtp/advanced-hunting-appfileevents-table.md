---
title: Tabella AppFileEvents nello schema di caccia avanzato
description: Informazioni sugli eventi correlati ai file associati alle app e ai servizi cloud nella tabella AppFileEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AppFileEvents, cloud app Security, MCAS
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 663dc2a3de676fa2daeab3d9621254e956d42fc4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204756"
---
# <a name="appfileevents"></a>AppFileEvents

**Si applica a:**
- Microsoft Threat Protection

La `AppFileEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulle attività correlate ai file nelle app e nei servizi cloud monitorati da Microsoft cloud app Security. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento |
| `Application` | stringa | Applicazione in cui è stata eseguita l'azione registrata |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FolderPath` | stringa | Cartella contenente il file a cui è stata applicata l'azione registrata |
| `PreviousFileName` | stringa | Nome originale del file che è stato rinominato come risultato dell'azione |
| `PreviousFolderPath` | stringa | Cartella originale contenente il file prima dell'applicazione dell'azione registrata |
| `Protocol` | stringa | Protocollo di rete utilizzato |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco per l'account in Azure AD |
| `AccountDisplayName` | stringa | Nome dell'account utente visualizzato nella rubrica. In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome. |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo |
| `DeviceType` | stringa | Tipo di dispositivo | 
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. |
| `IPAddress` | stringa | Indirizzo IP assegnato all'endpoint e utilizzato durante le comunicazioni di rete correlate |
| `DestinationDeviceName` | stringa | Nome del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `DestinationIPAddress` | stringa | Indirizzo IP del dispositivo che esegue l'applicazione server che ha elaborato l'azione registrata |
| `Location` | stringa | Città, paese o altra località geografica associata all'evento |
| `Isp` | stringa | Provider di servizi Internet (ISP) associato all'indirizzo IP dell'endpoint |
| `ReportId` | long | Identificatore univoco per l'evento |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'entità o sull'evento |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
