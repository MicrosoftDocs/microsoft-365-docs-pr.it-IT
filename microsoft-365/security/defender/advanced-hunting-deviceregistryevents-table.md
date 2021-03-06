---
title: Tabella DeviceRegistryEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi del Registro di sistema su cui è possibile eseguire query dalla tabella DeviceRegistryEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, registryevents, Registro di sistema, DeviceRegistryEvents, chiave, sottochiave, valore
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
ms.openlocfilehash: 0eef71a7ab88d24c1f9d0b3ebdba16b13c855355
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024260"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender
- Microsoft Defender per endpoint

La tabella nello schema di ricerca avanzata contiene informazioni sulla creazione e la `DeviceRegistryEvents` modifica delle voci del Registro di sistema. [](advanced-hunting-overview.md) Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento. Per informazioni [dettagliate, vedere](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) informazioni di riferimento sullo schema nel portale |
| `RegistryKey` | stringa | Chiave del Registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueType` | stringa | Tipo di dati, ad esempio binario o stringa, del valore del Registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueName` | stringa | Nome del valore del Registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueData` | stringa | Dati del valore del Registro di sistema a cui è stata applicata l'azione registrata |
| `PreviousRegistryKey` | stringa | Chiave del Registro di sistema originale del valore del Registro di sistema prima della modifica |
| `PreviousRegistryValueName` | stringa | Nome originale del valore del Registro di sistema prima della modifica |
| `PreviousRegistryValueData` | stringa | Dati originali del valore del Registro di sistema prima della modifica |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | Identificatore di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountObjectId` | stringa | ID oggetto di Azure AD dell'account utente che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file di immagine) che ha avviato l'evento. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessFileSize` | long | Dimensioni del file che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessVersionInfoCompanyName` | stringa | Nome della società dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
| `InitiatingProcessVersionInfoProductName` | stringa | Nome del prodotto dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
|` InitiatingProcessVersionInfoProductVersion` | stringa | Versione del prodotto dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
|` InitiatingProcessVersionInfoInternalFileName` | stringa | Nome file interno dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
| `InitiatingProcessVersionInfoOriginalFileName` | stringa | Nome del file originale dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
| `InitiatingProcessVersionInfoFileDescription` | stringa | Descrizione dalle informazioni sulla versione del processo (file immagine) responsabile dell'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora di inizio del processo che ha avviato l'evento |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui l'elemento padre del processo responsabile dell'evento è stato avviato |
| `InitiatingProcessIntegrityLevel` | stringa | Livello di integrità del processo che ha avviato l'evento. Windows i livelli di integrità ai processi in base a determinate caratteristiche, ad esempio se sono stati avviati da un download Internet. Questi livelli di integrità influenzano le autorizzazioni per le risorse |
| `InitiatingProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi UAC (User Access Control) applicata al processo che ha avviato l'evento |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp |
| `AppGuardContainerId` | stringa | Identificatore del contenitore virtualizzato utilizzato da Application Guard per isolare l'attività del browser |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
