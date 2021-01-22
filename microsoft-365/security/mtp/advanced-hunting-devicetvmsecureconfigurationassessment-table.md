---
title: Tabella DeviceTvmSecureConfigurationAssessment nello schema di Ricerca avanzata
description: Informazioni sugli eventi di valutazione della sicurezza nella tabella DeviceTvmSecureConfigurationAssessment dello schema di ricerca avanzata. Questi eventi di & di gestione delle vulnerabilità forniscono informazioni sul dispositivo, nonché dettagli sulla configurazione della sicurezza, impatto e informazioni sulla conformità.
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, configurazione della sicurezza, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 6924bbc7a88a4f32d97534c72a180a1f1c4f7db6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931099"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="ba0b8-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="ba0b8-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ba0b8-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ba0b8-106">**Applies to:**</span></span>
- <span data-ttu-id="ba0b8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba0b8-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="ba0b8-108">Ogni riga della tabella `DeviceTvmSecureConfigurationAssessment` contiene un evento di valutazione per una specifica configurazione di sicurezza della [Gestione delle minacce e della vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="ba0b8-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="ba0b8-109">Usare questo riferimento per controllare i risultati più recenti della valutazione e determinare se i dispositivi sono conformi.</span><span class="sxs-lookup"><span data-stu-id="ba0b8-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="ba0b8-110">Per informazioni su altre tabelle nello schema di Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ba0b8-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ba0b8-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="ba0b8-111">Column name</span></span> | <span data-ttu-id="ba0b8-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ba0b8-112">Data type</span></span> | <span data-ttu-id="ba0b8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba0b8-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="ba0b8-114">stringa</span><span class="sxs-lookup"><span data-stu-id="ba0b8-114">string</span></span> | <span data-ttu-id="ba0b8-115">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="ba0b8-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ba0b8-116">stringa</span><span class="sxs-lookup"><span data-stu-id="ba0b8-116">string</span></span> | <span data-ttu-id="ba0b8-117">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba0b8-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="ba0b8-118">stringa</span><span class="sxs-lookup"><span data-stu-id="ba0b8-118">string</span></span> | <span data-ttu-id="ba0b8-119">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba0b8-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="ba0b8-120">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="ba0b8-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="ba0b8-121">datetime</span><span class="sxs-lookup"><span data-stu-id="ba0b8-121">datetime</span></span> | <span data-ttu-id="ba0b8-122">Data e ora in cui è stato generato il record</span><span class="sxs-lookup"><span data-stu-id="ba0b8-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="ba0b8-123">stringa</span><span class="sxs-lookup"><span data-stu-id="ba0b8-123">string</span></span> | <span data-ttu-id="ba0b8-124">Identificatore univoco di una configurazione specifica</span><span class="sxs-lookup"><span data-stu-id="ba0b8-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="ba0b8-125">stringa</span><span class="sxs-lookup"><span data-stu-id="ba0b8-125">string</span></span> | <span data-ttu-id="ba0b8-126">Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ba0b8-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="ba0b8-127">stringa</span><span class="sxs-lookup"><span data-stu-id="ba0b8-127">string</span></span> | <span data-ttu-id="ba0b8-128">Sottocategoria o sottoraggruppamento a cui appartiene la configurazione.</span><span class="sxs-lookup"><span data-stu-id="ba0b8-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="ba0b8-129">In molti casi qui vengono descritte capacità o funzionalità specifiche.</span><span class="sxs-lookup"><span data-stu-id="ba0b8-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="ba0b8-130">stringa</span><span class="sxs-lookup"><span data-stu-id="ba0b8-130">string</span></span> | <span data-ttu-id="ba0b8-131">Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10)</span><span class="sxs-lookup"><span data-stu-id="ba0b8-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="ba0b8-132">booleano</span><span class="sxs-lookup"><span data-stu-id="ba0b8-132">boolean</span></span> | <span data-ttu-id="ba0b8-133">Indica se la configurazione o i criteri sono configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="ba0b8-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="ba0b8-134">boolean</span><span class="sxs-lookup"><span data-stu-id="ba0b8-134">boolean</span></span> | <span data-ttu-id="ba0b8-135">Indica se la configurazione o il criterio si applica al dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba0b8-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="ba0b8-136">stringa</span><span class="sxs-lookup"><span data-stu-id="ba0b8-136">string</span></span> | <span data-ttu-id="ba0b8-137">Informazioni contestuali aggiuntive sulla configurazione o sui criteri</span><span class="sxs-lookup"><span data-stu-id="ba0b8-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="ba0b8-138">boolean</span><span class="sxs-lookup"><span data-stu-id="ba0b8-138">boolean</span></span> | <span data-ttu-id="ba0b8-139">Indica se l'applicazione della configurazione o del criterio avrà un impatto sull'utente</span><span class="sxs-lookup"><span data-stu-id="ba0b8-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ba0b8-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ba0b8-140">Related topics</span></span>

- [<span data-ttu-id="ba0b8-141">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="ba0b8-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ba0b8-142">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="ba0b8-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ba0b8-143">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="ba0b8-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ba0b8-144">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="ba0b8-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ba0b8-145">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="ba0b8-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ba0b8-146">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="ba0b8-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ba0b8-147">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="ba0b8-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
