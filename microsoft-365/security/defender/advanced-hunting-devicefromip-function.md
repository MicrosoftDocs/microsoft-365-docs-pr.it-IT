---
title: Funzione DeviceFromIP() nella ricerca avanzata per Microsoft 365 Defender
description: Informazioni su come usare la funzione DeviceFromIP() per ottenere i dispositivi a cui è stato assegnato un indirizzo IP specifico
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, dispositivo, devicefromIP, funzione, arricchimento
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
ms.openlocfilehash: d2996021a84186adc6656927dbdc910db4d037de
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063533"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Usa la funzione nelle query di ricerca avanzate per ottenere rapidamente l'elenco dei dispositivi assegnati a un determinato indirizzo `DeviceFromIP()` IP in un determinato momento. [](advanced-hunting-overview.md) 

Questa funzione restituisce una tabella con le colonne seguenti:

| Colonna | Tipo di dati | Descrizione |
|------------|-------------|-------------|
| `IP` | stringa | Indirizzo IP  |
| `DeviceId` | stringa | Identificatore univoco del dispositivo nel servizio |


## <a name="syntax"></a>Sintassi

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argomenti

Questa funzione viene richiamata come parte di una query.

- **x**: il primo parametro è in genere già una colonna nella query. In questo caso, è la colonna denominata , l'indirizzo IP per il quale si desidera visualizzare un elenco dei dispositivi a cui è `IP` stato assegnato. Deve essere un indirizzo IP locale. Gli indirizzi IP esterni non sono supportati.
- **y**- Un secondo parametro facoltativo è , che indica alla funzione di ottenere i dispositivi assegnati più recenti `Timestamp` da un momento specifico. Se non viene specificato, la funzione restituisce gli ultimi record disponibili.

## <a name="example"></a>Esempio


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Ottenere i dispositivi più recenti a cui sono stati assegnati indirizzi IP specifici

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
