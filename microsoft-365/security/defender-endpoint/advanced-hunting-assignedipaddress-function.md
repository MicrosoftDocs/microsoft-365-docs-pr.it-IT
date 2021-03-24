---
title: Funzione AssignedIPAddresses() nella ricerca avanzata di Microsoft Defender per Endpoint
description: Informazioni su come usare la funzione AssignedIPAddresses() per ottenere gli indirizzi IP più recenti assegnati a un dispositivo
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection, ricerca, query, telemetria, riferimento allo schema, kusto, FileProfile, profilo file, funzione, arricchimento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 08ab7ff5bac917a027e4380a46ab1cb2cf0a1312
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064397"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Usa la funzione nelle query di ricerca avanzate per ottenere rapidamente gli indirizzi IP più recenti assegnati `AssignedIPAddresses()` a un dispositivo. Se si specifica un argomento timestamp, questa funzione ottiene gli indirizzi IP più recenti al momento specificato.

Questa funzione restituisce una tabella con le colonne seguenti:

Colonna | Tipo di dati | Descrizione
-|-|-
`Timestamp` | datetime | Ora dell'ultima volta in cui il dispositivo è stato osservato usando l'indirizzo IP
`IPAddress` | stringa | Indirizzo IP utilizzato dal dispositivo
`IPType` | stringa | Indica se l'indirizzo IP è pubblico o privato
`NetworkAdapterType` | int | Tipo di scheda di rete utilizzata dal dispositivo a cui è stato assegnato l'indirizzo IP. Per i valori possibili, fare riferimento a [questa enumerazione](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)
`ConnectedNetworks` | int | Reti a cui è connessa la scheda con l'indirizzo IP assegnato. Ogni matrice JSON contiene il nome di rete, la categoria (pubblico, privato o dominio), una descrizione e un flag che indica se è connesso pubblicamente a Internet

## <a name="syntax"></a>Sintassi

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argomenti

- **x**— `DeviceId` o valore che identifica il `DeviceName` dispositivo
- **y**— Valore (datetime) che indica alla funzione di ottenere gli indirizzi IP assegnati più di recente `Timestamp` da un'ora specifica. Se non specificato, la funzione restituisce gli indirizzi IP più recenti.

## <a name="examples"></a>Esempi

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Ottenere l'elenco degli indirizzi IP usati da un dispositivo 24 ore fa

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Ottenere gli indirizzi IP usati da un dispositivo e trovare i dispositivi che comunicano con esso

Questa query utilizza la funzione per ottenere gli indirizzi IP assegnati per il dispositivo ( ) in una data specifica o prima `AssignedIPAddresses()` `example-device-name` di ( `example-date` ). Usa quindi gli indirizzi IP per trovare le connessioni al dispositivo avviate da altri dispositivi. 

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
- [Comprensione dello schema](advanced-hunting-schema-reference.md)
