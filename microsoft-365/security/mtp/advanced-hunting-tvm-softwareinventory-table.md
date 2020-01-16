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
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d3b85bcbc2cb65cc434c7af0ba078bd835d8203f
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210498"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="b08aa-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="b08aa-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="b08aa-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b08aa-105">**Applies to:**</span></span>
- <span data-ttu-id="b08aa-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b08aa-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b08aa-107">La `DeviceTvmSoftwareInventoryVulnerabilities` tabella nello schema per Ricerca avanzata contiene l'inventario [Gestione delle minacce e delle vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) dei software sui dispositivi, oltre alle vulnerabilità di tali prodotti software.</span><span class="sxs-lookup"><span data-stu-id="b08aa-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="b08aa-108">La tabella include anche informazioni su sistema operativo, ID CVE ID e grado di vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="b08aa-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="b08aa-109">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="b08aa-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="b08aa-110">Per informazioni su altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b08aa-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b08aa-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b08aa-111">Column name</span></span> | <span data-ttu-id="b08aa-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b08aa-112">Data type</span></span> | <span data-ttu-id="b08aa-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b08aa-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="b08aa-114">stringa</span><span class="sxs-lookup"><span data-stu-id="b08aa-114">string</span></span> | <span data-ttu-id="b08aa-115">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="b08aa-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b08aa-116">stringa</span><span class="sxs-lookup"><span data-stu-id="b08aa-116">string</span></span> | <span data-ttu-id="b08aa-117">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="b08aa-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="b08aa-118">stringa</span><span class="sxs-lookup"><span data-stu-id="b08aa-118">string</span></span> | <span data-ttu-id="b08aa-119">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="b08aa-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b08aa-120">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b08aa-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="b08aa-121">stringa</span><span class="sxs-lookup"><span data-stu-id="b08aa-121">string</span></span> | <span data-ttu-id="b08aa-122">Versione del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="b08aa-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="b08aa-123">stringa</span><span class="sxs-lookup"><span data-stu-id="b08aa-123">string</span></span> | <span data-ttu-id="b08aa-124">Architettura del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="b08aa-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="b08aa-125">stringa</span><span class="sxs-lookup"><span data-stu-id="b08aa-125">string</span></span> | <span data-ttu-id="b08aa-126">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dalle possibili minacce</span><span class="sxs-lookup"><span data-stu-id="b08aa-126">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `SoftwareName` | <span data-ttu-id="b08aa-127">stringa</span><span class="sxs-lookup"><span data-stu-id="b08aa-127">string</span></span> | <span data-ttu-id="b08aa-128">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="b08aa-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="b08aa-129">stringa</span><span class="sxs-lookup"><span data-stu-id="b08aa-129">string</span></span> | <span data-ttu-id="b08aa-130">Numero della versione del prodotto software</span><span class="sxs-lookup"><span data-stu-id="b08aa-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="b08aa-131">stringa</span><span class="sxs-lookup"><span data-stu-id="b08aa-131">string</span></span> | <span data-ttu-id="b08aa-132">Identificatore univoco assegnato alla vulnerabilità della sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE)</span><span class="sxs-lookup"><span data-stu-id="b08aa-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="b08aa-133">stringa</span><span class="sxs-lookup"><span data-stu-id="b08aa-133">string</span></span> | <span data-ttu-id="b08aa-134">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dalle possibili minacce</span><span class="sxs-lookup"><span data-stu-id="b08aa-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="b08aa-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b08aa-135">Related topics</span></span>

- [<span data-ttu-id="b08aa-136">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="b08aa-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b08aa-137">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="b08aa-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b08aa-138">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="b08aa-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b08aa-139">Ricerca delle minacce attraverso dispositivi e email</span><span class="sxs-lookup"><span data-stu-id="b08aa-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b08aa-140">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="b08aa-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b08aa-141">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="b08aa-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b08aa-142">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="b08aa-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
