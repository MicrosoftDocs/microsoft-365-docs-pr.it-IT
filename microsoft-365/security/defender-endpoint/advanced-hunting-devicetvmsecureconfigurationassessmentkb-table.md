---
title: Tabella DeviceTvmSecureConfigurationAssessmentKB nello schema per Ricerca avanzata
description: Informazioni sulle varie configurazioni sicure valutate da Threat & Vulnerability Management nella tabella DeviceTvmSecureConfigurationAssessmentKB dello schema advanced hunting.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, configurazione della sicurezza, framework MITRE ATT&CK, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067005"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

La tabella `DeviceTvmSecureConfigurationAssessmentKB` nello schema per Ricerca avanzata contiene informazioni riguardanti le varie configurazioni sicure (ad esempio, se un dispositivo ha aggiornamenti automatici attivi) controllate da [Gestione delle minacce e della vulnerabilità](next-gen-threat-and-vuln-mgt.md). Include inoltre informazioni relative ai rischi, benchmark del settore correlati e tecniche e tattiche MITRE ATT&CK applicabili. Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.

Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).

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

- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprendere lo schema](advanced-hunting-schema-reference.md)
- [Panoramica della Gestione della vulnerabilità e delle minacce](next-gen-threat-and-vuln-mgt.md)
