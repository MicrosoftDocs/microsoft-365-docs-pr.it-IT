---
title: Tabella DeviceProcessEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi di generazione o creazione del processo nella classe DeviceProcessEventstable dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft Threat Protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, processcreationevents, DeviceProcessEvents, ID processo, riga di comando, DeviceProcessEvents
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 363d80431c14bc550cba34850c85593163aea1b1
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382842"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La `DeviceProcessEvents` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sulla creazione di processi e sugli eventi correlati. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

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
| `FileSize` | long | Dimensioni del file in byte |
| `ProcessVersionInfoCompanyName` | stringa | Nome della società dalle informazioni sulla versione del processo appena creato |
| `ProcessVersionInfoProductName` | stringa | Nome del prodotto dalle informazioni sulla versione del processo appena creato |
| `ProcessVersionInfoProductVersion` | stringa | Versione del prodotto dalle informazioni sulla versione del processo appena creato |
| `ProcessVersionInfoInternalFileName` | stringa | Nome file interno dalle informazioni sulla versione del processo appena creato |
| `ProcessVersionInfoOriginalFileName` | stringa | Nome del file originale dalle informazioni sulla versione del processo appena creato |
| `ProcessVersionInfoFileDescription` | stringa | Descrizione dalle informazioni sulla versione del processo appena creato |
| `ProcessId` | int | ID processo (PID) del processo appena creato |
| `ProcessCommandLine` | stringa | Riga di comando utilizzata per creare il nuovo processo |
| `ProcessIntegrityLevel` | stringa | Livello di integrità del processo appena creato. Windows assegna livelli di integrità ai processi in base a determinate caratteristiche, ad esempio se sono stati avviati da internet scaricati. Questi livelli di integrità influenzano le autorizzazioni per le risorse |
| `ProcessTokenElevation` | stringa | Indica il tipo di elevazione dei token applicata al processo appena creato. Valori possibili: TokenElevationTypeLimited (con restrizioni), TokenElevationTypeDefault (standard) e TokenElevationTypeFull (con privilegi elevati) |
| `ProcessCreationTime` | datetime | Data e ora di creazione del processo |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountSid` | stringa | Identificatore di sicurezza (SID) dell'account |
| `AccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account |
| `AccountObjectId` | stringa | Identificatore univoco dell'account in Azure AD |
| `LogonId` | stringa | Identificatore di una sessione di accesso. Questo identificatore è univoco nello stesso computer solo tra un riavvio e l'altro |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | Identificatore di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountObjectId` | stringa | ID oggetto di Azure AD dell'account utente che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessLogonId` | stringa | Identificatore per una sessione di accesso del processo che ha avviato l'evento. Questo identificatore è univoco nello stesso computer solo tra un riavvio e l'altro. |
| `InitiatingProcessIntegrityLevel` | stringa | Livello di integrità del processo che ha avviato l'evento. Windows assegna livelli di integrità ai processi in base a determinate caratteristiche, ad esempio se sono stati avviati da un download Internet. Questi livelli di integrità influenzano le autorizzazioni per le risorse |
| `InitiatingProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi UAC (User Access Control) applicata al processo che ha avviato l'evento |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file di immagine) che ha avviato l'evento. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessFileSize` | long | Dimensioni del file che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessVersionInfoCompanyName` | stringa | Nome della società dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
| `InitiatingProcessVersionInfoProductName` | stringa | Nome del prodotto dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
| `InitiatingProcessVersionInfoProductVersion` | stringa | Versione del prodotto dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
| `InitiatingProcessVersionInfoInternalFileName` | stringa | Nome file interno dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
| `InitiatingProcessVersionInfoOriginalFileName` | stringa | Nome del file originale dalle informazioni sulla versione del processo (file di immagine) responsabile dell'evento |
| `InitiatingProcessVersionInfoFileDescription` | stringa | Descrizione dalle informazioni sulla versione del processo (file immagine) responsabile dell'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora di inizio del processo che ha avviato l'evento |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui l'elemento padre del processo responsabile dell'evento è stato avviato |
| `InitiatingProcessSignerType` | stringa | Tipo di firmatario del processo (file immagine) che ha avviato l'evento |
| `InitiatingProcessSignatureStatus` | stringa | Informazioni sullo stato della firma del processo (file di immagine) che ha avviato l'evento |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp |
| `AppGuardContainerId` | stringa | Identificatore del contenitore virtualizzato utilizzato da Application Guard per isolare l'attività del browser |
| `AdditionalFields` | stringa | Informazioni aggiuntive sull'evento in formato matrice JSON |


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
