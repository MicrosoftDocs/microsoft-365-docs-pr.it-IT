---
title: Funzione FileProfile() nella ricerca avanzata per Microsoft 365 Defender
description: Informazioni su come usare FileProfile() per migliorare le informazioni sui file nei risultati delle query di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, FileProfile, profilo file, funzione, arricchimento
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
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929551"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La funzione è una funzione di arricchimento nella ricerca avanzata che `FileProfile()` aggiunge i dati seguenti ai file trovati dalla query. [](advanced-hunting-overview.md)

| Colonna | Tipo di dati | Descrizione |
|------------|-------------|-------------|
| SHA1 | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| SHA256 | stringa | SHA-256 del file a cui è stata applicata l'azione registrata |
| MD5 | stringa | Hash MD5 del file a cui è stata applicata l'azione registrata |
| FileSize | int | Dimensioni del file in byte |
| GlobalPrevalence | int | Numero di istanze dell'entità osservate da Microsoft a livello globale |
| GlobalFirstSeen | datetime | Data e ora in cui l'entità è stata osservata per la prima volta da Microsoft a livello globale |
| GlobalLastSeen | datetime | Data e ora dell'ultima osservazione globale dell'entità da parte di Microsoft |
| Firmatario | stringa | Informazioni sul firmatario del file |
| Autorità di certificazione | stringa | Informazioni sull'autorità di certificazione (CA) emittente |
| SignerHash | stringa | Valore hash univoco che identifica il firmatario |
| IsCertificateValid | boolean | Indica se il certificato utilizzato per firmare il file è valido |
| IsRootSignerMicrosoft | boolean | Indica se il firmatario del certificato radice è Microsoft |
| IsExecutable | boolean | Indica se il file è un file PE (Portable Executable) |
| ThreatName | stringa | Nome di rilevamento per qualsiasi malware o altre minacce rilevate |
| Publisher | stringa | Nome dell'organizzazione che ha pubblicato il file |
| SoftwareName | stringa | Nome del prodotto software |

## <a name="syntax"></a>Sintassi

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argomenti

- **x**-colonna ID file da utilizzare: `SHA1` , , o ; funzione utilizzata se non `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` specificata
- **y**: limite al numero di record da arricchire, da 1 a 1000; utilizza 100 se non specificato

## <a name="examples"></a>Esempi

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Proiettare solo la colonna SHA1 e arricchirla

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Arricchire i primi 500 record ed elencare i file a bassa diffusione

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
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Ottenere altri esempi di query](advanced-hunting-shared-queries.md)
