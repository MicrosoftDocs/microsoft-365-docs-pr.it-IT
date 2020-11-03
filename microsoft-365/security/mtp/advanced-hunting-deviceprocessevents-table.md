---
title: Tabella DeviceProcessEvents nello schema di caccia avanzato
description: Informazioni sugli eventi di creazione o di generazione dei processi nell'DeviceProcessEventstable dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento dello schema, kusto, tabella, colonna, tipo di dati, processcreationevents, DeviceProcessEvents, ID processo, riga di comando, DeviceProcessEvents
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
ms.openlocfilehash: 491dae64e70ca7bb70a7682992bafd46c1d06c72
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846917"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La `DeviceProcessEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulla creazione dei processi e sugli eventi correlati. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

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
| `ProcessId` | int | ID processo (PID) del processo appena creato |
| `ProcessCommandLine` | stringa | Riga di comando utilizzata per creare il nuovo processo |
| `ProcessIntegrityLevel` | stringa | Livello di integrità del processo appena creato. Windows assegna livelli di integrità ai processi basati su determinate caratteristiche, ad esempio se sono stati avviati da un download di Internet. Tali livelli di integrità influiscono sulle autorizzazioni per le risorse |
| `ProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi del controllo di accesso utente applicato al processo appena creato |
| `ProcessCreationTime` | datetime | Data e ora in cui è stato creato il processo |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountSid` | stringa | ID di sicurezza (SID) dell'account |
| `LogonId` | stringa | Identificatore per una sessione di accesso. Questo identificatore è univoco nello stesso computer solo tra i riavvii |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | ID di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessLogonId` | stringa | Identificatore per una sessione di accesso del processo che ha avviato l'evento. Questo identificatore è univoco nello stesso computer solo tra i riavvii. |
| `InitiatingProcessIntegrityLevel` | stringa | Livello di integrità del processo che ha avviato l'evento. Windows assegna livelli di integrità ai processi basati su determinate caratteristiche, ad esempio se sono stati avviati da un download Internet. Tali livelli di integrità influiscono sulle autorizzazioni per le risorse |
| `InitiatingProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi di controllo di accesso utente applicato al processo che ha avviato l'evento |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file di immagine) che ha avviato l'evento. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora in cui è stato avviato il processo che ha avviato l'evento |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui è stato avviato l'elemento padre del processo responsabile dell'evento |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp. |
| `AppGuardContainerId` | stringa | Identificatore per il contenitore virtualizzato utilizzato dalla protezione dell'applicazione per isolare l'attività del browser |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
