---
title: Tabella DeviceTvmSoftwareInventoryVulnerabilities nello schema per Ricerca avanzata
description: Informazioni su un inventario si software nel dispositivo e sulle loro vulnerabilità nella tabella DeviceTvmSoftwareInventoryVulnerabilities dello schema per Ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, ricerca, query, telemetria, schema di riferimento, esplora dati, tabella, colonna, tipo di dati, descrizione, gestione delle minacce e vulnerabilità, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, sistema operativo, DeviceTvmSoftwareVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f7c7ab393a956aa894a0ca8704ea0e99a82addc9
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911197"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

**Si applica a:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

La `DeviceTvmSoftwareInventoryVulnerabilities` tabella nello schema per Ricerca avanzata contiene l'inventario [Gestione delle minacce e delle vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) dei software sui dispositivi, oltre alle vulnerabilità di tali prodotti software. La tabella include anche informazioni su sistema operativo, ID CVE ID e grado di vulnerabilità. Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `MachineId` | stringa | Identificatore univoco per il computer nel servizio |
| `ComputerName` | stringa | Nome di dominio completo (FQDN) del computer |
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione sul computer. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. |
| `OSVersion` | stringa | Versione del sistema operativo in esecuzione sul computer |
| `OSArchitecture` | stringa | Architettura del sistema operativo in esecuzione sul computer |
| `SoftwareVendor` | stringa | Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dalle possibili minacce |
| `SoftwareName` | stringa | Nome del prodotto software |
| `SoftwareVersion` | stringa | Numero della versione del prodotto software |
| `CveId` | stringa | Identificatore univoco assegnato alla vulnerabilità della sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE) |
| `VulnerabilitySeverityLevel` | stringa | Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dalle possibili minacce |



## <a name="related-topics"></a>Argomenti correlati

- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e email](advanced-hunting-query-emails-devices.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica della Gestione della vulnerabilità e delle minacce](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
