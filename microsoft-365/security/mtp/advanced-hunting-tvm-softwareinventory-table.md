---
title: Tabella DeviceTvmSoftwareInventoryVulnerabilities nello schema per Ricerca avanzata
description: Informazioni su un inventario si software nel dispositivo e sulle loro vulnerabilità nella tabella DeviceTvmSoftwareInventoryVulnerabilities dello schema per Ricerca avanzata.
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, Threat & vulnerabilità di gestione, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 92c06eb01abd13df22ae33e72d9663084b05f7ef
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600293"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La `DeviceTvmSoftwareInventoryVulnerabilities` tabella nello schema per Ricerca avanzata contiene l'inventario [Gestione delle minacce e delle vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) dei software sui dispositivi, oltre alle vulnerabilità di tali prodotti software. La tabella include anche informazioni su sistema operativo, ID CVE ID e grado di vulnerabilità. Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

Per informazioni su altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
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
