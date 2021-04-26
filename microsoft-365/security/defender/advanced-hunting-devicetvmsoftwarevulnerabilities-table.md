---
title: Tabella DeviceTvmSoftwareVulnerabilities nello schema di ricerca avanzata
description: Informazioni sulle vulnerabilità software riscontrate nei dispositivi e sull'elenco degli aggiornamenti della sicurezza disponibili che affrontano ogni vulnerabilità nella tabella DeviceTvmSoftwareVulnerabilities dello schema di ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 17faffc45cfd1f472dec3f423681aaa3f64944a3
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023810"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="efd90-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="efd90-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="efd90-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="efd90-105">**Applies to:**</span></span>
- <span data-ttu-id="efd90-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="efd90-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="efd90-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="efd90-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="efd90-108">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="efd90-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="efd90-109">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="efd90-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="efd90-110">La tabella nello schema di ricerca avanzata contiene l'& di gestione delle & delle vulnerabilità `DeviceTvmSoftwareVulnerabilities` nei prodotti software installati. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="efd90-110">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="efd90-111">La tabella include anche informazioni su sistema operativo, ID CVE ID e grado di vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="efd90-111">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="efd90-112">È possibile utilizzare questa tabella, ad esempio, per cercare eventi che coinvolgono dispositivi con gravi vulnerabilità nel software.</span><span class="sxs-lookup"><span data-stu-id="efd90-112">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="efd90-113">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="efd90-113">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="efd90-114">Le `DeviceTvmSoftwareInventory` tabelle e hanno `DeviceTvmSoftwareVulnerabilities` sostituito la `DeviceTvmSoftwareInventoryVulnerabilities` tabella.</span><span class="sxs-lookup"><span data-stu-id="efd90-114">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="efd90-115">Insieme, le prime due tabelle includono più colonne che puoi usare per informare le attività di gestione della vulnerablità o cercare dispositivi vulnerabili.</span><span class="sxs-lookup"><span data-stu-id="efd90-115">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="efd90-116">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="efd90-116">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="efd90-117">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="efd90-117">Column name</span></span> | <span data-ttu-id="efd90-118">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="efd90-118">Data type</span></span> | <span data-ttu-id="efd90-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efd90-119">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="efd90-120">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-120">string</span></span> | <span data-ttu-id="efd90-121">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="efd90-121">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="efd90-122">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-122">string</span></span> | <span data-ttu-id="efd90-123">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="efd90-123">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="efd90-124">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-124">string</span></span> | <span data-ttu-id="efd90-125">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="efd90-125">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="efd90-126">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="efd90-126">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="efd90-127">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-127">string</span></span> | <span data-ttu-id="efd90-128">Versione del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="efd90-128">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="efd90-129">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-129">string</span></span> | <span data-ttu-id="efd90-130">Architettura del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="efd90-130">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="efd90-131">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-131">string</span></span> | <span data-ttu-id="efd90-132">Nome del fornitore del software</span><span class="sxs-lookup"><span data-stu-id="efd90-132">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="efd90-133">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-133">string</span></span> | <span data-ttu-id="efd90-134">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="efd90-134">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="efd90-135">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-135">string</span></span> | <span data-ttu-id="efd90-136">Numero della versione del prodotto software</span><span class="sxs-lookup"><span data-stu-id="efd90-136">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="efd90-137">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-137">string</span></span> | <span data-ttu-id="efd90-138">Identificatore univoco assegnato alla vulnerabilità di sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE)</span><span class="sxs-lookup"><span data-stu-id="efd90-138">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="efd90-139">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-139">string</span></span> | <span data-ttu-id="efd90-140">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dalle possibili minacce</span><span class="sxs-lookup"><span data-stu-id="efd90-140">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="efd90-141">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-141">string</span></span> | <span data-ttu-id="efd90-142">Nome o descrizione dell'aggiornamento della sicurezza fornito dal fornitore del software per risolvere la vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="efd90-142">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="efd90-143">stringa</span><span class="sxs-lookup"><span data-stu-id="efd90-143">string</span></span> | <span data-ttu-id="efd90-144">Identificatore degli aggiornamenti della sicurezza applicabili o dell'identificatore per gli articoli della Knowledge Base (KB) corrispondenti</span><span class="sxs-lookup"><span data-stu-id="efd90-144">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="efd90-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="efd90-145">Related topics</span></span>

- [<span data-ttu-id="efd90-146">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="efd90-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="efd90-147">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="efd90-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="efd90-148">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="efd90-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="efd90-149">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="efd90-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="efd90-150">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="efd90-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="efd90-151">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="efd90-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="efd90-152">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="efd90-152">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)