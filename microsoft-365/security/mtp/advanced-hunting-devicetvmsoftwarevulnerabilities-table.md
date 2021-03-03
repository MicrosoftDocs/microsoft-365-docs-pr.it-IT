---
title: Tabella DeviceTvmSoftwareVulnerabilities nello schema di ricerca avanzata
description: Informazioni sulle vulnerabilità software riscontrate nei dispositivi e sull'elenco degli aggiornamenti della sicurezza disponibili che affrontano ogni vulnerabilità nella tabella DeviceTvmSoftwareVulnerabilities dello schema di ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: maccruz
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ed5104068d7cff4ddace3405219ebc57092d390e
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416803"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

>[!IMPORTANT]
> Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato. Microsoft makes no warranties, express or implied, with respect to the information provided here.

La `DeviceTvmSoftwareVulnerabilities` tabella nello schema di ricerca avanzata contiene l'elenco delle vulnerabilità di Gestione delle [&](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) minacce nei prodotti software installati. La tabella include anche informazioni su sistema operativo, ID CVE ID e grado di vulnerabilità. È possibile utilizzare questa tabella, ad esempio, per cercare eventi che coinvolgono dispositivi con gravi vulnerabilità nel software. Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

>[!NOTE]
> La `DeviceTvmSoftwareInventory` tabella e le tabelle sono state `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` sostituite. Insieme, le prime due tabelle includono più colonne che è possibile usare per informare le attività di gestione della vulnerablity o per cercare dispositivi vulnerabili.

Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `DeviceId` | stringa | Identificatore univoco per il computer nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del computer |
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione sul computer. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7. |
| `OSVersion` | stringa | Versione del sistema operativo in esecuzione sul computer |
| `OSArchitecture` | stringa | Architettura del sistema operativo in esecuzione sul computer |
| `SoftwareVendor` | stringa | Nome del fornitore del software |
| `SoftwareName` | stringa | Nome del prodotto software |
| `SoftwareVersion` | stringa | Numero della versione del prodotto software |
| `CveId` | stringa | Identificatore univoco assegnato alla vulnerabilità di sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE) |
| `VulnerabilitySeverityLevel` | stringa | Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dalle possibili minacce |
| `RecommendedSecurityUpdate` | stringa | Nome o descrizione dell'aggiornamento della sicurezza fornito dal fornitore del software per risolvere la vulnerabilità |
| `RecommendedSecurityUpdateId` | stringa | Identificatore degli aggiornamenti della sicurezza applicabili o identificatore per gli articoli della Knowledge Base (KB) corrispondenti |



## <a name="related-topics"></a>Argomenti correlati

- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica della Gestione della vulnerabilità e delle minacce](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
