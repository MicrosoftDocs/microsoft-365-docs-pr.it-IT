---
title: La tabella DeviceTvmSoftwareVulnerabilitiesKB nello schema di ricerca avanzata
description: Informazioni sulle vulnerabilità del software monitorate dalla Gestione delle minacce e delle vulnerabilità nella tabella DeviceTvmSoftwareVulnerabilitiesKB dello schema di ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062885"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="b55e1-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="b55e1-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b55e1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b55e1-105">**Applies to:**</span></span>
- [<span data-ttu-id="b55e1-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b55e1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="b55e1-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b55e1-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b55e1-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b55e1-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b55e1-109">La tabella `DeviceTvmSoftwareVulnerabilitiesKB` nello schema di ricerca avanzata contiene l'elenco delle vulnerabilità per le quali [Gestione delle minacce e delle vulnerabilità](next-gen-threat-and-vuln-mgt.md) valuta i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b55e1-109">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) assesses devices for.</span></span> <span data-ttu-id="b55e1-110">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="b55e1-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="b55e1-111">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b55e1-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="b55e1-112">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b55e1-112">Column name</span></span> | <span data-ttu-id="b55e1-113">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b55e1-113">Data type</span></span> | <span data-ttu-id="b55e1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b55e1-114">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="b55e1-115">stringa</span><span class="sxs-lookup"><span data-stu-id="b55e1-115">string</span></span> | <span data-ttu-id="b55e1-116">Identificatore univoco assegnato alla vulnerabilità di sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE)</span><span class="sxs-lookup"><span data-stu-id="b55e1-116">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="b55e1-117">stringa</span><span class="sxs-lookup"><span data-stu-id="b55e1-117">string</span></span> | <span data-ttu-id="b55e1-118">Punteggio di gravità assegnato alla vulnerabilità di sicurezza secondo il Sistema di punteggio della vulnerabilità comune (CVSS)</span><span class="sxs-lookup"><span data-stu-id="b55e1-118">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="b55e1-119">boolean</span><span class="sxs-lookup"><span data-stu-id="b55e1-119">boolean</span></span> | <span data-ttu-id="b55e1-120">Indica se il codice di sfruttamento della vulnerabilità è disponibile pubblicamente</span><span class="sxs-lookup"><span data-stu-id="b55e1-120">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="b55e1-121">stringa</span><span class="sxs-lookup"><span data-stu-id="b55e1-121">string</span></span> | <span data-ttu-id="b55e1-122">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dal panorama delle minacce</span><span class="sxs-lookup"><span data-stu-id="b55e1-122">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="b55e1-123">datetime</span><span class="sxs-lookup"><span data-stu-id="b55e1-123">datetime</span></span> | <span data-ttu-id="b55e1-124">Data e ora dell'ultima modifica dell'elemento o dei metadati correlati</span><span class="sxs-lookup"><span data-stu-id="b55e1-124">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="b55e1-125">datetime</span><span class="sxs-lookup"><span data-stu-id="b55e1-125">datetime</span></span> | <span data-ttu-id="b55e1-126">La vulnerabilità della data è stata resa pubblica</span><span class="sxs-lookup"><span data-stu-id="b55e1-126">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="b55e1-127">stringa</span><span class="sxs-lookup"><span data-stu-id="b55e1-127">string</span></span> | <span data-ttu-id="b55e1-128">Descrizione della vulnerabilità e dei rischi associati</span><span class="sxs-lookup"><span data-stu-id="b55e1-128">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="b55e1-129">stringa</span><span class="sxs-lookup"><span data-stu-id="b55e1-129">string</span></span> | <span data-ttu-id="b55e1-130">Elenco di tutti i prodotti software soggetti alla vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="b55e1-130">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b55e1-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b55e1-131">Related topics</span></span>

- [<span data-ttu-id="b55e1-132">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="b55e1-132">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b55e1-133">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="b55e1-133">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b55e1-134">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="b55e1-134">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="b55e1-135">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="b55e1-135">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
