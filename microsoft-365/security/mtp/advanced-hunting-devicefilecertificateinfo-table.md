---
title: Tabella DeviceFileCertificateInfo nello schema di ricerca avanzata
description: Informazioni sulle informazioni sulla firma dei file nella tabella DeviceFileCertificateInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, firma digitale, certificato, firma file, DeviceFileCertificateInfo
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
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931315"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La `DeviceFileCertificateInfo` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sui certificati di firma dei file. Questa tabella usa i dati ottenuti dalle attività di verifica dei certificati eseguite regolarmente sui file sugli endpoint.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `IsSigned` | boolean | Indica se il file è firmato |
| `SignatureType` | stringa | Indica se le informazioni sulla firma sono stata lette come contenuto incorporato nel file stesso o da un file di catalogo esterno. |
| `Signer` | stringa | Informazioni sul firmatario del file |
| `SignerHash` | stringa | Valore hash univoco che identifica il firmatario |
| `Issuer` | stringa | Informazioni sull'autorità di certificazione (CA) emittente |
| `IssuerHash` | stringa | Valore hash univoco che identifica l'autorità di certificazione (CA) emittente |
| `CertificateSerialNumber` | stringa | Identificatore del certificato univoco dell'autorità di certificazione emittente |
| `CrlDistributionPointUrls` | stringa |  Array JSON che elenca gli URL delle condivisioni di rete che contengono certificati ed elenchi di revoche di certificati (CRL) |
| `CertificateCreationTime` | datetime | Data e ora di creazione del certificato |
| `CertificateExpirationTime` | datetime | Data e ora di scadenza del certificato |
| `CertificateCountersignatureTime` | datetime | Data e ora in cui il certificato è stato controfirmato |
| `IsTrusted` | boolean | Indica se il file è attendibile in base ai risultati della funzione WinVerifyTrust, che verifica la presenza di informazioni sconosciute sul certificato radice, firme non valide, certificati revocati e altri attributi discutibili |
| `IsRootSignerMicrosoft` | boolean | Indica se il firmatario del certificato radice è Microsoft |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare eventi univoci, questa colonna deve essere usata insieme alle colonne DeviceName e Timestamp. | 

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
