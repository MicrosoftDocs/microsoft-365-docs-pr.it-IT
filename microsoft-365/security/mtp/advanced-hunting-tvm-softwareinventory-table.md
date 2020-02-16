---
title: Tabella DeviceTvmSoftwareInventoryVulnerabilities nello schema per Ricerca avanzata
description: Informazioni su un inventario si software nel dispositivo e sulle loro vulnerabilità nella tabella DeviceTvmSoftwareInventoryVulnerabilities dello schema per Ricerca avanzata.
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, Threat & vulnerabilità di gestione, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3ed9cce1c85dc924762be4408c670f13f318ca02
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087915"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="2c7a8-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="2c7a8-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="2c7a8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2c7a8-105">**Applies to:**</span></span>
- <span data-ttu-id="2c7a8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2c7a8-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2c7a8-107">La `DeviceTvmSoftwareInventoryVulnerabilities` tabella nello schema per Ricerca avanzata contiene l'inventario [Gestione delle minacce e delle vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) dei software sui dispositivi, oltre alle vulnerabilità di tali prodotti software.</span><span class="sxs-lookup"><span data-stu-id="2c7a8-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="2c7a8-108">La tabella include anche informazioni su sistema operativo, ID CVE ID e grado di vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="2c7a8-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="2c7a8-109">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="2c7a8-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="2c7a8-110">Per informazioni su altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2c7a8-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2c7a8-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="2c7a8-111">Column name</span></span> | <span data-ttu-id="2c7a8-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2c7a8-112">Data type</span></span> | <span data-ttu-id="2c7a8-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c7a8-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="2c7a8-114">stringa</span><span class="sxs-lookup"><span data-stu-id="2c7a8-114">string</span></span> | <span data-ttu-id="2c7a8-115">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="2c7a8-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2c7a8-116">stringa</span><span class="sxs-lookup"><span data-stu-id="2c7a8-116">string</span></span> | <span data-ttu-id="2c7a8-117">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="2c7a8-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="2c7a8-118">stringa</span><span class="sxs-lookup"><span data-stu-id="2c7a8-118">string</span></span> | <span data-ttu-id="2c7a8-119">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="2c7a8-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="2c7a8-120">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2c7a8-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="2c7a8-121">stringa</span><span class="sxs-lookup"><span data-stu-id="2c7a8-121">string</span></span> | <span data-ttu-id="2c7a8-122">Versione del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="2c7a8-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="2c7a8-123">stringa</span><span class="sxs-lookup"><span data-stu-id="2c7a8-123">string</span></span> | <span data-ttu-id="2c7a8-124">Architettura del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="2c7a8-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="2c7a8-125">stringa</span><span class="sxs-lookup"><span data-stu-id="2c7a8-125">string</span></span> | <span data-ttu-id="2c7a8-126">Nome del fornitore del software</span><span class="sxs-lookup"><span data-stu-id="2c7a8-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="2c7a8-127">stringa</span><span class="sxs-lookup"><span data-stu-id="2c7a8-127">string</span></span> | <span data-ttu-id="2c7a8-128">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="2c7a8-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="2c7a8-129">stringa</span><span class="sxs-lookup"><span data-stu-id="2c7a8-129">string</span></span> | <span data-ttu-id="2c7a8-130">Numero della versione del prodotto software</span><span class="sxs-lookup"><span data-stu-id="2c7a8-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="2c7a8-131">stringa</span><span class="sxs-lookup"><span data-stu-id="2c7a8-131">string</span></span> | <span data-ttu-id="2c7a8-132">Identificatore univoco assegnato alla vulnerabilità della sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE)</span><span class="sxs-lookup"><span data-stu-id="2c7a8-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="2c7a8-133">stringa</span><span class="sxs-lookup"><span data-stu-id="2c7a8-133">string</span></span> | <span data-ttu-id="2c7a8-134">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dalle possibili minacce</span><span class="sxs-lookup"><span data-stu-id="2c7a8-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="2c7a8-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2c7a8-135">Related topics</span></span>

- [<span data-ttu-id="2c7a8-136">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="2c7a8-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2c7a8-137">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="2c7a8-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2c7a8-138">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="2c7a8-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2c7a8-139">Ricerca delle minacce attraverso dispositivi e email</span><span class="sxs-lookup"><span data-stu-id="2c7a8-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2c7a8-140">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="2c7a8-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2c7a8-141">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="2c7a8-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2c7a8-142">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="2c7a8-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
