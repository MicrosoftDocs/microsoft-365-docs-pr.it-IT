---
title: Tabella DeviceEvents nello schema di ricerca avanzata
description: Informazioni su antivirus, firewall e altri tipi di eventi nella tabella degli eventi vari dei dispositivi (DeviceEvents) dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, eventi di sicurezza, antivirus, firewall, exploit guard, DeviceEvents
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
ms.openlocfilehash: 02e0caed602ffa14a756f0cc8e695fc9fb953efc
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712475"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La tabella o gli eventi vari dei dispositivi nello schema di ricerca avanzata contengono informazioni sui vari tipi di evento, inclusi gli eventi attivati dai controlli di sicurezza, ad esempio Windows Defender Antivirus e `DeviceEvents` protezione dagli exploit. [](advanced-hunting-overview.md) Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).


| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento. Per informazioni [dettagliate, vedere la guida di riferimento](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) allo schema nel portale |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FolderPath` | stringa | Cartella contenente il file a cui è stata applicata l'azione registrata |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `SHA256` | stringa | SHA-256 del file a cui è stata applicata l'azione registrata. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `MD5` | stringa | Hash MD5 del file a cui è stata applicata l'azione registrata |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountSid` | stringa | Identificatore di sicurezza (SID) dell'account |
| `RemoteUrl` | stringa | URL o nome di dominio completo (FQDN) connesso a |
| `RemoteDeviceName` | stringa | Nome del computer che ha eseguito un'operazione remota nel computer interessato. A seconda dell'evento segnalato, questo nome può essere un nome di dominio completo (FQDN), un nome NetBIOS o un nome host senza informazioni sul dominio |
| `ProcessId` | int | ID processo (PID) del processo appena creato |
| `ProcessCommandLine` | stringa | Riga di comando utilizzata per creare il nuovo processo |
| `ProcessCreationTime` | datetime | Data e ora di creazione del processo |
| `ProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi del controllo di accesso utente applicata al processo appena creato |
| `LogonId` | stringa | Identificatore di una sessione di accesso. Questo identificatore è univoco nello stesso computer solo tra un riavvio e l'altro |
| `RegistryKey` | stringa | Chiave del Registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueName` | stringa | Nome del valore del Registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueData` | stringa | Dati del valore del Registro di sistema a cui è stata applicata l'azione registrata |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `RemotePort` | int | Porta TCP nel dispositivo remoto a cui era in corso la connessione |
| `LocalIP` | stringa | Indirizzo IP assegnato al computer locale utilizzato durante la comunicazione |
| `LocalPort` | int | Porta TCP sul computer locale utilizzata durante la comunicazione |
| `FileOriginUrl` | stringa | URL da cui è stato scaricato il file |
| `FileOriginIP` | stringa | Indirizzo IP da cui è stato scaricato il file |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'evento in formato matrice JSON |
| `InitiatingProcessFileSize` | long | Dimensioni del file che ha eseguito il processo responsabile dell'evento |
| `FileSize` | long | Dimensioni del file in byte |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file di immagine) che ha avviato l'evento. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file immagine) che ha avviato l'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora di inizio del processo che ha avviato l'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui è stato avviato l'elemento padre del processo responsabile dell'evento |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file immagine) che ha avviato l'evento |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | Identificatore di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountObjectId` | stringa | ID oggetto di Azure AD dell'account utente che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessLogonId` | stringa | Identificatore di una sessione di accesso del processo che ha avviato l'evento. Questo identificatore è univoco nello stesso computer solo tra un riavvio e l'altro |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare eventi univoci, questa colonna deve essere usata insieme alle colonne DeviceName e Timestamp |
| `AppGuardContainerId` | stringa | Identificatore del contenitore virtualizzato usato da Application Guard per isolare l'attività del browser |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
