---
title: Tabella DeviceTvmSoftwareVulnerabilities nello schema di ricerca avanzata
description: Informazioni sulle vulnerabilità software riscontrate nei dispositivi e sull'elenco degli aggiornamenti della sicurezza disponibili che affrontano ogni vulnerabilità nella tabella DeviceTvmSoftwareVulnerabilities dello schema di ricerca avanzata.
keywords: ricerca avanzata, ricerca di minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 6911031e3caa27eff80bb83a3a88643cac2b6918
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065925"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="81e86-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="81e86-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="81e86-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="81e86-105">**Applies to:**</span></span>
- <span data-ttu-id="81e86-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81e86-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="81e86-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="81e86-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="81e86-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="81e86-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="81e86-109">La tabella nello schema di ricerca avanzata contiene l'& di gestione delle & delle vulnerabilità `DeviceTvmSoftwareVulnerabilities` nei prodotti software installati. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="81e86-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="81e86-110">La tabella include anche informazioni su sistema operativo, ID CVE ID e grado di vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="81e86-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="81e86-111">È possibile utilizzare questa tabella, ad esempio, per cercare eventi che coinvolgono dispositivi con gravi vulnerabilità nel software.</span><span class="sxs-lookup"><span data-stu-id="81e86-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="81e86-112">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="81e86-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="81e86-113">Le `DeviceTvmSoftwareInventory` tabelle e hanno `DeviceTvmSoftwareVulnerabilities` sostituito la `DeviceTvmSoftwareInventoryVulnerabilities` tabella.</span><span class="sxs-lookup"><span data-stu-id="81e86-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="81e86-114">Insieme, le prime due tabelle includono più colonne che puoi usare per informare le attività di gestione della vulnerablità o cercare dispositivi vulnerabili.</span><span class="sxs-lookup"><span data-stu-id="81e86-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="81e86-115">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="81e86-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="81e86-116">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="81e86-116">Column name</span></span> | <span data-ttu-id="81e86-117">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="81e86-117">Data type</span></span> | <span data-ttu-id="81e86-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81e86-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="81e86-119">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-119">string</span></span> | <span data-ttu-id="81e86-120">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="81e86-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="81e86-121">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-121">string</span></span> | <span data-ttu-id="81e86-122">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="81e86-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="81e86-123">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-123">string</span></span> | <span data-ttu-id="81e86-124">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="81e86-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="81e86-125">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="81e86-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="81e86-126">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-126">string</span></span> | <span data-ttu-id="81e86-127">Versione del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="81e86-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="81e86-128">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-128">string</span></span> | <span data-ttu-id="81e86-129">Architettura del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="81e86-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="81e86-130">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-130">string</span></span> | <span data-ttu-id="81e86-131">Nome del fornitore del software</span><span class="sxs-lookup"><span data-stu-id="81e86-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="81e86-132">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-132">string</span></span> | <span data-ttu-id="81e86-133">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="81e86-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="81e86-134">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-134">string</span></span> | <span data-ttu-id="81e86-135">Numero della versione del prodotto software</span><span class="sxs-lookup"><span data-stu-id="81e86-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="81e86-136">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-136">string</span></span> | <span data-ttu-id="81e86-137">Identificatore univoco assegnato alla vulnerabilità di sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE)</span><span class="sxs-lookup"><span data-stu-id="81e86-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="81e86-138">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-138">string</span></span> | <span data-ttu-id="81e86-139">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dalle possibili minacce</span><span class="sxs-lookup"><span data-stu-id="81e86-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="81e86-140">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-140">string</span></span> | <span data-ttu-id="81e86-141">Nome o descrizione dell'aggiornamento della sicurezza fornito dal fornitore del software per risolvere la vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="81e86-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="81e86-142">stringa</span><span class="sxs-lookup"><span data-stu-id="81e86-142">string</span></span> | <span data-ttu-id="81e86-143">Identificatore degli aggiornamenti della sicurezza applicabili o dell'identificatore per gli articoli della Knowledge Base (KB) corrispondenti</span><span class="sxs-lookup"><span data-stu-id="81e86-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="81e86-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="81e86-144">Related topics</span></span>

- [<span data-ttu-id="81e86-145">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="81e86-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="81e86-146">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="81e86-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="81e86-147">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="81e86-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="81e86-148">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="81e86-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="81e86-149">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="81e86-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="81e86-150">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="81e86-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="81e86-151">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="81e86-151">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)