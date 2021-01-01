---
title: Funzione DeviceFromIP () in Advanced Hunting for Microsoft 365 Defender
description: Informazioni su come utilizzare la funzione DeviceFromIP () per ottenere i dispositivi a cui è stato assegnato un indirizzo IP specifico
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, dispositivo, devicefromIP, funzione, arricchimento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741109"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Utilizzare la `DeviceFromIP()` funzione nelle query di [caccia avanzate](advanced-hunting-overview.md) per ottenere rapidamente l'elenco di dispositivi assegnati a un determinato indirizzo IP in un determinato momento. 

Questa funzione restituisce una tabella con le colonne seguenti:

| Colonna | Tipo di dati | Descrizione |
|------------|-------------|-------------|
| `IP` | stringa | Indirizzo IP  |
| `DeviceId` | stringa | Identificatore univoco per il dispositivo nel servizio |


## <a name="syntax"></a>Sintassi

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argomenti

Questa funzione viene richiamata come parte di una query.

- **x**: il primo parametro è in genere già una colonna della query. In questo caso, è la colonna denominata `IP` , l'indirizzo IP per il quale si desidera visualizzare un elenco di dispositivi che sono stati assegnati. Dovrebbe essere un indirizzo IP locale. Gli indirizzi IP esterni non sono supportati.
- **y**-un secondo parametro facoltativo è il `Timestamp` , che indica alla funzione di ottenere i dispositivi assegnati più recenti da un determinato intervallo di tempo. Se non specificato, la funzione restituirà i record disponibili più recenti.

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
