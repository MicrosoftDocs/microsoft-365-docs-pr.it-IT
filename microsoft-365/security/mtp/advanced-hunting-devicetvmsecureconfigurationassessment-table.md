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
ms.openlocfilehash: bfe63397d194567a7d71de703363083d2fd4fe75
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847609"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="5da50-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="5da50-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5da50-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5da50-106">**Applies to:**</span></span>
- <span data-ttu-id="5da50-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5da50-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="5da50-108">Ogni riga della tabella `DeviceTvmSecureConfigurationAssessment` contiene un evento di valutazione per una specifica configurazione di sicurezza della [Gestione delle minacce e della vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="5da50-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="5da50-109">Usare questo riferimento per controllare i risultati più recenti della valutazione e determinare se i dispositivi sono conformi.</span><span class="sxs-lookup"><span data-stu-id="5da50-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="5da50-110">Per informazioni su altre tabelle nello schema di Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="5da50-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5da50-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5da50-111">Column name</span></span> | <span data-ttu-id="5da50-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5da50-112">Data type</span></span> | <span data-ttu-id="5da50-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5da50-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="5da50-114">stringa</span><span class="sxs-lookup"><span data-stu-id="5da50-114">string</span></span> | <span data-ttu-id="5da50-115">Identificatore univoco per il dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="5da50-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5da50-116">stringa</span><span class="sxs-lookup"><span data-stu-id="5da50-116">string</span></span> | <span data-ttu-id="5da50-117">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="5da50-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="5da50-118">stringa</span><span class="sxs-lookup"><span data-stu-id="5da50-118">string</span></span> | <span data-ttu-id="5da50-119">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5da50-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="5da50-120">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="5da50-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="5da50-121">datetime</span><span class="sxs-lookup"><span data-stu-id="5da50-121">datetime</span></span> | <span data-ttu-id="5da50-122">Data e ora in cui è stato generato il record</span><span class="sxs-lookup"><span data-stu-id="5da50-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="5da50-123">stringa</span><span class="sxs-lookup"><span data-stu-id="5da50-123">string</span></span> | <span data-ttu-id="5da50-124">Identificatore univoco di una configurazione specifica</span><span class="sxs-lookup"><span data-stu-id="5da50-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="5da50-125">stringa</span><span class="sxs-lookup"><span data-stu-id="5da50-125">string</span></span> | <span data-ttu-id="5da50-126">Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="5da50-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="5da50-127">stringa</span><span class="sxs-lookup"><span data-stu-id="5da50-127">string</span></span> | <span data-ttu-id="5da50-128">Sottocategoria o sottoraggruppamento a cui appartiene la configurazione.</span><span class="sxs-lookup"><span data-stu-id="5da50-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="5da50-129">In molti casi qui vengono descritte capacità o funzionalità specifiche.</span><span class="sxs-lookup"><span data-stu-id="5da50-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="5da50-130">stringa</span><span class="sxs-lookup"><span data-stu-id="5da50-130">string</span></span> | <span data-ttu-id="5da50-131">Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10)</span><span class="sxs-lookup"><span data-stu-id="5da50-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="5da50-132">booleano</span><span class="sxs-lookup"><span data-stu-id="5da50-132">boolean</span></span> | <span data-ttu-id="5da50-133">Indica se la configurazione o i criteri sono configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="5da50-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="5da50-134">boolean</span><span class="sxs-lookup"><span data-stu-id="5da50-134">boolean</span></span> | <span data-ttu-id="5da50-135">Indica se la configurazione o il criterio si applica al dispositivo</span><span class="sxs-lookup"><span data-stu-id="5da50-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="5da50-136">stringa</span><span class="sxs-lookup"><span data-stu-id="5da50-136">string</span></span> | <span data-ttu-id="5da50-137">Ulteriori informazioni contestuali sulla configurazione o sui criteri</span><span class="sxs-lookup"><span data-stu-id="5da50-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="5da50-138">boolean</span><span class="sxs-lookup"><span data-stu-id="5da50-138">boolean</span></span> | <span data-ttu-id="5da50-139">Indica se l'impatto dell'utente verrà applicato se la configurazione o il criterio vengono applicati</span><span class="sxs-lookup"><span data-stu-id="5da50-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5da50-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5da50-140">Related topics</span></span>

- [<span data-ttu-id="5da50-141">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="5da50-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5da50-142">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="5da50-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5da50-143">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="5da50-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5da50-144">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="5da50-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5da50-145">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="5da50-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5da50-146">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="5da50-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5da50-147">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="5da50-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
