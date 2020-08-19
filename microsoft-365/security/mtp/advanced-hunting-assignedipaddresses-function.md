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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794232"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Utilizzare la `AssignedIPAddresses()` funzione per ottenere rapidamente gli indirizzi IP più recenti che sono stati assegnati a un dispositivo o gli indirizzi IP più recenti da un determinato momento. Questa funzione restituisce una tabella con le colonne seguenti:

| Colonna | Tipo di dati | Descrizione |
|------------|-------------|-------------|
| Timestamp | datetime | Ora più recente in cui il dispositivo è stato osservato utilizzando l'indirizzo IP |
| IPAddress | stringa | Indirizzo IP utilizzato dal dispositivo |
| IPType | stringa | Indica se l'indirizzo IP è un indirizzo pubblico o privato |
| NetworkAdapterType | int | Tipo di scheda di rete utilizzato dal dispositivo a cui è stato assegnato l'indirizzo IP. Per i valori possibili, fare riferimento a [Questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)  |
| ConnectedNetworks | int | Reti a cui è connessa la scheda con l'indirizzo IP assegnato. Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o di dominio), una descrizione e un contrassegno che indica se è connesso pubblicamente a Internet |


## <a name="syntax"></a>Sintassi

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argomenti

- **x** - `DeviceId` o `DeviceName` valore che identifica il dispositivo
- **y** - `Timestamp` (DateTime) valore che indica il momento specifico in cui ottenere gli indirizzi IP più recenti. Se non specificato, la funzione restituirà gli indirizzi IP più recenti.

## <a name="examples"></a>Esempi

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a>Ottenere l'elenco di indirizzi IP utilizzati da un dispositivo fino a 24 ore fa

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