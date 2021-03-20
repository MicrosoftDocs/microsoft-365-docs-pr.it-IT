---
title: Tabella DeviceTvmSecureConfigurationAssessmentKB nello schema per Ricerca avanzata
description: Informazioni sulle diverse configurazioni sicure valutate da Gestione delle minacce e della vulnerabilità nella tabella DeviceTvmSecureConfigurationAssessmentKB dello schema per Ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità & minacce, TVM, gestione dei dispositivi, configurazione della sicurezza, mitre att&framework CK, knowledge base, KB, DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 23b109ee5c149ecf9015f8c1622e03b20bdf243c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907337"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="ab5cf-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="ab5cf-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ab5cf-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ab5cf-105">**Applies to:**</span></span>
- <span data-ttu-id="ab5cf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab5cf-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="ab5cf-107">La tabella `DeviceTvmSecureConfigurationAssessmentKB` nello schema per Ricerca avanzata contiene informazioni riguardanti le varie configurazioni sicure (ad esempio, se un dispositivo ha aggiornamenti automatici attivi) controllate da [Gestione delle minacce e della vulnerabilità](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="ab5cf-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="ab5cf-108">Include inoltre informazioni relative ai rischi, benchmark del settore correlati e tecniche e tattiche MITRE ATT&CK applicabili.</span><span class="sxs-lookup"><span data-stu-id="ab5cf-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="ab5cf-109">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="ab5cf-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="ab5cf-110">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ab5cf-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ab5cf-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="ab5cf-111">Column name</span></span> | <span data-ttu-id="ab5cf-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ab5cf-112">Data type</span></span> | <span data-ttu-id="ab5cf-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab5cf-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="ab5cf-114">stringa</span><span class="sxs-lookup"><span data-stu-id="ab5cf-114">string</span></span> | <span data-ttu-id="ab5cf-115">Identificatore univoco di una configurazione specifica</span><span class="sxs-lookup"><span data-stu-id="ab5cf-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="ab5cf-116">stringa</span><span class="sxs-lookup"><span data-stu-id="ab5cf-116">string</span></span> | <span data-ttu-id="ab5cf-117">Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10)</span><span class="sxs-lookup"><span data-stu-id="ab5cf-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="ab5cf-118">stringa</span><span class="sxs-lookup"><span data-stu-id="ab5cf-118">string</span></span> | <span data-ttu-id="ab5cf-119">Nome visualizzato della configurazione</span><span class="sxs-lookup"><span data-stu-id="ab5cf-119">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="ab5cf-120">stringa</span><span class="sxs-lookup"><span data-stu-id="ab5cf-120">string</span></span> | <span data-ttu-id="ab5cf-121">Descrizione della configurazione</span><span class="sxs-lookup"><span data-stu-id="ab5cf-121">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="ab5cf-122">stringa</span><span class="sxs-lookup"><span data-stu-id="ab5cf-122">string</span></span> | <span data-ttu-id="ab5cf-123">Descrizione del rischio associato</span><span class="sxs-lookup"><span data-stu-id="ab5cf-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="ab5cf-124">stringa</span><span class="sxs-lookup"><span data-stu-id="ab5cf-124">string</span></span> | <span data-ttu-id="ab5cf-125">Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ab5cf-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="ab5cf-126">stringa</span><span class="sxs-lookup"><span data-stu-id="ab5cf-126">string</span></span> |<span data-ttu-id="ab5cf-127">Sottocategoria o sottoraggruppamento a cui appartiene la configurazione.</span><span class="sxs-lookup"><span data-stu-id="ab5cf-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="ab5cf-128">In molti casi qui vengono descritte capacità o funzionalità specifiche.</span><span class="sxs-lookup"><span data-stu-id="ab5cf-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="ab5cf-129">stringa</span><span class="sxs-lookup"><span data-stu-id="ab5cf-129">string</span></span> | <span data-ttu-id="ab5cf-130">Elenco dei parametri del settore che consigliano una configurazione identica o simile</span><span class="sxs-lookup"><span data-stu-id="ab5cf-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="ab5cf-131">stringa</span><span class="sxs-lookup"><span data-stu-id="ab5cf-131">string</span></span> | <span data-ttu-id="ab5cf-132">Etichette che rappresentano vari attributi utilizzati per identificare o categorizzare una configurazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ab5cf-132">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="ab5cf-133">stringa</span><span class="sxs-lookup"><span data-stu-id="ab5cf-133">string</span></span> | <span data-ttu-id="ab5cf-134">Azioni consigliate per ridurre o risolvere eventuali rischi associati</span><span class="sxs-lookup"><span data-stu-id="ab5cf-134">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ab5cf-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ab5cf-135">Related topics</span></span>

- [<span data-ttu-id="ab5cf-136">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="ab5cf-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ab5cf-137">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="ab5cf-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ab5cf-138">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="ab5cf-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ab5cf-139">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="ab5cf-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ab5cf-140">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="ab5cf-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ab5cf-141">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="ab5cf-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ab5cf-142">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="ab5cf-142">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)