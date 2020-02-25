---
title: Tabella DeviceEvents nello schema di caccia avanzato
description: Informazioni su antivirus, firewall e altri tipi di evento nella tabella DeviceEvents (Miscellaneous device events) dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, eventi di sicurezza, antivirus, firewall, exploit Guard, DeviceEvents
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
ms.openlocfilehash: f99420b978f77f8b4a4660394d4a6f335c5aad66
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235045"
---
# <a name="deviceevents"></a>DeviceEvents

**Si applica a:**
- Microsoft Threat Protection



Gli eventi o `DeviceEvents` la tabella del dispositivo miscellaneo nello schema di [caccia avanzato](advanced-hunting-overview.md) contengono informazioni sui vari tipi di evento, tra cui gli eventi attivati dai controlli di sicurezza, ad esempio Windows Defender Antivirus e exploit Protection. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).


| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FolderPath` | stringa | Cartella contenente il file a cui è stata applicata l'azione registrata |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `SHA256` | stringa | SHA-256 del file a cui è stata applicata l'azione registrata. Questo campo in genere non viene popolato, se disponibile, utilizzare la colonna SHA1 |
| `MD5` | stringa | Hash MD5 del file a cui è stata applicata l'azione registrata |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountSid` | stringa | ID di sicurezza (SID) dell'account |
| `RemoteUrl` | stringa | URL o nome di dominio completo (FQDN) connesso a |
| `RemoteDeviceName` | stringa | Nome del computer in cui è stata eseguita un'operazione remota sul computer in questione. A seconda dell'evento segnalato, questo nome potrebbe essere un nome di dominio completo (FQDN), un nome NetBIOS o un nome host senza informazioni sul dominio. |
| `ProcessId` | int | ID processo (PID) del processo appena creato |
| `ProcessCommandLine` | stringa | Riga di comando utilizzata per creare il nuovo processo |
| `ProcessCreationTime` | datetime | Data e ora in cui è stato creato il processo |
| `ProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi del controllo di accesso utente applicato al processo appena creato |
| `LogonId` | stringa | Identificatore per una sessione di accesso. Questo identificatore è univoco nello stesso computer solo tra i riavvii |
| `RegistryKey` | stringa | Chiave del registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueName` | stringa | Nome del valore del registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueData` | stringa | Dati del valore del registro di sistema a cui è stata applicata l'azione registrata |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `RemotePort` | int | Porta TCP sul dispositivo remoto connesso a |
| `LocalIP` | stringa | Indirizzo IP assegnato al computer locale utilizzato durante la comunicazione |
| `LocalPort` | int | Porta TCP sul computer locale utilizzato durante la comunicazione |
| `FileOriginUrl` | stringa | URL da cui è stato scaricato il file |
| `FileOriginIP` | stringa | Indirizzo IP da cui è stato scaricato il file |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'evento nel formato di matrice JSON |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file di immagine) che ha avviato l'evento. Questo campo in genere non viene popolato, se disponibile, utilizzare la colonna SHA1 |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora in cui è stato avviato il processo che ha avviato l'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui è stato avviato l'elemento padre del processo responsabile dell'evento |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | ID di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessLogonId` | stringa | Identificatore per una sessione di accesso del processo che ha avviato l'evento. Questo identificatore è univoco nello stesso computer solo tra i riavvii |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp. |
| `AppGuardContainerId` | stringa | Identificatore per il contenitore virtualizzato utilizzato dalla protezione dell'applicazione per isolare l'attività del browser |

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
