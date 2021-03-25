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
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="aca5f-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="aca5f-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aca5f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="aca5f-105">**Applies to:**</span></span>
- [<span data-ttu-id="aca5f-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="aca5f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="aca5f-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="aca5f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aca5f-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="aca5f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="aca5f-109">La tabella `DeviceTvmSecureConfigurationAssessmentKB` nello schema per Ricerca avanzata contiene informazioni riguardanti le varie configurazioni sicure (ad esempio, se un dispositivo ha aggiornamenti automatici attivi) controllate da [Gestione delle minacce e della vulnerabilità](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="aca5f-109">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="aca5f-110">Include inoltre informazioni relative ai rischi, benchmark del settore correlati e tecniche e tattiche MITRE ATT&CK applicabili.</span><span class="sxs-lookup"><span data-stu-id="aca5f-110">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="aca5f-111">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="aca5f-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="aca5f-112">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="aca5f-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="aca5f-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="aca5f-113">Column name</span></span> | <span data-ttu-id="aca5f-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="aca5f-114">Data type</span></span> | <span data-ttu-id="aca5f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aca5f-115">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="aca5f-116">stringa</span><span class="sxs-lookup"><span data-stu-id="aca5f-116">string</span></span> | <span data-ttu-id="aca5f-117">Identificatore univoco di una configurazione specifica</span><span class="sxs-lookup"><span data-stu-id="aca5f-117">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="aca5f-118">stringa</span><span class="sxs-lookup"><span data-stu-id="aca5f-118">string</span></span> | <span data-ttu-id="aca5f-119">Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10)</span><span class="sxs-lookup"><span data-stu-id="aca5f-119">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="aca5f-120">stringa</span><span class="sxs-lookup"><span data-stu-id="aca5f-120">string</span></span> | <span data-ttu-id="aca5f-121">Nome visualizzato della configurazione</span><span class="sxs-lookup"><span data-stu-id="aca5f-121">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="aca5f-122">stringa</span><span class="sxs-lookup"><span data-stu-id="aca5f-122">string</span></span> | <span data-ttu-id="aca5f-123">Descrizione della configurazione</span><span class="sxs-lookup"><span data-stu-id="aca5f-123">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="aca5f-124">stringa</span><span class="sxs-lookup"><span data-stu-id="aca5f-124">string</span></span> | <span data-ttu-id="aca5f-125">Descrizione del rischio associato</span><span class="sxs-lookup"><span data-stu-id="aca5f-125">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="aca5f-126">stringa</span><span class="sxs-lookup"><span data-stu-id="aca5f-126">string</span></span> | <span data-ttu-id="aca5f-127">Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="aca5f-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="aca5f-128">stringa</span><span class="sxs-lookup"><span data-stu-id="aca5f-128">string</span></span> |<span data-ttu-id="aca5f-129">Sottocategoria o sottoraggruppamento a cui appartiene la configurazione.</span><span class="sxs-lookup"><span data-stu-id="aca5f-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="aca5f-130">In molti casi qui vengono descritte capacità o funzionalità specifiche.</span><span class="sxs-lookup"><span data-stu-id="aca5f-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="aca5f-131">stringa</span><span class="sxs-lookup"><span data-stu-id="aca5f-131">string</span></span> | <span data-ttu-id="aca5f-132">Elenco dei parametri del settore che consigliano una configurazione identica o simile</span><span class="sxs-lookup"><span data-stu-id="aca5f-132">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="aca5f-133">stringa</span><span class="sxs-lookup"><span data-stu-id="aca5f-133">string</span></span> | <span data-ttu-id="aca5f-134">Elenco delle tecniche del framework Mitre ATT&CK framework correlate alla configurazione</span><span class="sxs-lookup"><span data-stu-id="aca5f-134">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="aca5f-135">stringa</span><span class="sxs-lookup"><span data-stu-id="aca5f-135">string</span></span> | <span data-ttu-id="aca5f-136">Elenco delle tattiche del framework Mitre ATT&CK framework correlate alla configurazione</span><span class="sxs-lookup"><span data-stu-id="aca5f-136">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="aca5f-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="aca5f-137">Related topics</span></span>

- [<span data-ttu-id="aca5f-138">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="aca5f-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="aca5f-139">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="aca5f-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="aca5f-140">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="aca5f-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="aca5f-141">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="aca5f-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
