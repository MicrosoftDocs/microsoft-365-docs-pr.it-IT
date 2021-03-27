---
title: Tabella DeviceLogonEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi di autenticazione o di accesso nella tabella DeviceLogonEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft Threat Protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, logonevents, DeviceLogonEvents, autenticazione, accesso, accesso
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
ms.openlocfilehash: e1d1284fa6132e37b31245bd45557e180d0135f2
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382674"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La `DeviceLogonEvents` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sugli accessi utente e altri eventi di autenticazione nei dispositivi. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ActionType` | stringa |Tipo di attività che ha attivato l'evento |
| `LogonType` | stringa | Tipo di sessione di accesso, in particolare:<br><br> - **Interattivo-** L'utente interagisce fisicamente con il computer usando la tastiera e lo schermo locali<br><br> - **Accessi remoti interattivi (RDP):** l'utente interagisce con il computer in remoto utilizzando Desktop remoto, Servizi terminal, Assistenza remota o altri client RDP<br><br> - **Rete** - Sessione avviata quando si accede al computer tramite PsExec o quando si accede a risorse condivise nel computer, ad esempio stampanti e cartelle condivise.<br><br> - **Batch** - Sessione avviata da attività pianificate<br><br> - **Servizio** - Sessione avviata dai servizi all'avvio<br> |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountSid` | stringa | Identificatore di sicurezza (SID) dell'account |
| `Protocol` | stringa | Protocollo utilizzato durante la comunicazione |
| `FailureReason` | stringa | Informazioni che spiegano perché l'azione registrata non è riuscita |
| `IsLocalAdmin` | boolean | Indicatore booleano che indica se l'utente è un amministratore locale nel computer |
| `LogonId` | stringa | Identificatore di una sessione di accesso. Questo identificatore è univoco nello stesso computer solo tra un riavvio e l'altro |
| `RemoteDeviceName` | stringa | Nome del computer che ha eseguito un'operazione remota nel computer interessato. A seconda dell'evento segnalato, questo nome può essere un nome di dominio completo (FQDN), un nome NetBIOS o un nome host senza informazioni sul dominio |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `RemoteIPType` | stringa | Tipo di indirizzo IP, ad esempio Public, Private, Reserved, Loopback, Teredo, FourToSixMapping e Broadcast |
| `RemotePort` | int | Porta TCP nel dispositivo remoto a cui era in corso la connessione |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | Identificatore di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountUpn` | stringa | Nome dell'entità utente (UPN) dell'account che ha eseguito il processo responsabile dell'evento |
| ` InitiatingProcessAccountObjectId` | stringa | ID oggetto di Azure AD dell'account utente che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessIntegrityLevel` | stringa | Livello di integrità del processo che ha avviato l'evento. Windows assegna livelli di integrità ai processi in base a determinate caratteristiche, ad esempio se sono stati avviati da un download Internet. Questi livelli di integrità influenzano le autorizzazioni per le risorse |
| `InitiatingProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi UAC (User Access Control) applicata al processo che ha avviato l'evento |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file di immagine) che ha avviato l'evento. Questo campo in genere non viene popolato: utilizzare la colonna SHA1 quando disponibile |
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
