---
title: Tabella DeviceRegistryEvents nello schema di caccia avanzato
description: Informazioni sugli eventi del registro di sistema che è possibile eseguire una query dalla tabella DeviceRegistryEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento dello schema, kusto, tabella, colonna, tipo di dati, registryevents, registro di sistema, DeviceRegistryEvents, chiave, sottochiave, valore
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
ms.openlocfilehash: 5d43584ed9af9a0ac6154d593f4517d0a4152023
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087965"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La `DeviceRegistryEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sulla creazione e la modifica delle voci del registro di sistema. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento |
| `RegistryKey` | stringa | Chiave del registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueType` | stringa | Tipo di dati, ad esempio binario o stringa, del valore del registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueName` | stringa | Nome del valore del registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueData` | stringa | Dati del valore del registro di sistema a cui è stata applicata l'azione registrata |
| `PreviousRegistryValueName` | stringa | Nome originale del valore del registro di sistema prima che sia stato modificato |
| `PreviousRegistryValueData` | stringa | Dati originali del valore del registro di sistema prima che venissero modificati |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | ID di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora in cui è stato avviato il processo che ha avviato l'evento |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui è stato avviato l'elemento padre del processo responsabile dell'evento |
| `InitiatingProcessIntegrityLevel` | stringa | Livello di integrità del processo che ha avviato l'evento. Windows assegna livelli di integrità ai processi basati su determinate caratteristiche, ad esempio se sono stati avviati da un download Internet. Tali livelli di integrità influiscono sulle autorizzazioni per le risorse |
| `InitiatingProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi di controllo di accesso utente applicato al processo che ha avviato l'evento |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp. |
| `AppGuardContainerId` | stringa | Identificatore per il contenitore virtualizzato utilizzato dalla protezione dell'applicazione per isolare l'attività del browser |

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
