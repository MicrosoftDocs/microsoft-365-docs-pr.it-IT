---
title: Tabella DeviceFileEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi correlati ai file nella tabella DeviceFileEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca di minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, filecreationevents, DeviceFileEvents, file, percorso, hash, sha1, sha256, md5
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
ms.openlocfilehash: 6528d25b385a2b4eafc408cbfb6609372a6688de
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498592"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La `DeviceFileEvents` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sulla creazione, la modifica e altri eventi del file system. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento. Per informazioni [dettagliate, vedere](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) informazioni di riferimento sullo schema nel portale |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FolderPath` | stringa | Cartella contenente il file a cui è stata applicata l'azione registrata |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `SHA256` | stringa | SHA-256 del file a cui è stata applicata l'azione registrata. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `MD5` | stringa | Hash MD5 del file a cui è stata applicata l'azione registrata |
| `FileOriginUrl` | stringa | URL da cui è stato scaricato il file |
| `FileOriginReferrerUrl` | stringa | URL della pagina Web collegata al file scaricato |
| `FileOriginIP` | stringa | Indirizzo IP da cui è stato scaricato il file |
| `PreviousFolderPath` | stringa | Cartella originale contenente il file prima dell'applicazione dell'azione registrata |
| `PreviousFileName` | stringa | Nome originale del file rinominato in seguito all'azione |
| `FileSize` | long | Dimensioni del file in byte |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | Identificatore di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountObjectId` | stringa | ID oggetto di Azure AD dell'account utente che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file di immagine) che ha avviato l'evento. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessFileSize` | long | Dimensioni del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessVersionInfoCompanyName` | stringa | Nome della società dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
| `InitiatingProcessVersionInfoProductName` | stringa | Nome del prodotto dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
|` InitiatingProcessVersionInfoProductVersion` | stringa | Versione del prodotto dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
|` InitiatingProcessVersionInfoInternalFileName` | stringa | Nome file interno dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
| `InitiatingProcessVersionInfoOriginalFileName` | stringa | Nome del file originale dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
| `InitiatingProcessVersionInfoFileDescription` | stringa | Descrizione dalle informazioni sulla versione del processo (file immagine) responsabile dell'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora di inizio del processo che ha avviato l'evento |
| `InitiatingProcessIntegrityLevel` | stringa | Livello di integrità del processo che ha avviato l'evento. Windows assegna livelli di integrità ai processi in base a determinate caratteristiche, ad esempio se sono stati avviati da un download Internet. Questi livelli di integrità influenzano le autorizzazioni per le risorse |
| `InitiatingProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi UAC (User Access Control) applicata al processo che ha avviato l'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui l'elemento padre del processo responsabile dell'evento è stato avviato |
| `RequestProtocol` | stringa | Protocollo di rete, se applicabile, utilizzato per avviare l'attività: Sconosciuto, Locale, SMB o NFS |
| `RequestSourceIP` | stringa | Indirizzo IPv4 o IPv6 del dispositivo remoto che ha avviato l'attività |
| `RequestSourcePort` | stringa | Porta di origine nel dispositivo remoto che ha avviato l'attività |
| `RequestAccountName` | stringa | Nome utente dell'account utilizzato per avviare l'attività in remoto |
| `RequestAccountDomain` | stringa | Dominio dell'account utilizzato per avviare l'attività in remoto |
| `RequestAccountSid` | stringa | Identificatore di sicurezza (SID) dell'account utilizzato per avviare in remoto l'attività |
| `ShareName` | stringa | Nome della cartella condivisa contenente il file |
| `InitiatingProcessFileSize` | long | Dimensioni del file che ha eseguito il processo responsabile dell'evento |
| `SensitivityLabel` | stringa | Etichetta applicata a un messaggio di posta elettronica, un file o altro contenuto per classificarlo per la protezione delle informazioni |
| `SensitivitySubLabel` | stringa | Sottoetichetta applicata a un messaggio di posta elettronica, un file o altro contenuto per classificarlo per la protezione delle informazioni; Le sottoetichetta di riservatezza sono raggruppate sotto le etichette di riservatezza, ma vengono trattate in modo indipendente |
| `IsAzureInfoProtectionApplied` | boolean | Indica se il file è crittografato da Azure Information Protection |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp. |
| `AppGuardContainerId` | stringa | Identificatore del contenitore virtualizzato utilizzato da Application Guard per isolare l'attività del browser |
| `AdditionalFields` | stringa | Informazioni aggiuntive sull'entità o sull'evento |
>[!NOTE]
> Le informazioni sull'hash dei file verranno sempre visualizzate quando sono disponibili. Tuttavia, esistono diversi motivi per cui non è possibile eseguire il calcolo di sha1, SHA256 o MD5. Ad esempio, il file potrebbe trovarsi in un archivio remoto, bloccato da un altro processo, compresso o contrassegnato come virtuale. In questi scenari, le informazioni sull'hash dei file vengono visualizzate vuote.

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
