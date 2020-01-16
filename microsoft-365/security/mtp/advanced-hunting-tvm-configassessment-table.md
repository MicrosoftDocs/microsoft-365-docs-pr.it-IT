---
title: Tabella DeviceTvmSecureConfigurationAssessment nello schema di Ricerca avanzata
description: Informazioni sugli eventi di valutazione della sicurezza della Gestione delle minacce e della vulnerabilità nella tabella DeviceTvmSecureConfigurationAssessment dello schema di Ricerca avanzata. Questi eventi forniscono informazioni sul computer, oltre a dettagli relativi alla configurazione della sicurezza, all’impatto e a informazioni sulla conformità.
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, Threat & vulnerabilità di gestione, TVM, gestione dei dispositivi, configurazione della sicurezza, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3d58ba24aa3ad2226cfae3ee96a8f0ed3a1c9566
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210301"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="e8daa-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="e8daa-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="e8daa-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e8daa-106">**Applies to:**</span></span>
- <span data-ttu-id="e8daa-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e8daa-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e8daa-108">Ogni riga della tabella `DeviceTvmSecureConfigurationAssessment` contiene un evento di valutazione per una specifica configurazione di sicurezza della [Gestione delle minacce e della vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="e8daa-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="e8daa-109">Usare questo riferimento per controllare i risultati più recenti della valutazione e determinare se i dispositivi sono conformi.</span><span class="sxs-lookup"><span data-stu-id="e8daa-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="e8daa-110">Per informazioni su altre tabelle nello schema di Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="e8daa-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e8daa-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="e8daa-111">Column name</span></span> | <span data-ttu-id="e8daa-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e8daa-112">Data type</span></span> | <span data-ttu-id="e8daa-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8daa-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="e8daa-114">stringa</span><span class="sxs-lookup"><span data-stu-id="e8daa-114">string</span></span> | <span data-ttu-id="e8daa-115">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="e8daa-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e8daa-116">stringa</span><span class="sxs-lookup"><span data-stu-id="e8daa-116">string</span></span> | <span data-ttu-id="e8daa-117">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="e8daa-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="e8daa-118">stringa</span><span class="sxs-lookup"><span data-stu-id="e8daa-118">string</span></span> | <span data-ttu-id="e8daa-119">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="e8daa-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="e8daa-120">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="e8daa-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="e8daa-121">datetime</span><span class="sxs-lookup"><span data-stu-id="e8daa-121">datetime</span></span> | <span data-ttu-id="e8daa-122">Data e ora in cui è stato generato il record</span><span class="sxs-lookup"><span data-stu-id="e8daa-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="e8daa-123">stringa</span><span class="sxs-lookup"><span data-stu-id="e8daa-123">string</span></span> | <span data-ttu-id="e8daa-124">Identificatore univoco di una configurazione specifica</span><span class="sxs-lookup"><span data-stu-id="e8daa-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="e8daa-125">stringa</span><span class="sxs-lookup"><span data-stu-id="e8daa-125">string</span></span> | <span data-ttu-id="e8daa-126">Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="e8daa-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="e8daa-127">stringa</span><span class="sxs-lookup"><span data-stu-id="e8daa-127">string</span></span> | <span data-ttu-id="e8daa-128">Sottocategoria o sottoraggruppamento a cui appartiene la configurazione.</span><span class="sxs-lookup"><span data-stu-id="e8daa-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="e8daa-129">In molti casi qui vengono descritte capacità o funzionalità specifiche.</span><span class="sxs-lookup"><span data-stu-id="e8daa-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="e8daa-130">stringa</span><span class="sxs-lookup"><span data-stu-id="e8daa-130">string</span></span> | <span data-ttu-id="e8daa-131">Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10)</span><span class="sxs-lookup"><span data-stu-id="e8daa-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="e8daa-132">booleano</span><span class="sxs-lookup"><span data-stu-id="e8daa-132">boolean</span></span> | <span data-ttu-id="e8daa-133">Indica se la configurazione o i criteri sono configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="e8daa-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e8daa-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e8daa-134">Related topics</span></span>

- [<span data-ttu-id="e8daa-135">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="e8daa-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e8daa-136">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="e8daa-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e8daa-137">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="e8daa-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e8daa-138">Ricerca delle minacce attraverso dispositivi ed email</span><span class="sxs-lookup"><span data-stu-id="e8daa-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e8daa-139">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="e8daa-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e8daa-140">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="e8daa-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e8daa-141">Panoramica della Gestione delle minacce e della vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="e8daa-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
