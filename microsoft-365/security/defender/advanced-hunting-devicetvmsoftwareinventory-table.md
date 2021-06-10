---
title: Tabella DeviceTvmSoftwareInventory nello schema di ricerca avanzata
description: Informazioni sull'inventario del software nei dispositivi nella tabella DeviceTvmSoftwareInventory dello schema di ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, & gestione delle vulnerabilità delle minacce, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 5f82684ebb10b72ff83a6789c010f5ec9fa099e7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024230"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="bf379-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="bf379-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bf379-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="bf379-105">**Applies to:**</span></span>
- <span data-ttu-id="bf379-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf379-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="bf379-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="bf379-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="bf379-108">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="bf379-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bf379-109">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="bf379-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="bf379-110">La tabella nello schema di ricerca avanzata contiene l'inventario threat & Vulnerability Management del software attualmente installato nei dispositivi della rete, incluse le informazioni sulla fine `DeviceTvmSoftwareInventory` del supporto. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="bf379-110">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="bf379-111">Puoi, ad esempio, cercare eventi che coinvolgono dispositivi installati con una versione software attualmente vulnerabile.</span><span class="sxs-lookup"><span data-stu-id="bf379-111">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="bf379-112">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="bf379-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="bf379-113">Le `DeviceTvmSoftwareInventory` tabelle e hanno `DeviceTvmSoftwareVulnerabilities` sostituito la `DeviceTvmSoftwareInventoryVulnerabilities` tabella.</span><span class="sxs-lookup"><span data-stu-id="bf379-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="bf379-114">Insieme, le prime due tabelle includono più colonne che puoi usare per informare le attività di gestione della vulnerablità o cercare dispositivi vulnerabili.</span><span class="sxs-lookup"><span data-stu-id="bf379-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="bf379-115">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="bf379-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="bf379-116">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="bf379-116">Column name</span></span> | <span data-ttu-id="bf379-117">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="bf379-117">Data type</span></span> | <span data-ttu-id="bf379-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf379-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="bf379-119">stringa</span><span class="sxs-lookup"><span data-stu-id="bf379-119">string</span></span> | <span data-ttu-id="bf379-120">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="bf379-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="bf379-121">stringa</span><span class="sxs-lookup"><span data-stu-id="bf379-121">string</span></span> | <span data-ttu-id="bf379-122">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="bf379-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="bf379-123">stringa</span><span class="sxs-lookup"><span data-stu-id="bf379-123">string</span></span> | <span data-ttu-id="bf379-124">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="bf379-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="bf379-125">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="bf379-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="bf379-126">stringa</span><span class="sxs-lookup"><span data-stu-id="bf379-126">string</span></span> | <span data-ttu-id="bf379-127">Versione del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="bf379-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="bf379-128">stringa</span><span class="sxs-lookup"><span data-stu-id="bf379-128">string</span></span> | <span data-ttu-id="bf379-129">Architettura del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="bf379-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="bf379-130">stringa</span><span class="sxs-lookup"><span data-stu-id="bf379-130">string</span></span> | <span data-ttu-id="bf379-131">Nome del fornitore del software</span><span class="sxs-lookup"><span data-stu-id="bf379-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="bf379-132">stringa</span><span class="sxs-lookup"><span data-stu-id="bf379-132">string</span></span> | <span data-ttu-id="bf379-133">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="bf379-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="bf379-134">stringa</span><span class="sxs-lookup"><span data-stu-id="bf379-134">string</span></span> | <span data-ttu-id="bf379-135">Numero della versione del prodotto software</span><span class="sxs-lookup"><span data-stu-id="bf379-135">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="bf379-136">stringa</span><span class="sxs-lookup"><span data-stu-id="bf379-136">string</span></span> | <span data-ttu-id="bf379-137">Indica la fase del ciclo di vita del prodotto software rispetto alla data di fine del supporto (EOS) o di fine vita (EOL) specificata</span><span class="sxs-lookup"><span data-stu-id="bf379-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="bf379-138">stringa</span><span class="sxs-lookup"><span data-stu-id="bf379-138">string</span></span> | <span data-ttu-id="bf379-139">Data di fine del supporto (EOS) o fine vita (EOL) del prodotto software</span><span class="sxs-lookup"><span data-stu-id="bf379-139">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="bf379-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bf379-140">Related topics</span></span>

- [<span data-ttu-id="bf379-141">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="bf379-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bf379-142">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="bf379-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bf379-143">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="bf379-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="bf379-144">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="bf379-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bf379-145">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="bf379-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bf379-146">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="bf379-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="bf379-147">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="bf379-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)