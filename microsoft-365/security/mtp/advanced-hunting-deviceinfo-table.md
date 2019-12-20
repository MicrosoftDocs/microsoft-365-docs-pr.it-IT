---
title: Tabella DeviceInfo nello schema di caccia avanzato
description: Informazioni sul sistema operativo, sul nome del computer e su altri computer nella tabella DeviceInfo dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, machineinfo, DeviceInfo, dispositivo, macchina, sistema operativo, piattaforma, utenti
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1141447de9b7ac714fb200dab56c4c2e8d75a05d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809333"
---
# <a name="deviceinfo"></a>DeviceInfo

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La `DeviceInfo` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sui computer nell'organizzazione, tra cui la versione del sistema operativo, gli utenti attivi e il nome del computer. Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ClientVersion` | stringa | Versione dell'agente endpoint o del sensore in esecuzione nel computer |
| `PublicIP` | stringa | Indirizzo IP pubblico utilizzato dal computer onboarded per la connessione al servizio ATP Microsoft Defender. Questo potrebbe essere l'indirizzo IP del computer stesso, un dispositivo NAT o un proxy |
| `OSArchitecture` | stringa | Architettura del sistema operativo in esecuzione sul computer |
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione sul computer. Questo indica sistemi operativi specifici, tra cui le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7 |
| `OSBuild` | stringa | Versione di compilazione del sistema operativo in esecuzione nel computer |
| `IsAzureADJoined` | boolean | Indicatore booleano del fatto che il computer sia aggiunto a Azure Active Directory |
| `LoggedOnUsers` | stringa | Elenco di tutti gli utenti che hanno effettuato l'accesso al computer al momento dell'evento in formato matrice JSON |
| `RegistryDeviceTag` | stringa | Tag del computer aggiunto tramite il registro di sistema |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp. |
| `OSVersion` | stringa | Versione del sistema operativo in esecuzione sul computer |
| `MachineGroup` | stringa | Gruppo di macchine del computer. Questo gruppo viene utilizzato dal controllo di accesso basato sui ruoli per determinare l'accesso al computer |

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)