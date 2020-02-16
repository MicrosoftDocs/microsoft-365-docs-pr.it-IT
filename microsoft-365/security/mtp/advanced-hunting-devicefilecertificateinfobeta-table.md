---
title: Tabella DeviceFileCertificateInfoBeta nello schema di caccia avanzato
description: Informazioni sulla firma dei file nella tabella DeviceFileCertificateInfoBeta dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, firma digitale, certificato, firma dei file, DeviceFileCertificateInfoBeta
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
ms.openlocfilehash: c1d6b9170f0cc236f2656ce2adb596c31d9ee2bd
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087525"
---
# <a name="devicefilecertificateinfobeta"></a>DeviceFileCertificateInfoBeta

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La `DeviceFileCertificateInfoBeta` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sui certificati di firma dei file. In questa tabella vengono utilizzati i dati ottenuti dalle attività di verifica dei certificati eseguite regolarmente sui file negli endpoint.

Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `IsSigned` | boolean | Indica se il file è firmato |
| `SignatureType` | stringa | Indica se le informazioni sulla firma sono state lette come contenuto incorporato nel file stesso o lette da un file di catalogo esterno. |
| `Signer` | stringa | Informazioni sul firmatario del file |
| `SignerHash` | stringa | Valore hash univoco che identifica il firmatario |
| `Issuer` | stringa | Informazioni sull'autorità di certificazione (CA) di emissione |
| `IssuerHash` | stringa | Valore hash univoco che identifica l'autorità di certificazione (CA) di emissione |
| `CertificateSerialNumber` | stringa | Identificatore del certificato univoco per l'autorità di certificazione (CA) di emissione |
| `CrlDistributionPointUrls` | stringa |  Array JSON che elenca gli URL delle condivisioni di rete che contengono certificati e elenchi di revoche di certificati (CRL) |
| `CertificateCreationTime` | datetime | Data e ora in cui è stato creato il certificato |
| `CertificateExpirationTime` | datetime | Data e ora in cui il certificato è impostato per scadere |
| `CertificateCountersignatureTime` | datetime | Data e ora in cui il certificato è stato controfirmato |
| `IsTrusted` | boolean | Indica se il file è attendibile in base ai risultati della funzione WinVerifyTrust, che consente di verificare la presenza di informazioni sul certificato radice sconosciute, firme non valide, certificati revocati e altri attributi discutibili. |
| `IsRootSignerMicrosoft` | boolean | Indica se il firmatario del certificato radice è Microsoft |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e timestamp. | 

## <a name="related-topics"></a>Argomenti correlati
- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
