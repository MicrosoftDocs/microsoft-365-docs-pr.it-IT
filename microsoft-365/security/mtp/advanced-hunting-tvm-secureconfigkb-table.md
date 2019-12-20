---
title: Tabella DeviceTvmSecureConfigurationAssessmentKB nello schema per Ricerca avanzata
description: Informazioni sulle diverse configurazioni sicure valutate da Gestione delle minacce e della vulnerabilità nella tabella DeviceTvmSecureConfigurationAssessmentKB dello schema per Ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca minacce informatiche, ricerca, eseguire una query, telemetria, riferimento dello schema, esplora dati, tabella, colonna, tipo di dati, descrizione, gestione delle minacce e della vulnerabilità, TVM, gestione dei dispositivi, configurazione della sicurezza, framework MITRE ATT&CK, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: a3ae0a95af4a51d492c577e6a2ac1f2b96bba635
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806935"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La tabella `DeviceTvmSecureConfigurationAssessmentKB` nello schema per Ricerca avanzata contiene informazioni riguardanti le varie configurazioni sicure (ad esempio, se un dispositivo ha aggiornamenti automatici attivi) controllate da [Gestione delle minacce e della vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Include inoltre informazioni relative ai rischi, benchmark del settore correlati e tecniche e tattiche MITRE ATT&CK applicabili. Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `ConfigurationId` | stringa | Identificatore univoco di una configurazione specifica |
| `ConfigurationImpact` | stringa | Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10) |
| `ConfigurationName` | stringa | Nome visualizzato della configurazione |
| `ConfigurationDescription` | stringa | Descrizione della configurazione |
| `RiskDescription` | stringa | Descrizione del rischio associato |
| `ConfigurationCategory` | stringa | Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza|
| `ConfigurationSubcategory` | stringa |Sottocategoria o sottoraggruppamento a cui appartiene la configurazione. In molti casi qui vengono descritte capacità o funzionalità specifiche. |
| `ConfigurationBenchmarks` | stringa | Elenco dei parametri del settore che consigliano una configurazione identica o simile |
| `RelatedMitreTechniques` | stringa | Elenco delle tecniche del framework Mitre ATT&CK framework correlate alla configurazione |
| `RelatedMitreTactics ` | stringa | Elenco delle tattiche del framework Mitre ATT&CK framework correlate alla configurazione |

## <a name="related-topics"></a>Argomenti correlati

- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Ricerca delle minacce attraverso dispositivi e posta elettronica](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica della Gestione della vulnerabilità e delle minacce](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
