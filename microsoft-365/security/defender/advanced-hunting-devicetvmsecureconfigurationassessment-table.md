---
title: Tabella DeviceTvmSecureConfigurationAssessment nello schema di Ricerca avanzata
description: Informazioni sugli eventi di valutazione della sicurezza nella tabella DeviceTvmSecureConfigurationAssessment dello schema di ricerca avanzata. Questi eventi di & gestione delle vulnerabilità forniscono informazioni sul dispositivo, nonché informazioni sulla configurazione della sicurezza, sull'impatto e sulla conformità.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, threat & gestione delle vulnerabilità, TVM, gestione dei dispositivi, configurazione della sicurezza, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2e3e649911cb2ce63c2a49be0ebc93e35e8055d6
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024218"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="20ff1-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="20ff1-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="20ff1-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="20ff1-106">**Applies to:**</span></span>
- <span data-ttu-id="20ff1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20ff1-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="20ff1-108">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="20ff1-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="20ff1-109">Ogni riga della tabella `DeviceTvmSecureConfigurationAssessment` contiene un evento di valutazione per una specifica configurazione di sicurezza della [Gestione delle minacce e della vulnerabilità](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="20ff1-109">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="20ff1-110">Usare questo riferimento per controllare i risultati più recenti della valutazione e determinare se i dispositivi sono conformi.</span><span class="sxs-lookup"><span data-stu-id="20ff1-110">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="20ff1-111">Per informazioni su altre tabelle nello schema di Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="20ff1-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="20ff1-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="20ff1-112">Column name</span></span> | <span data-ttu-id="20ff1-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="20ff1-113">Data type</span></span> | <span data-ttu-id="20ff1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20ff1-114">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="20ff1-115">stringa</span><span class="sxs-lookup"><span data-stu-id="20ff1-115">string</span></span> | <span data-ttu-id="20ff1-116">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="20ff1-116">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="20ff1-117">stringa</span><span class="sxs-lookup"><span data-stu-id="20ff1-117">string</span></span> | <span data-ttu-id="20ff1-118">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="20ff1-118">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="20ff1-119">stringa</span><span class="sxs-lookup"><span data-stu-id="20ff1-119">string</span></span> | <span data-ttu-id="20ff1-120">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="20ff1-120">Platform of the operating system running on the device.</span></span> <span data-ttu-id="20ff1-121">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="20ff1-121">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="20ff1-122">datetime</span><span class="sxs-lookup"><span data-stu-id="20ff1-122">datetime</span></span> | <span data-ttu-id="20ff1-123">Data e ora in cui è stato generato il record</span><span class="sxs-lookup"><span data-stu-id="20ff1-123">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="20ff1-124">stringa</span><span class="sxs-lookup"><span data-stu-id="20ff1-124">string</span></span> | <span data-ttu-id="20ff1-125">Identificatore univoco di una configurazione specifica</span><span class="sxs-lookup"><span data-stu-id="20ff1-125">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="20ff1-126">stringa</span><span class="sxs-lookup"><span data-stu-id="20ff1-126">string</span></span> | <span data-ttu-id="20ff1-127">Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="20ff1-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="20ff1-128">stringa</span><span class="sxs-lookup"><span data-stu-id="20ff1-128">string</span></span> | <span data-ttu-id="20ff1-129">Sottocategoria o sottoraggruppamento a cui appartiene la configurazione.</span><span class="sxs-lookup"><span data-stu-id="20ff1-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="20ff1-130">In molti casi qui vengono descritte capacità o funzionalità specifiche.</span><span class="sxs-lookup"><span data-stu-id="20ff1-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="20ff1-131">stringa</span><span class="sxs-lookup"><span data-stu-id="20ff1-131">string</span></span> | <span data-ttu-id="20ff1-132">Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10)</span><span class="sxs-lookup"><span data-stu-id="20ff1-132">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="20ff1-133">booleano</span><span class="sxs-lookup"><span data-stu-id="20ff1-133">boolean</span></span> | <span data-ttu-id="20ff1-134">Indica se la configurazione o i criteri sono configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="20ff1-134">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="20ff1-135">boolean</span><span class="sxs-lookup"><span data-stu-id="20ff1-135">boolean</span></span> | <span data-ttu-id="20ff1-136">Indica se la configurazione o il criterio si applica al dispositivo</span><span class="sxs-lookup"><span data-stu-id="20ff1-136">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="20ff1-137">stringa</span><span class="sxs-lookup"><span data-stu-id="20ff1-137">string</span></span> | <span data-ttu-id="20ff1-138">Informazioni contestuali aggiuntive sulla configurazione o sui criteri</span><span class="sxs-lookup"><span data-stu-id="20ff1-138">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="20ff1-139">boolean</span><span class="sxs-lookup"><span data-stu-id="20ff1-139">boolean</span></span> | <span data-ttu-id="20ff1-140">Indica se l'impatto dell'utente sarà negativo se viene applicata la configurazione o il criterio</span><span class="sxs-lookup"><span data-stu-id="20ff1-140">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="20ff1-141">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="20ff1-141">Related topics</span></span>

- [<span data-ttu-id="20ff1-142">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="20ff1-142">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="20ff1-143">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="20ff1-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="20ff1-144">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="20ff1-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="20ff1-145">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="20ff1-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="20ff1-146">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="20ff1-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="20ff1-147">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="20ff1-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="20ff1-148">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="20ff1-148">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)