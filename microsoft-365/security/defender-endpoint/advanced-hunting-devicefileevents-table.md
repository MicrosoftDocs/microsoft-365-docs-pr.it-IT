---
title: Tabella DeviceFileEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi correlati ai file nella tabella DeviceFileEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca di minacce, ricerca di minacce informatiche, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, devicefileevents, file, percorso, hash, sha1, sha256, md5, FileCreationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 323cc8e809b81f937a29e41f24c2976c3d5c175b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500859"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La `DeviceFileEvents` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sulla creazione, la modifica e altri eventi del file system. Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

Per informazioni sulle altre tabelle nello schema di ricerca avanzata, vedere la guida di riferimento [allo schema di ricerca avanzata.](advanced-hunting-schema-reference.md)

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco del dispositivo nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FolderPath` | stringa | Cartella contenente il file a cui è stata applicata l'azione registrata |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `SHA256` | stringa | SHA-256 del file a cui è stata applicata l'azione registrata. Questo campo in genere non viene popolato: utilizzare la colonna SHA1 quando disponibile |
| `MD5` | stringa | Hash MD5 del file a cui è stata applicata l'azione registrata |
| `FileOriginUrl` | stringa | URL da cui è stato scaricato il file |
| `FileOriginReferrerUrl` | stringa | URL della pagina Web collegata al file scaricato |
| `FileOriginIP` | stringa | Indirizzo IP da cui è stato scaricato il file |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | Identificatore di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora di inizio del processo che ha avviato l'evento |
| `InitiatingProcessIntegrityLevel` | stringa | livello di integrità del processo che ha avviato l'evento. Windows assegna livelli di integrità ai processi in base a determinate caratteristiche, ad esempio se sono stati avviati da un download Internet. Questi livelli di integrità influenzano le autorizzazioni per le risorse |
| `InitiatingProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi UAC (User Access Control) applicata al processo che ha avviato l'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui l'elemento padre del processo responsabile dell'evento è stato avviato |
| `RequestProtocol` | stringa | Protocollo di rete, se applicabile, utilizzato per avviare l'attività: Sconosciuto, Locale, SMB o NFS |
| `ShareName` | stringa | Nome della cartella condivisa contenente il file |
| `RequestSourceIP` | stringa | Indirizzo IPv4 o IPv6 del dispositivo remoto che ha avviato l'attività |
| `RequestSourcePort` | stringa | Porta di origine nel dispositivo remoto che ha avviato l'attività |
| `RequestAccountName` | stringa | Nome utente dell'account utilizzato per avviare l'attività in remoto |
| `RequestAccountDomain` | stringa | Dominio dell'account utilizzato per avviare l'attività in remoto |
| `RequestAccountSid` | stringa | Identificatore di sicurezza (SID) dell'account per avviare l'attività in remoto |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp |
| `AppGuardContainerId` | stringa | Identificatore del contenitore virtualizzato utilizzato da Application Guard per isolare l'attività del browser |
| `SensitivityLabel` | stringa | Etichetta applicata a un messaggio di posta elettronica, un file o altro contenuto per classificarlo per la protezione delle informazioni |
| `SensitivitySubLabel` | stringa | Sottoetichetta applicata a un messaggio di posta elettronica, un file o altro contenuto per classificarlo per la protezione delle informazioni; Le sottoetichetta di riservatezza sono raggruppate sotto le etichette di riservatezza, ma vengono trattate in modo indipendente |
| `IsAzureInfoProtectionApplied` | boolean | Indica se il file è crittografato da Azure Information Protection |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprensione dello schema](advanced-hunting-schema-reference.md)
