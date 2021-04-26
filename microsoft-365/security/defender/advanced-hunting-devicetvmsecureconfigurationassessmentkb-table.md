---
title: Tabella DeviceTvmSecureConfigurationAssessmentKB nello schema per Ricerca avanzata
description: Informazioni sulle diverse configurazioni sicure valutate da Gestione delle minacce e della vulnerabilità nella tabella DeviceTvmSecureConfigurationAssessmentKB dello schema per Ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, configurazione della sicurezza, miTRE ATT&framework CK, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1dfa710b86afdcfd8a5643555564a0f34c7b4702
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024242"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="49151-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="49151-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="49151-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="49151-105">**Applies to:**</span></span>
- <span data-ttu-id="49151-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49151-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="49151-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="49151-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="49151-108">La tabella `DeviceTvmSecureConfigurationAssessmentKB` nello schema per Ricerca avanzata contiene informazioni riguardanti le varie configurazioni sicure (ad esempio, se un dispositivo ha aggiornamenti automatici attivi) controllate da [Gestione delle minacce e della vulnerabilità](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="49151-108">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="49151-109">Include inoltre informazioni relative ai rischi, benchmark del settore correlati e tecniche e tattiche MITRE ATT&CK applicabili.</span><span class="sxs-lookup"><span data-stu-id="49151-109">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="49151-110">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="49151-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="49151-111">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="49151-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="49151-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="49151-112">Column name</span></span> | <span data-ttu-id="49151-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="49151-113">Data type</span></span> | <span data-ttu-id="49151-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49151-114">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="49151-115">stringa</span><span class="sxs-lookup"><span data-stu-id="49151-115">string</span></span> | <span data-ttu-id="49151-116">Identificatore univoco di una configurazione specifica</span><span class="sxs-lookup"><span data-stu-id="49151-116">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="49151-117">stringa</span><span class="sxs-lookup"><span data-stu-id="49151-117">string</span></span> | <span data-ttu-id="49151-118">Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10)</span><span class="sxs-lookup"><span data-stu-id="49151-118">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="49151-119">stringa</span><span class="sxs-lookup"><span data-stu-id="49151-119">string</span></span> | <span data-ttu-id="49151-120">Nome visualizzato della configurazione</span><span class="sxs-lookup"><span data-stu-id="49151-120">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="49151-121">stringa</span><span class="sxs-lookup"><span data-stu-id="49151-121">string</span></span> | <span data-ttu-id="49151-122">Descrizione della configurazione</span><span class="sxs-lookup"><span data-stu-id="49151-122">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="49151-123">stringa</span><span class="sxs-lookup"><span data-stu-id="49151-123">string</span></span> | <span data-ttu-id="49151-124">Descrizione del rischio associato</span><span class="sxs-lookup"><span data-stu-id="49151-124">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="49151-125">stringa</span><span class="sxs-lookup"><span data-stu-id="49151-125">string</span></span> | <span data-ttu-id="49151-126">Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="49151-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="49151-127">stringa</span><span class="sxs-lookup"><span data-stu-id="49151-127">string</span></span> |<span data-ttu-id="49151-128">Sottocategoria o sottoraggruppamento a cui appartiene la configurazione.</span><span class="sxs-lookup"><span data-stu-id="49151-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="49151-129">In molti casi qui vengono descritte capacità o funzionalità specifiche.</span><span class="sxs-lookup"><span data-stu-id="49151-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="49151-130">stringa</span><span class="sxs-lookup"><span data-stu-id="49151-130">string</span></span> | <span data-ttu-id="49151-131">Elenco dei parametri del settore che consigliano una configurazione identica o simile</span><span class="sxs-lookup"><span data-stu-id="49151-131">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="49151-132">stringa</span><span class="sxs-lookup"><span data-stu-id="49151-132">string</span></span> | <span data-ttu-id="49151-133">Etichette che rappresentano vari attributi utilizzati per identificare o categorizzare una configurazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="49151-133">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="49151-134">stringa</span><span class="sxs-lookup"><span data-stu-id="49151-134">string</span></span> | <span data-ttu-id="49151-135">Azioni consigliate per ridurre o risolvere eventuali rischi associati</span><span class="sxs-lookup"><span data-stu-id="49151-135">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="49151-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="49151-136">Related topics</span></span>

- [<span data-ttu-id="49151-137">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="49151-137">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="49151-138">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="49151-138">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="49151-139">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="49151-139">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="49151-140">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="49151-140">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="49151-141">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="49151-141">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="49151-142">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="49151-142">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="49151-143">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="49151-143">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)