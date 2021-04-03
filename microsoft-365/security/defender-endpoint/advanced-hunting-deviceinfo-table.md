---
title: Tabella DeviceInfo nello schema di ricerca avanzata
description: Informazioni sul sistema operativo, sul nome del computer e su altre informazioni sul dispositivo nella tabella DeviceInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca di minacce, ricerca di minacce informatiche, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, deviceinfo, dispositivo, sistema operativo, piattaforma, utenti, DeviceInfo
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
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500825"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La tabella nello schema di ricerca avanzata contiene informazioni sui dispositivi nell'organizzazione, tra cui la versione del sistema operativo, gli utenti `DeviceInfo` attivi e il nome del computer. [](advanced-hunting-overview.md) Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

Per informazioni sulle altre tabelle nello schema di ricerca avanzata, vedere la guida di riferimento [allo schema di ricerca avanzata.](advanced-hunting-schema-reference.md)

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco del dispositivo nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo |
| `ClientVersion` | stringa | Versione dell'agente endpoint o del sensore in esecuzione nel dispositivo |
| `PublicIP` | stringa | Indirizzo IP pubblico usato dal dispositivo onboarded per connettersi al servizio Defender for Endpoint. Può trattarsi dell'indirizzo IP del dispositivo stesso, di un dispositivo NAT o di un proxy |
| `OSArchitecture` | stringa | Architettura del sistema operativo in esecuzione nel dispositivo |
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Questo indica sistemi operativi specifici, incluse le varianti all'interno della stessa famiglia, ad esempio Windows 10 e Windows 7 |
| `OSBuild` | stringa | Versione build del sistema operativo in esecuzione nel dispositivo |
| `IsAzureADJoined` | boolean | Indicatore booleano che indica se il dispositivo è aggiunto ad Azure Active Directory |
| `LoggedOnUsers` | stringa | Elenco di tutti gli utenti connessi al dispositivo al momento dell'evento in formato matrice JSON |
| `RegistryDeviceTag` | stringa | Tag dispositivo aggiunto tramite il Registro di sistema |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp |
| `OSVersion` | stringa | Versione del sistema operativo in esecuzione nel dispositivo |
| `MachineGroup` | stringa | Gruppo di computer del computer. Questo gruppo viene utilizzato dal controllo di accesso basato sui ruoli per determinare l'accesso al computer |

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprensione dello schema](advanced-hunting-schema-reference.md)
