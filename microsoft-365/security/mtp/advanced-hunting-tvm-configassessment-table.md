---
title: Tabella DeviceTvmSecureConfigurationAssessment nello schema di Ricerca avanzata
description: Informazioni sugli eventi di valutazione della sicurezza della Gestione delle minacce e della vulnerabilità nella tabella DeviceTvmSecureConfigurationAssessment dello schema di Ricerca avanzata. Questi eventi forniscono informazioni sul computer, oltre a dettagli relativi alla configurazione della sicurezza, all’impatto e a informazioni sulla conformità.
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, ricerca, query, telemetria, schema di riferimento, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle minacce e della vulnerabilità, TVM, gestione dei dispositivi, configurazione della sicurezza, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2fee44c0d9c9ff30ca23ccef863e056cadee7de8
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911199"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

**Si applica a:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

Ogni riga della tabella `DeviceTvmSecureConfigurationAssessment` contiene un evento di valutazione per una specifica configurazione di sicurezza della [Gestione delle minacce e della vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Usare questo riferimento per controllare i risultati più recenti della valutazione e determinare se i dispositivi sono conformi.

Per informazioni su altre tabelle nello schema di Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `MachineId` | stringa | Identificatore univoco per il computer nel servizio |
| `ComputerName` | stringa | Nome di dominio completo (FQDN) del computer |
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione sul computer. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.|
| `Timestamp` | datetime | Data e ora in cui è stato generato il record |
| `ConfigurationId` | stringa | Identificatore univoco di una configurazione specifica |
| `ConfigurationCategory` | stringa | Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza |
| `ConfigurationSubcategory` | stringa | Sottocategoria o sottoraggruppamento a cui appartiene la configurazione. In molti casi qui vengono descritte capacità o funzionalità specifiche. |
| `ConfigurationImpact` | stringa | Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10) |
| `IsCompliant` | booleano | Indica se la configurazione o i criteri sono configurati correttamente |

## <a name="related-topics"></a>Argomenti correlati

- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi ed email](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica della Gestione delle minacce e della vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
