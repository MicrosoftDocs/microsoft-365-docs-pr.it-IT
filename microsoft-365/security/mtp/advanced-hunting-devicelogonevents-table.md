---
title: Tabella DeviceLogonEvents nello schema di caccia avanzato
description: Informazioni sugli eventi di autenticazione o di accesso nella tabella DeviceLogonEvents dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, logonevents, DeviceLogonEvents, autenticazione, accesso, accedi
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
ms.openlocfilehash: 07b2c2301784f378075e3c9803cebc5bcabf9cb0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899268"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

**Si applica a:**
- Microsoft Threat Protection



La `DeviceLogonEvents` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli accessi degli utenti e altri eventi di autenticazione. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ActionType` | stringa |Tipo di attività che ha attivato l'evento |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountSid` | stringa | ID di sicurezza (SID) dell'account |
| `LogonType` | stringa | Tipo di sessione di accesso, in particolare:<br><br> - **Interattivo** -utente interagisce fisicamente con il computer utilizzando la tastiera e lo schermo locali<br><br> - **Accessi Remote interattivi (RDP)** -l'utente interagisce con il computer in remoto tramite Desktop remoto, Servizi terminal, assistenza remota o altri client RDP<br><br> - La sessione di **rete** è stata avviata quando si accede al computer tramite PsExec o quando si accede a risorse condivise nel computer, ad esempio stampanti e cartelle condivise.<br><br> - Sessione **batch** iniziata dalle attività pianificate<br><br> - Sessione di **servizio** avviata dai servizi all'avvio<br> |
| `LogonId` | stringa | Identificatore per una sessione di accesso. Questo identificatore è univoco nello stesso computer solo tra i riavvii |
| `RemoteDeviceName` | stringa | Nome del computer in cui è stata eseguita un'operazione remota sul computer in questione. A seconda dell'evento segnalato, questo nome potrebbe essere un nome di dominio completo (FQDN), un nome NetBIOS o un nome host senza informazioni sul dominio. |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `RemoteIPType` | stringa | Tipo di indirizzo IP, ad esempio pubblico, privato, riservato, loopback, Teredo, FourToSixMapping e broadcast |
| `RemotePort` | int | Porta TCP sul dispositivo remoto connesso a |
| `AdditionalFields` | stringa | Ulteriori informazioni sull'evento nel formato di matrice JSON |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | ID di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessIntegrityLevel` | stringa | Livello di integrità del processo che ha avviato l'evento. Windows assegna livelli di integrità ai processi basati su determinate caratteristiche, ad esempio se sono stati avviati da un download Internet. Tali livelli di integrità influiscono sulle autorizzazioni per le risorse |
| `InitiatingProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi di controllo di accesso utente applicato al processo che ha avviato l'evento |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file di immagine) che ha avviato l'evento. Questo campo in genere non viene popolato, se disponibile, utilizzare la colonna SHA1 |
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
| `IsLocalAdmin` | boolean | Indicatore booleano che indica se l'utente è un amministratore locale del computer |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
