---
title: Tabella DeviceFileCertificateInfo nello schema di ricerca avanzata
description: Informazioni sulle informazioni sulla firma dei file nella tabella DeviceFileCertificateInfo dello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, firma digitale, certificato, firma file, DeviceFileCertificateInfo
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
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b3b5af8093107925c6c12c901e8138960c5eeaf6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064381"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La `DeviceFileCertificateInfo` tabella nello schema di ricerca [avanzata](advanced-hunting-overview.md) contiene informazioni sui certificati di firma dei file. Questa tabella usa i dati ottenuti dalle attività di verifica dei certificati eseguite regolarmente sui file sugli endpoint.

Per informazioni sulle altre tabelle nello schema di ricerca avanzata, vedere la guida di riferimento [allo schema di ricerca avanzata.](advanced-hunting-schema-reference.md)

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Data e ora di registrazione dell'evento |
| `DeviceId` | stringa | Identificatore univoco del dispositivo nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo |
| `SHA1` | stringa | SHA-1 del file a cui è stata applicata l'azione registrata |
| `IsSigned` | boolean | Indica se il file è firmato |
| `SignatureType` | stringa | Indica se le informazioni sulla firma sono stati letti come contenuto incorporato nel file stesso o letti da un file di catalogo esterno |
| `Signer` | stringa | Informazioni sul firmatario del file |
| `SignerHash` | stringa | Valore hash univoco che identifica il firmatario |
| `Issuer` | stringa | Informazioni sull'autorità di certificazione (CA) emittente |
| `IssuerHash` | stringa | Valore hash univoco che identifica l'autorità di certificazione (CA) emittente |
| `CertificateSerialNumber` | stringa | Identificatore del certificato univoco dell'autorità di certificazione (CA) emittente |
| `CrlDistributionPointUrls` | stringa |  Array JSON che elenca gli URL delle condivisioni di rete che contengono certificati ed elenchi di revoche di certificati (CRL) |
| `CertificateCreationTime` | datetime | Data e ora di creazione del certificato |
| `CertificateExpirationTime` | datetime | Data e ora di scadenza del certificato |
| `CertificateCountersignatureTime` | datetime | Data e ora in cui il certificato è stato controfirmato |
| `IsTrusted` | boolean | Indica se il file è attendibile in base ai risultati della funzione WinVerifyTrust, che verifica la presenza di informazioni sconosciute sul certificato radice, firme non valide, certificati revocati e altri attributi discutibile |
| `IsRootSignerMicrosoft` | boolean | Indica se il firmatario del certificato radice è Microsoft |
| `ReportId` | long | Identificatore di evento basato su un contatore ripetuto. Per identificare gli eventi univoci, è necessario utilizzare questa colonna insieme alle colonne DeviceName e Timestamp. |


## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprensione dello schema](advanced-hunting-schema-reference.md)
