---
title: Rilevare dispositivi esposti
description: Informazioni su gestione di minacce e vulnerabilità possono essere usate per aiutare amministratori della sicurezza, amministratori IT e SecOps a collaborare.
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
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="6a13f-104">Ricerca di dispositivi esposti - gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="6a13f-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a13f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6a13f-105">**Applies to:**</span></span>

- [<span data-ttu-id="6a13f-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6a13f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6a13f-107">Minaccia e gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="6a13f-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6a13f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a13f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6a13f-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6a13f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6a13f-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="6a13f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="6a13f-111">Usare la ricerca avanzata per trovare i dispositivi con vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="6a13f-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="6a13f-112">La ricerca avanzata è uno strumento di ricerca delle minacce basato sulla query che permette di esplorare dati non elaborati fino a 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="6a13f-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="6a13f-113">È possibile esaminare in modo proattivo gli eventi nella rete per individuare gli indicatori di minaccia e le entità.</span><span class="sxs-lookup"><span data-stu-id="6a13f-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="6a13f-114">L'accesso flessibile ai dati consente la ricerca senza vincoli delle minacce note e potenziali.</span><span class="sxs-lookup"><span data-stu-id="6a13f-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="6a13f-115">Ulteriori informazioni sulla ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="6a13f-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="6a13f-116">Tabelle dello schema</span><span class="sxs-lookup"><span data-stu-id="6a13f-116">Schema tables</span></span>

- <span data-ttu-id="6a13f-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventario del software installato nei dispositivi, incluse le informazioni sulla versione e lo stato di fine del supporto.</span><span class="sxs-lookup"><span data-stu-id="6a13f-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status.</span></span>

- <span data-ttu-id="6a13f-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Vulnerabilità software trovate nei dispositivi e l'elenco degli aggiornamenti della sicurezza disponibili che affrontano ogni vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="6a13f-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability.</span></span>

- <span data-ttu-id="6a13f-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base di vulnerabilità divulgate pubblicamente, incluso se il codice di exploit è pubblicamente disponibile.</span><span class="sxs-lookup"><span data-stu-id="6a13f-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available.</span></span>

- <span data-ttu-id="6a13f-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Eventi di valutazione delle minacce e gestione delle vulnerabilità, che indicano lo stato di varie configurazioni di sicurezza nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6a13f-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices.</span></span>

- <span data-ttu-id="6a13f-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge Base di varie configurazioni di sicurezza utilizzate da Threat & Vulnerability Management per valutare i dispositivi; include mapping a diversi standard e benchmark</span><span class="sxs-lookup"><span data-stu-id="6a13f-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="6a13f-122">Verificare quali dispositivi sono coinvolti in avvisi di gravità elevata</span><span class="sxs-lookup"><span data-stu-id="6a13f-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="6a13f-123">Passare a **Ricerca avanzata** dal riquadro di spostamento sinistro della Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="6a13f-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="6a13f-124">Scorrere verso il basso fino agli schemi di ricerca avanzata TVM per acquisire familiarità con i nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="6a13f-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="6a13f-125">Immettere le query seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a13f-125">Enter the following queries:</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="6a13f-126">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6a13f-126">Related topics</span></span>

- [<span data-ttu-id="6a13f-127">Panoramica delle minacce gestione delle vulnerabilità sicurezza</span><span class="sxs-lookup"><span data-stu-id="6a13f-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6a13f-128">Consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="6a13f-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="6a13f-129">API</span><span class="sxs-lookup"><span data-stu-id="6a13f-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="6a13f-130">Configurare l'accesso ai dati per gestione di minacce e vulnerabilità ruoli</span><span class="sxs-lookup"><span data-stu-id="6a13f-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="6a13f-131">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="6a13f-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="6a13f-132">Tutte le tabelle di ricerca avanzate</span><span class="sxs-lookup"><span data-stu-id="6a13f-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
