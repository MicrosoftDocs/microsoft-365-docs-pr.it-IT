---
title: La tabella DeviceTvmSoftwareVulnerabilitiesKB nello schema di ricerca avanzata
description: Informazioni sulle vulnerabilità del software monitorate dalla Gestione delle minacce e delle vulnerabilità nella tabella DeviceTvmSoftwareVulnerabilitiesKB dello schema di ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, schema, riferimento, kusto, tabella, colonna, tipo di dati, descrizione, & gestione delle vulnerabilità delle minacce, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023798"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="a0bf6-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="a0bf6-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a0bf6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a0bf6-105">**Applies to:**</span></span>
- <span data-ttu-id="a0bf6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a0bf6-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="a0bf6-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a0bf6-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="a0bf6-108">La tabella `DeviceTvmSoftwareVulnerabilitiesKB` nello schema di ricerca avanzata contiene l'elenco delle vulnerabilità per le quali [Gestione delle minacce e delle vulnerabilità](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) valuta i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="a0bf6-108">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="a0bf6-109">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="a0bf6-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="a0bf6-110">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a0bf6-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a0bf6-111">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="a0bf6-111">Column name</span></span> | <span data-ttu-id="a0bf6-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a0bf6-112">Data type</span></span> | <span data-ttu-id="a0bf6-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0bf6-113">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="a0bf6-114">stringa</span><span class="sxs-lookup"><span data-stu-id="a0bf6-114">string</span></span> | <span data-ttu-id="a0bf6-115">Identificatore univoco assegnato alla vulnerabilità di sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE)</span><span class="sxs-lookup"><span data-stu-id="a0bf6-115">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="a0bf6-116">stringa</span><span class="sxs-lookup"><span data-stu-id="a0bf6-116">string</span></span> | <span data-ttu-id="a0bf6-117">Punteggio di gravità assegnato alla vulnerabilità di sicurezza secondo il Sistema di punteggio della vulnerabilità comune (CVSS)</span><span class="sxs-lookup"><span data-stu-id="a0bf6-117">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="a0bf6-118">boolean</span><span class="sxs-lookup"><span data-stu-id="a0bf6-118">boolean</span></span> | <span data-ttu-id="a0bf6-119">Indica se il codice di sfruttamento della vulnerabilità è disponibile pubblicamente</span><span class="sxs-lookup"><span data-stu-id="a0bf6-119">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="a0bf6-120">stringa</span><span class="sxs-lookup"><span data-stu-id="a0bf6-120">string</span></span> | <span data-ttu-id="a0bf6-121">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dal panorama delle minacce</span><span class="sxs-lookup"><span data-stu-id="a0bf6-121">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="a0bf6-122">datetime</span><span class="sxs-lookup"><span data-stu-id="a0bf6-122">datetime</span></span> | <span data-ttu-id="a0bf6-123">Data e ora dell'ultima modifica dell'elemento o dei metadati correlati</span><span class="sxs-lookup"><span data-stu-id="a0bf6-123">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="a0bf6-124">datetime</span><span class="sxs-lookup"><span data-stu-id="a0bf6-124">datetime</span></span> | <span data-ttu-id="a0bf6-125">La vulnerabilità della data è stata resa pubblica</span><span class="sxs-lookup"><span data-stu-id="a0bf6-125">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="a0bf6-126">stringa</span><span class="sxs-lookup"><span data-stu-id="a0bf6-126">string</span></span> | <span data-ttu-id="a0bf6-127">Descrizione della vulnerabilità e dei rischi associati</span><span class="sxs-lookup"><span data-stu-id="a0bf6-127">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="a0bf6-128">stringa</span><span class="sxs-lookup"><span data-stu-id="a0bf6-128">string</span></span> | <span data-ttu-id="a0bf6-129">Elenco di tutti i prodotti software soggetti alla vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="a0bf6-129">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a0bf6-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a0bf6-130">Related topics</span></span>

- [<span data-ttu-id="a0bf6-131">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="a0bf6-131">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a0bf6-132">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="a0bf6-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a0bf6-133">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="a0bf6-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a0bf6-134">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="a0bf6-134">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a0bf6-135">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="a0bf6-135">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a0bf6-136">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="a0bf6-136">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="a0bf6-137">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="a0bf6-137">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)