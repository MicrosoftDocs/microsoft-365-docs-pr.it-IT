---
title: Rilevare dispositivi esposti
description: Informazioni su come è possibile utilizzare la gestione delle minacce e delle vulnerabilità per aiutare amministratori della sicurezza, amministratori IT e SecOps a collaborare.
keywords: Scenari di Microsoft Defender for Endpoint-tvm, Microsoft Defender for Endpoint, tvm, tvm scenarios, reduce threat & vulnerability exposure, reduce threat and vulnerability, improve security configuration, increase Microsoft Secure Score for Devices, increase threat & vulnerability Microsoft Secure Score for Devices, Microsoft Secure Score for Devices, exposure score, security controls
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9a8ebcc89c3009cd93fbb42f2a74bbb9ffcc31b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934094"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>Ricerca di dispositivi esposti - gestione delle minacce e delle vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Gestione di minacce e vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>Usare la ricerca avanzata per trovare i dispositivi con vulnerabilità

La ricerca avanzata è uno strumento di ricerca delle minacce basato sulla query che permette di esplorare dati non elaborati fino a 30 giorni. È possibile esaminare in modo proattivo gli eventi nella rete per individuare gli indicatori di minaccia e le entità. L'accesso flessibile ai dati consente la ricerca senza vincoli delle minacce note e potenziali. [Ulteriori informazioni sulla ricerca avanzata](advanced-hunting-overview.md)

### <a name="schema-tables"></a>Tabelle dello schema

- [DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventario del software installato nei dispositivi, incluse le informazioni sulla versione e lo stato di fine del supporto.

- [DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Vulnerabilità software trovate nei dispositivi e l'elenco degli aggiornamenti della sicurezza disponibili che affrontano ogni vulnerabilità.

- [DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base di vulnerabilità divulgate pubblicamente, incluso se il codice di exploit è pubblicamente disponibile.

- [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Eventi di valutazione della gestione delle minacce e delle vulnerabilità, che indicano lo stato di varie configurazioni di sicurezza nei dispositivi.

- [DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge Base di varie configurazioni di sicurezza utilizzate da Threat & Vulnerability Management per valutare i dispositivi; include mapping a diversi standard e benchmark

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>Verificare quali dispositivi sono coinvolti in avvisi di gravità elevata

1. Vai a **Ricerca avanzata** dal riquadro di spostamento sinistro di Microsoft Defender Security Center.

2. Scorrere verso il basso fino agli schemi di ricerca avanzata TVM per acquisire familiarità con i nomi delle colonne.

3. Immettere le query seguenti:

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica della gestione delle minacce e delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Consigli sulla sicurezza](tvm-security-recommendation.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)
- [Configurare l'accesso ai dati per i ruoli di gestione delle minacce e delle vulnerabilità](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [Panoramica della rilevazione avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Tutte le tabelle di ricerca avanzate](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
