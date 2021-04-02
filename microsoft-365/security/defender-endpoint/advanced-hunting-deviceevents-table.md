---
title: Tabella DeviceEvents nello schema di ricerca avanzata
description: Informazioni su antivirus, firewall e altri tipi di eventi nella tabella eventi di dispositivo vari (DeviceEvents) dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, eventi di sicurezza, antivirus, firewall, exploit guard, MiscEvents
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
ms.openlocfilehash: 1e67da3a5d93c5e8c86afd755c882f3f0459aab0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499194"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La tabella o gli eventi vari del dispositivo nello schema di ricerca avanzata contengono informazioni su vari tipi di eventi, inclusi gli eventi attivati dai controlli di sicurezza, ad esempio Microsoft Defender Antivirus e la `DeviceEvents` protezione dagli exploit. [](advanced-hunting-overview.md) Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

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
| `AccountDomain` | stringa | Dominio dell'account |
| `AccountName` |stringa | Nome utente dell'account |
| `AccountSid` | stringa | Identificatore di sicurezza (SID) dell'account |
| `RemoteUrl` | stringa | URL o nome di dominio completo (FQDN) connesso a |
| `RemoteDeviceName` | stringa | Nome del dispositivo che ha eseguito un'operazione remota sul dispositivo interessato. A seconda dell'evento segnalato, questo nome può essere un nome di dominio completo (FQDN), un nome NetBIOS o un nome host senza informazioni sul dominio |
| `ProcessId` | int | ID processo (PID) del processo appena creato |
| `ProcessCommandLine` | stringa | Riga di comando utilizzata per creare il nuovo processo |
| `ProcessCreationTime` | datetime | Data e ora di creazione del processo |
| `ProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi UAC (User Access Control) applicata al processo appena creato |
| `LogonId` | stringa | Identificatore di una sessione di accesso. Questo identificatore è univoco nello stesso dispositivo solo tra un riavvio e l'altro |
| `RegistryKey` | stringa | Chiave del Registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueName` | stringa | Nome del valore del Registro di sistema a cui è stata applicata l'azione registrata |
| `RegistryValueData` | stringa | Dati del valore del Registro di sistema a cui è stata applicata l'azione registrata |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `RemotePort` | int | Porta TCP nel dispositivo remoto a cui era in corso la connessione |
| `LocalIP` | stringa | Indirizzo IP assegnato al dispositivo locale utilizzato durante la comunicazione |
| `LocalPort` | int | Porta TCP nel dispositivo locale utilizzato durante la comunicazione |
| `FileOriginUrl` | stringa | URL da cui è stato scaricato il file |
| `FileOriginIP` | stringa | Indirizzo IP da cui è stato scaricato il file |
| `AdditionalFields` | stringa | Informazioni aggiuntive sull'evento in formato matrice JSON |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file di immagine) che ha avviato l'evento. Questo campo in genere non viene popolato: utilizzare la colonna SHA1 quando disponibile |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora di inizio del processo che ha avviato l'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui l'elemento padre del processo responsabile dell'evento è stato avviato |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file di immagine) che ha avviato l'evento |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | Identificatore di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessLogonId` | stringa | Identificatore per una sessione di accesso del processo che ha avviato l'evento. Questo identificatore è univoco nello stesso dispositivo solo tra un riavvio e l'altro |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare eventi univoci, è necessario utilizzare questa colonna insieme alle `DeviceName` colonne e `Timestamp` |
| `AppGuardContainerId` | stringa | Identificatore del contenitore virtualizzato utilizzato da Application Guard per isolare l'attività del browser |


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprensione dello schema](advanced-hunting-schema-reference.md)
