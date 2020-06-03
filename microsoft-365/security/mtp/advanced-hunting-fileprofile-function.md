---
title: Funzione fileprofile () in Advanced Hunting for Microsoft Threat Protection
description: Informazioni su come utilizzare il fileprofile () per arricchire i dati dei file nei risultati della query di ricerca avanzata
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
ms.openlocfilehash: 039b9dc038cd1a1645aee2289f3bdb389eb3f426
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515925"
---
# <a name="fileprofile"></a>Fileprofile ()

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La `FileProfile()` funzione è una funzione di arricchimento nella [ricerca avanzata](advanced-hunting-overview.md) che consente di aggiungere i dati seguenti ai file trovati dalla query.

| Colonna | Tipo di dati | Descrizione |
|------------|-------------|-------------|
| SHA1 | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| SHA256 | stringa | SHA-256 del file a cui è stata applicata l'azione registrata |
| MD5 | stringa | Hash MD5 del file a cui è stata applicata l'azione registrata |
| FileSize | int | Dimensione del file in byte |
| GlobalPrevalence | int | Numero di istanze dell'entità osservate da Microsoft a livello globale |
| GlobalFirstSeen | datetime | Data e ora in cui l'entità è stata osservata per la prima volta da Microsoft globalmente |
| GlobalLastSeen | datetime | Data e ora in cui l'entità è stata osservata per l'ultima volta da Microsoft globalmente |
| Firmatario | stringa | Informazioni sul firmatario del file |
| Autorità di certificazione | stringa | Informazioni sull'autorità di certificazione (CA) di emissione |
| SignerHash | stringa | Valore hash univoco che identifica il firmatario |
| IsCertificateValid | boolean | Se il certificato utilizzato per firmare il file è valido |
| IsRootSignerMicrosoft | boolean | Indica se il firmatario del certificato radice è Microsoft |
| IsExecutable | boolean | Se il file è un file eseguibile (PE) portatile |
| Threatname | stringa | Nome del rilevamento per qualsiasi malware o altre minacce trovate |
| Publisher | stringa | Nome dell'organizzazione che ha pubblicato il file |
| Softwarename | stringa | Nome del prodotto software |

## <a name="syntax"></a>Sintassi

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argomenti

- **x** -colonna ID file da utilizzare: `SHA1` , `SHA256` `InitiatingProcessSHA1` o, `InitiatingProcessSHA256` se non specificata, viene utilizzata una funzione. `SHA1`
- **y** -limitare il numero di record da arricchire, 1-1000; la funzione utilizza 100 se non specificata

## <a name="examples"></a>Esempi

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Proiettare solo la colonna SHA1 e arricchirla

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Arricchire i primi 500 record ed elencare i file di bassa prevalenza

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)