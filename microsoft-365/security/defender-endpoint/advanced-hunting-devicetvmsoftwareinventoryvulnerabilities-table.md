---
title: Tabella DeviceTvmSoftwareInventoryVulnerabilities nello schema per Ricerca avanzata
description: Informazioni su un inventario si software nel dispositivo e sulle loro vulnerabilità nella tabella DeviceTvmSoftwareInventoryVulnerabilities dello schema per Ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163460"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="5d070-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="5d070-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5d070-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5d070-105">**Applies to:**</span></span>

- [<span data-ttu-id="5d070-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5d070-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="5d070-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5d070-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5d070-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5d070-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="5d070-109">La `DeviceTvmSoftwareInventoryVulnerabilities` tabella nello schema per Ricerca avanzata contiene l'inventario [Gestione delle minacce e delle vulnerabilità](next-gen-threat-and-vuln-mgt.md) dei software sui dispositivi, oltre alle vulnerabilità di tali prodotti software.</span><span class="sxs-lookup"><span data-stu-id="5d070-109">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="5d070-110">La tabella include anche informazioni su sistema operativo, ID CVE ID e grado di vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="5d070-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="5d070-111">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="5d070-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="5d070-112">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="5d070-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="5d070-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="5d070-113">Column name</span></span> | <span data-ttu-id="5d070-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="5d070-114">Data type</span></span> | <span data-ttu-id="5d070-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d070-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="5d070-116">stringa</span><span class="sxs-lookup"><span data-stu-id="5d070-116">string</span></span> | <span data-ttu-id="5d070-117">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="5d070-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="5d070-118">stringa</span><span class="sxs-lookup"><span data-stu-id="5d070-118">string</span></span> | <span data-ttu-id="5d070-119">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="5d070-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="5d070-120">stringa</span><span class="sxs-lookup"><span data-stu-id="5d070-120">string</span></span> | <span data-ttu-id="5d070-121">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5d070-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="5d070-122">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="5d070-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="5d070-123">stringa</span><span class="sxs-lookup"><span data-stu-id="5d070-123">string</span></span> | <span data-ttu-id="5d070-124">Versione del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="5d070-124">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="5d070-125">stringa</span><span class="sxs-lookup"><span data-stu-id="5d070-125">string</span></span> | <span data-ttu-id="5d070-126">Architettura del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="5d070-126">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="5d070-127">stringa</span><span class="sxs-lookup"><span data-stu-id="5d070-127">string</span></span> | <span data-ttu-id="5d070-128">Nome del fornitore del software</span><span class="sxs-lookup"><span data-stu-id="5d070-128">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="5d070-129">stringa</span><span class="sxs-lookup"><span data-stu-id="5d070-129">string</span></span> | <span data-ttu-id="5d070-130">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="5d070-130">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="5d070-131">stringa</span><span class="sxs-lookup"><span data-stu-id="5d070-131">string</span></span> | <span data-ttu-id="5d070-132">Numero della versione del prodotto software</span><span class="sxs-lookup"><span data-stu-id="5d070-132">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="5d070-133">stringa</span><span class="sxs-lookup"><span data-stu-id="5d070-133">string</span></span> | <span data-ttu-id="5d070-134">Identificatore univoco assegnato alla vulnerabilità di sicurezza nell'ambito del sistema Vulnerabilità ed esposizioni comuni (CVE)</span><span class="sxs-lookup"><span data-stu-id="5d070-134">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="5d070-135">stringa</span><span class="sxs-lookup"><span data-stu-id="5d070-135">string</span></span> | <span data-ttu-id="5d070-136">Livello di gravità assegnato alla vulnerabilità della sicurezza in base al Punteggio CVSS e ai fattori dinamici influenzati dalle possibili minacce</span><span class="sxs-lookup"><span data-stu-id="5d070-136">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="5d070-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5d070-137">Related topics</span></span>

- [<span data-ttu-id="5d070-138">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="5d070-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5d070-139">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="5d070-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5d070-140">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="5d070-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="5d070-141">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="5d070-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
