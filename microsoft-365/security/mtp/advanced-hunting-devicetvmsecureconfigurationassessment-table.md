---
title: Tabella DeviceTvmSecureConfigurationAssessment nello schema di Ricerca avanzata
description: Informazioni sugli eventi di valutazione della sicurezza nella tabella DeviceTvmSecureConfigurationAssessment dello schema di caccia avanzato. Tali rischi & eventi di gestione della vulnerabilità forniscono informazioni sui dispositivi, oltre a dettagli sulla configurazione della sicurezza, informazioni sull'impatto e sulla conformità.
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, Threat & vulnerabilità di gestione, TVM, gestione dei dispositivi, configurazione della sicurezza, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 356548c3115aacce8c76d7fbc552811c168750ed
ms.sourcegitcommit: e8b3855302fc34d09b6df6c737033a2f326d6eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48770074"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection



Ogni riga della tabella `DeviceTvmSecureConfigurationAssessment` contiene un evento di valutazione per una specifica configurazione di sicurezza della [Gestione delle minacce e della vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Usare questo riferimento per controllare i risultati più recenti della valutazione e determinare se i dispositivi sono conformi.

Per informazioni su altre tabelle nello schema di Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).

| Nome colonna | Tipo di dati | Descrizione |
|-------------|-----------|-------------|
| `DeviceId` | stringa | Identificatore univoco per il dispositivo nel servizio |
| `DeviceName` | stringa | Nome di dominio completo (FQDN) del dispositivo |
| `OSPlatform` | stringa | Piattaforma del sistema operativo in esecuzione nel dispositivo. Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.|
| `Timestamp` | datetime | Data e ora in cui è stato generato il record |
| `ConfigurationId` | stringa | Identificatore univoco di una configurazione specifica |
| `ConfigurationCategory` | stringa | Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza |
| `ConfigurationSubcategory` | stringa | Sottocategoria o sottoraggruppamento a cui appartiene la configurazione. In molti casi qui vengono descritte capacità o funzionalità specifiche. |
| `ConfigurationImpact` | stringa | Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10) |
| `IsCompliant` | booleano | Indica se la configurazione o i criteri sono configurati correttamente |
| `IsApplicable` | boolean | Indica se la configurazione o il criterio si applica al dispositivo |
| `Context` | stringa | Ulteriori informazioni contestuali sulla configurazione o sui criteri |
| `IsExpectedUserImpactCompliant` | boolean | Indica se l'impatto dell'utente verrà applicato se la configurazione o il criterio vengono applicati |

## <a name="related-topics"></a>Argomenti correlati

- [Ricerca proattiva delle minacce](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica della Gestione della vulnerabilità e delle minacce](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
