---
title: La tabella DeviceTvmSoftwareVulnerabilitiesKB nello schema di ricerca avanzata
description: Informazioni sulle vulnerabilità del software monitorate dalla Gestione delle minacce e delle vulnerabilità nella tabella DeviceTvmSoftwareVulnerabilitiesKB dello schema di ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, schema, riferimento, kusto, tabella, colonna, tipo di dati, descrizione, & gestione delle vulnerabilità delle minacce, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023798"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender
- Microsoft Defender per endpoint



La tabella `DeviceTvmSoftwareVulnerabilitiesKB` nello schema di ricerca avanzata contiene l'elenco delle vulnerabilità per le quali [Gestione delle minacce e delle vulnerabilità](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) valuta i dispositivi. Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `CveId` | stringa | Identificatore univoco assegnato alla vulnerabilità di sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE) |
| `CvssScore` | stringa | Punteggio di gravità assegnato alla vulnerabilità di sicurezza secondo il Sistema di punteggio della vulnerabilità comune (CVSS) |
| `IsExploitAvailable` | boolean | Indica se il codice di sfruttamento della vulnerabilità è disponibile pubblicamente |
| `VulnerabilitySeverityLevel` | stringa | Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dal panorama delle minacce |
| `LastModifiedTime` | datetime | Data e ora dell'ultima modifica dell'elemento o dei metadati correlati |
| `PublishedDate` | datetime | La vulnerabilità della data è stata resa pubblica |
| `VulnerabilityDescription` | stringa | Descrizione della vulnerabilità e dei rischi associati |
| `AffectedSoftware` | stringa | Elenco di tutti i prodotti software soggetti alla vulnerabilità |

## <a name="related-topics"></a>Argomenti correlati

- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica della Gestione della vulnerabilità e delle minacce](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)