---
title: Funzione AssignedIPAddresses () in Advanced Hunting for Microsoft Threat Protection
description: Informazioni su come utilizzare la funzione AssignedIPAddresses () per ottenere gli indirizzi IP più recenti assegnati a un dispositivo
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, fileprofile, profilo file, funzione, arricchimento
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 462a4884e2b17f9ae75ea3bdc1531b180dcc5934
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430128"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

Utilizzare la `AssignedIPAddresses()` funzione nelle query di [caccia avanzate](advanced-hunting-overview.md) per ottenere rapidamente gli indirizzi IP più recenti che sono stati assegnati a un dispositivo. Se si specifica un argomento timestamp, questa funzione otterrà gli indirizzi IP più recenti al momento specificato. 

Questa funzione restituisce una tabella con le colonne seguenti:

| Colonna | Tipo di dati | Descrizione |
|------------|-------------|-------------|
| `Timestamp` | datetime | Ora più recente in cui il dispositivo è stato osservato utilizzando l'indirizzo IP |
| `IPAddress` | stringa | Indirizzo IP utilizzato dal dispositivo |
| `IPType` | stringa | Indica se l'indirizzo IP è un indirizzo pubblico o privato |
| `NetworkAdapterType` | int | Tipo di scheda di rete utilizzato dal dispositivo a cui è stato assegnato l'indirizzo IP. Per i valori possibili, fare riferimento a [Questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Reti a cui è connessa la scheda con l'indirizzo IP assegnato. Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o di dominio), una descrizione e un contrassegno che indica se è connesso pubblicamente a Internet |

## <a name="syntax"></a>Sintassi

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argomenti

- **x**- `DeviceId` o `DeviceName` valore che identifica il dispositivo
- **y**- `Timestamp` valore (DateTime) che indica alla funzione di ottenere gli indirizzi IP assegnati più recenti da un determinato intervallo di tempo. Se non specificato, la funzione restituirà gli indirizzi IP più recenti.

## <a name="examples"></a>Esempi

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Ottenere l'elenco di indirizzi IP utilizzati da un dispositivo 24 ore fa

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Ottenere gli indirizzi IP utilizzati da un dispositivo e individuare i dispositivi che comunicano con esso
Questa query utilizza la `AssignedIPAddresses()` funzione per ottenere gli indirizzi IP assegnati per il dispositivo ( `example-device-name` ) in o prima di una data specifica ( `example-date` ). Vengono quindi utilizzati gli indirizzi IP per individuare le connessioni al dispositivo avviato da altri dispositivi. 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
