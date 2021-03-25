---
title: Tabella DeviceTvmSoftwareVulnerabilities nello schema di ricerca avanzata
description: Informazioni sulle vulnerabilità software riscontrate nei dispositivi e sull'elenco degli aggiornamenti della sicurezza disponibili che affrontano ogni vulnerabilità nella tabella DeviceTvmSoftwareVulnerabilities dello schema di ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067997"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="b19d4-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="b19d4-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b19d4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b19d4-105">**Applies to:**</span></span>
- [<span data-ttu-id="b19d4-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="b19d4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="b19d4-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b19d4-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b19d4-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b19d4-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b19d4-109">La tabella nello schema di ricerca avanzata contiene l'& di gestione delle & delle vulnerabilità `DeviceTvmSoftwareVulnerabilities` nei prodotti software installati. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="b19d4-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="b19d4-110">La tabella include anche informazioni su sistema operativo, ID CVE ID e grado di vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="b19d4-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="b19d4-111">È possibile utilizzare questa tabella, ad esempio, per cercare eventi che coinvolgono dispositivi con gravi vulnerabilità nel software.</span><span class="sxs-lookup"><span data-stu-id="b19d4-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="b19d4-112">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="b19d4-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="b19d4-113">Le `DeviceTvmSoftwareInventory` tabelle e hanno `DeviceTvmSoftwareVulnerabilities` sostituito la `DeviceTvmSoftwareInventoryVulnerabilities` tabella.</span><span class="sxs-lookup"><span data-stu-id="b19d4-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="b19d4-114">Insieme, le prime due tabelle includono più colonne che è possibile utilizzare per informare le attività di gestione delle vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="b19d4-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="b19d4-115">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="b19d4-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="b19d4-116">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b19d4-116">Column name</span></span> | <span data-ttu-id="b19d4-117">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b19d4-117">Data type</span></span> | <span data-ttu-id="b19d4-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b19d4-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="b19d4-119">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-119">string</span></span> | <span data-ttu-id="b19d4-120">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="b19d4-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b19d4-121">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-121">string</span></span> | <span data-ttu-id="b19d4-122">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="b19d4-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="b19d4-123">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-123">string</span></span> | <span data-ttu-id="b19d4-124">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b19d4-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="b19d4-125">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b19d4-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="b19d4-126">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-126">string</span></span> | <span data-ttu-id="b19d4-127">Versione del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="b19d4-127">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="b19d4-128">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-128">string</span></span> | <span data-ttu-id="b19d4-129">Architettura del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="b19d4-129">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="b19d4-130">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-130">string</span></span> | <span data-ttu-id="b19d4-131">Nome del fornitore del software</span><span class="sxs-lookup"><span data-stu-id="b19d4-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="b19d4-132">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-132">string</span></span> | <span data-ttu-id="b19d4-133">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="b19d4-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="b19d4-134">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-134">string</span></span> | <span data-ttu-id="b19d4-135">Numero della versione del prodotto software</span><span class="sxs-lookup"><span data-stu-id="b19d4-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="b19d4-136">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-136">string</span></span> | <span data-ttu-id="b19d4-137">Identificatore univoco assegnato alla vulnerabilità di sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE)</span><span class="sxs-lookup"><span data-stu-id="b19d4-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="b19d4-138">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-138">string</span></span> | <span data-ttu-id="b19d4-139">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dalle possibili minacce</span><span class="sxs-lookup"><span data-stu-id="b19d4-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="b19d4-140">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-140">string</span></span> | <span data-ttu-id="b19d4-141">Nome o descrizione dell'aggiornamento della sicurezza fornito dal fornitore del software per risolvere la vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="b19d4-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="b19d4-142">stringa</span><span class="sxs-lookup"><span data-stu-id="b19d4-142">string</span></span> | <span data-ttu-id="b19d4-143">Identificatore degli aggiornamenti della sicurezza applicabili o dell'identificatore per gli articoli della Knowledge Base (KB) corrispondenti</span><span class="sxs-lookup"><span data-stu-id="b19d4-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="b19d4-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b19d4-144">Related topics</span></span>

- [<span data-ttu-id="b19d4-145">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="b19d4-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b19d4-146">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="b19d4-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b19d4-147">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="b19d4-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="b19d4-148">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="b19d4-148">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
