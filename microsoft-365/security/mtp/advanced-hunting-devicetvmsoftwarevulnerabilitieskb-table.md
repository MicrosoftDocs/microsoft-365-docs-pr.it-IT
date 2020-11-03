---
title: La tabella DeviceTvmSoftwareVulnerabilitiesKB nello schema di ricerca avanzata
description: Informazioni sulle vulnerabilità del software monitorate dalla Gestione delle minacce e delle vulnerabilità nella tabella DeviceTvmSoftwareVulnerabilitiesKB dello schema di ricerca avanzata.
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, schema, riferimento, kusto, tabella, colonna, tipo di dati, descrizione, Threat & vulnerabilità di gestione, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: f5cbc037dce72979874be6246a24ea3491a90df1
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847489"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La tabella `DeviceTvmSoftwareVulnerabilitiesKB` nello schema di ricerca avanzata contiene l'elenco delle vulnerabilità per le quali [Gestione delle minacce e delle vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) valuta i dispositivi. Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

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
- [Panoramica della Gestione della vulnerabilità e delle minacce](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
