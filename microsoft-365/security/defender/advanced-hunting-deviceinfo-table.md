---
title: Tabella DeviceInfo nello schema di ricerca avanzata
description: Informazioni sul sistema operativo, sul nome del computer e su altre informazioni sul computer nella tabella DeviceInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, machineinfo, DeviceInfo, dispositivo, computer, sistema operativo, piattaforma, utenti
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
ms.openlocfilehash: b5baf4adf9c9abaf746c1d6c3ea1c29c3b471b0b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498594"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La tabella nello schema di ricerca avanzata contiene informazioni sui dispositivi nell'organizzazione, tra cui la versione del sistema operativo, gli utenti `DeviceInfo` attivi e il nome del computer. [](advanced-hunting-overview.md) Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `ClientVersion` | stringa | Versione dell'agente endpoint o del sensore in esecuzione nel computer |
| `PublicIP` | stringa | Indirizzo IP pubblico utilizzato dal computer onboarded per connettersi al servizio Microsoft Defender for Endpoint. Può trattarsi dell'indirizzo IP del computer stesso, di un dispositivo NAT o di un proxy |
| `OSArchitecture` | stringa | Architettura del sistema operativo in esecuzione sul computer |
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione sul computer. Questo indica sistemi operativi specifici, incluse le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7 |
| `OSBuild` | stringa | Versione build del sistema operativo in esecuzione nel computer |
| `IsAzureADJoined` | boolean | Indicatore booleano che indica se il computer è aggiunto ad Azure Active Directory |
| `AadObjectId` | stringa | Identificatore univoco per il dispositivo in Azure AD |
| `LoggedOnUsers` | stringa | Elenco di tutti gli utenti connessi al computer al momento dell'evento in formato matrice JSON |
| `RegistryDeviceTag` | stringa | Tag computer aggiunto tramite il Registro di sistema |
| `OSVersion` | stringa | Versione del sistema operativo in esecuzione sul computer |
| `MachineGroup` | stringa | Gruppo di computer del computer. Questo gruppo viene utilizzato dal controllo di accesso basato sui ruoli per determinare l'accesso al computer |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp |
|`AdditionalFields` | stringa | Informazioni aggiuntive sull'evento in formato matrice JSON |

La `DeviceInfo` tabella fornisce informazioni sul dispositivo in base agli heartbeat, ovvero report periodici o segnali provenienti da un dispositivo. Ogni quindici minuti, il dispositivo invia un heartbeat parziale che contiene attributi che cambiano frequentemente, ad esempio `LoggedOnUsers` . Una volta al giorno, viene inviato un heartbeat completo contenente gli attributi del dispositivo.

Puoi usare la query di esempio seguente per ottenere lo stato più recente di un dispositivo:

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
