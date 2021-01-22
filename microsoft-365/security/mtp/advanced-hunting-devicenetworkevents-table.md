---
title: Tabella DeviceNetworkEvents nello schema di ricerca avanzata
description: Informazioni sugli eventi di connessione di rete su cui è possibile eseguire query dalla tabella DeviceNetworkEvents dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, devicenetworkevents, NetworkCommunicationEvents, connessione di rete, ip remoto, ip locale
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0ed696f36737a4102895369e1254b4215cad4def
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931219"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La `DeviceNetworkEvents` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sulle connessioni di rete e sugli eventi correlati. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

>[!TIP]
> Per informazioni dettagliate sui tipi di eventi (valori) supportati da una tabella, utilizzare il riferimento allo schema predefinito `ActionType` disponibile nel Centro sicurezza. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ActionType` | stringa | Tipo di attività che ha attivato l'evento. Per informazioni [dettagliate, vedere le informazioni di riferimento](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) sullo schema nel portale |
| `RemoteIP` | stringa | Indirizzo IP connesso a |
| `RemotePort` | int | Porta TCP nel dispositivo remoto a cui era in corso la connessione |
| `RemoteUrl` | stringa | URL o nome di dominio completo (FQDN) connesso a |
| `LocalIP` | stringa | Indirizzo IP assegnato al computer locale utilizzato durante la comunicazione |
| `LocalPort` | int | Porta TCP sul computer locale utilizzata durante la comunicazione |
| `Protocol` | stringa | Protocollo utilizzato durante la comunicazione |
| `LocalIPType` | stringa | Tipo di indirizzo IP, ad esempio Public, Private, Reserved, Loopback, Teredo, FourToSixMapping e Broadcast |
| `RemoteIPType` | stringa | Tipo di indirizzo IP, ad esempio Public, Private, Reserved, Loopback, Teredo, FourToSixMapping e Broadcast |
| `InitiatingProcessSHA1` | stringa | SHA-1 del processo (file immagine) che ha avviato l'evento |
| `InitiatingProcessSHA256` | stringa | SHA-256 del processo (file immagine) che ha avviato l'evento. (questo campo in genere non viene popolato: usare la colonna SHA1, se disponibile). |
| `InitiatingProcessMD5` | stringa | Hash MD5 del processo (file immagine) che ha avviato l'evento |
| `InitiatingProcessFileName` | stringa | Nome del processo che ha avviato l'evento |
| `InitiatingProcessId` | int | ID processo (PID) del processo che ha avviato l'evento |
| `InitiatingProcessCommandLine` | stringa | Riga di comando utilizzata per eseguire il processo che ha avviato l'evento |
| `InitiatingProcessCreationTime` | datetime | Data e ora di inizio del processo che ha avviato l'evento |
| `InitiatingProcessFolderPath` | stringa | Cartella contenente il processo (file immagine) che ha avviato l'evento |
| `InitiatingProcessParentFileName` | stringa | Nome del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentId` | int | ID processo (PID) del processo padre che ha generato il processo responsabile dell'evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e ora in cui è stato avviato l'elemento padre del processo responsabile dell'evento |
| `InitiatingProcessAccountDomain` | stringa | Dominio dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountName` | stringa | Nome utente dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessAccountSid` | stringa | Identificatore di sicurezza (SID) dell'account che ha eseguito il processo responsabile dell'evento |
| `InitiatingProcessIntegrityLevel` | stringa | Livello di integrità del processo che ha avviato l'evento. Windows assegna livelli di integrità ai processi in base a determinate caratteristiche, ad esempio se sono stati avviati da un download Internet. Questi livelli di integrità influenzano le autorizzazioni per le risorse |
| `InitiatingProcessTokenElevation` | stringa | Tipo di token che indica la presenza o l'assenza dell'elevazione dei privilegi del controllo di accesso utente applicata al processo che ha avviato l'evento |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare eventi univoci, questa colonna deve essere usata insieme alle colonne DeviceName e Timestamp |
| `AppGuardContainerId` | stringa | Identificatore del contenitore virtualizzato usato da Application Guard per isolare l'attività del browser |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
