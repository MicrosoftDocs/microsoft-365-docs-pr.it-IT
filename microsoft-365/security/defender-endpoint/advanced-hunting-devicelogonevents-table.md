---
title: Tabella DeviceLogonEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi di autenticazione o di accesso nella tabella DeviceLogonEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, devicelogonevents, autenticazione, accesso, accesso, LogonEvents
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
ms.openlocfilehash: c270f54c856c1ed504533c826ca884786c784549
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499147"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La `DeviceLogonEvents` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sugli accessi utente e altri eventi di autenticazione. Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

> [!NOTE]
> La raccolta di DeviceLogonEvents non è supportata in Windows 7 o Windows Server 2008 R2.
> Ti consigliamo di eseguire l'aggiornamento a Windows 10 o Windows Server 2019 per una visibilità ottimale dell'attività di accesso degli utenti.

Per informazioni sulle altre tabelle nello schema di ricerca avanzata, vedere la guida di riferimento [allo schema di ricerca avanzata.](advanced-hunting-schema-reference.md)

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco del dispositivo nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo |
| `ActionType` | stringa |Tipo di attività che ha attivato l'evento |
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountName` | stringa | Nome utente dell'account |
| `AccountSid` | stringa | Identificatore di sicurezza (SID) dell'account |
| `LogonType` | stringa | Tipo di sessione di accesso, in particolare:<br><br> - **Interattivo:** l'utente interagisce fisicamente con il dispositivo usando la tastiera e lo schermo locali<br><br> - **Accessi remoti interattivi (RDP):** l'utente interagisce con il dispositivo in remoto utilizzando Desktop remoto, Servizi terminal, Assistenza remota o altri client RDP<br><br> - **Rete** - Sessione avviata quando si accede al dispositivo tramite PsExec o quando si accede a risorse condivise nel dispositivo, ad esempio stampanti e cartelle condivise.<br><br> - **Batch** - Sessione avviata da attività pianificate<br><br> - **Servizio** - Sessione avviata dai servizi all'avvio<br> |
| `LogonId` | stringa | Identificatore di una sessione di accesso. Questo identificatore è univoco nello stesso dispositivo solo tra un riavvio e l'altro |
| `RemoteDeviceName` | stringa | Nome del dispositivo che ha eseguito un'operazione remota sul dispositivo interessato. A seconda dell'evento segnalato, questo nome può essere un nome di dominio completo (FQDN), un nome NetBIOS o un nome host senza informazioni sul dominio |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `RemoteIPType` | stringa | Tipo di indirizzo IP, ad esempio Public, Private, Reserved, Loopback, Teredo, FourToSixMapping e Broadcast |
| `RemotePort` | int | Porta TCP nel dispositivo remoto a cui era in corso la connessione |
| `AdditionalFields` | stringa | Informazioni aggiuntive sull'evento in formato matrice JSON |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | Identificatore di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessIntegrityLevel` | stringa | Livello di integrità del processo che ha avviato l'evento. Windows assegna livelli di integrità ai processi in base a determinate caratteristiche, ad esempio se sono stati avviati da un download Internet. Questi livelli di integrità influenzano le autorizzazioni per le risorse |
| `InitiatingProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi UAC (User Access Control) applicata al processo che ha avviato l'evento |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file di immagine) che ha avviato l'evento. Questo campo in genere non viene popolato: utilizzare la colonna SHA1 quando disponibile |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora di inizio del processo che ha avviato l'evento |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui l'elemento padre del processo responsabile dell'evento è stato avviato |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare eventi univoci, è necessario utilizzare questa colonna insieme alle `DeviceName` colonne e `Timestamp` |
| `AppGuardContainerId` | stringa | Identificatore del contenitore virtualizzato utilizzato da Application Guard per isolare l'attività del browser |
| `IsLocalAdmin` | boolean | Indicatore booleano che indica se l'utente è un amministratore locale nel dispositivo |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprensione dello schema](advanced-hunting-schema-reference.md)
