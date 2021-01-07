---
title: Tabella DeviceFileEvents nello schema di caccia avanzato
description: Informazioni sugli eventi correlati ai file nella tabella DeviceFileEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento dello schema, kusto, tabella, colonna, tipo di dati, descrizione, filecreationevents, DeviceFileEvents, file, percorso, hash, SHA1, SHA256, MD5
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
ms.openlocfilehash: 9b48321693f883e40a100e29e5e1ec3c5203caa2
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771860"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La `DeviceFileEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulla creazione, la modifica e altri eventi del file System. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi ( `ActionType` valori) supportati da una tabella, utilizzare la Guida di [riferimento allo schema incorporata](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponibile nel centro sicurezza.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento. Per informazioni dettagliate, vedere la Guida [di riferimento allo schema in-Portal.](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `FileName` | stringa | Nome del file a cui è stata applicata l'azione registrata |
| `FolderPath` | stringa | Cartella contenente il file a cui è stata applicata l'azione registrata |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `SHA256` | stringa | SHA-256 del file a cui è stata applicata l'azione registrata. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `MD5` | stringa | Hash MD5 del file a cui è stata applicata l'azione registrata |
| `FileOriginUrl` | stringa | URL da cui è stato scaricato il file |
| `FileOriginReferrerUrl` | stringa | URL della pagina Web che collega al file scaricato |
| `FileOriginIP` | stringa | Indirizzo IP da cui è stato scaricato il file |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | ID di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file di immagine) che ha avviato l'evento. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora in cui è stato avviato il processo che ha avviato l'evento |
| `InitiatingProcessIntegrityLevel` | stringa | Livello di integrità del processo che ha avviato l'evento. Windows assegna livelli di integrità ai processi basati su determinate caratteristiche, ad esempio se sono stati avviati da un download Internet. Tali livelli di integrità influiscono sulle autorizzazioni per le risorse |
| `InitiatingProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi di controllo di accesso utente applicato al processo che ha avviato l'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui è stato avviato l'elemento padre del processo responsabile dell'evento |
| `RequestProtocol` | stringa | Protocollo di rete, se applicabile, utilizzato per avviare l'attività: Unknown, local, SMB o NFS |
| `ShareName` | stringa | Nome della cartella condivisa che contiene il file |
| `RequestSourceIP` | stringa | Indirizzo IPv4 o IPv6 del dispositivo remoto che ha avviato l'attività |
| `RequestSourcePort` | stringa | Porta di origine nel dispositivo remoto che ha avviato l'attività |
| `RequestAccountName` | stringa | Nome utente dell'account utilizzato per avviare l'attività in remoto |
| `RequestAccountDomain` | stringa | Dominio dell'account utilizzato per avviare l'attività in remoto |
| `RequestAccountSid` | stringa | ID di sicurezza (SID) dell'account utilizzato per avviare l'attività in remoto |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp. |
| `AppGuardContainerId` | stringa | Identificatore per il contenitore virtualizzato utilizzato dalla protezione dell'applicazione per isolare l'attività del browser |
| `SensitivityLabel` | stringa | Etichetta applicata a un messaggio di posta elettronica, un file o un altro contenuto per classificarlo per la protezione delle informazioni |
| `SensitivitySubLabel` | stringa | Sottoetichetta applicata a un messaggio di posta elettronica, un file o un altro contenuto per classificarlo per la protezione delle informazioni; le sottoetichette di sensitivity sono raggruppate in etichette di riservatezza, ma vengono trattate in modo indipendente |
| `IsAzureInfoProtectionApplied` | boolean | Indica se il file è crittografato con Azure Information Protection |

>[!NOTE]
> Le informazioni sull'hash del file vengono sempre visualizzate quando è disponibile. Tuttavia, esistono diversi possibili motivi per cui non è possibile calcolare un SHA1, SHA256 o MD5. Ad esempio, il file potrebbe trovarsi in uno spazio di archiviazione remoto, bloccato da un altro processo, compresso o contrassegnato come virtuale. In questi scenari, le informazioni sull'hash dei file vengono visualizzate come vuote.

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
