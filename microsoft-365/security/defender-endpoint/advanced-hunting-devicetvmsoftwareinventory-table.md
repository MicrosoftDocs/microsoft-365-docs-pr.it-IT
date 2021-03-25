---
title: Tabella DeviceTvmSoftwareInventory nello schema di ricerca avanzata
description: Informazioni sull'inventario del software nei dispositivi nella tabella DeviceTvmSoftwareInventory dello schema di ricerca avanzata.
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
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067506"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="bf58e-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="bf58e-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bf58e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="bf58e-105">**Applies to:**</span></span>
- [<span data-ttu-id="bf58e-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="bf58e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="bf58e-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="bf58e-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bf58e-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="bf58e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="bf58e-109">La tabella nello schema di ricerca avanzata contiene l'inventario threat & Vulnerability Management del software attualmente installato nei dispositivi della rete, incluse le informazioni sulla fine `DeviceTvmSoftwareInventory` del supporto. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="bf58e-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="bf58e-110">Puoi, ad esempio, cercare eventi che coinvolgono dispositivi installati con una versione software attualmente vulnerabile.</span><span class="sxs-lookup"><span data-stu-id="bf58e-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="bf58e-111">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="bf58e-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="bf58e-112">Le `DeviceTvmSoftwareInventory` tabelle e hanno `DeviceTvmSoftwareVulnerabilities` sostituito la `DeviceTvmSoftwareInventoryVulnerabilities` tabella.</span><span class="sxs-lookup"><span data-stu-id="bf58e-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="bf58e-113">Insieme, le prime due tabelle includono più colonne che è possibile utilizzare per informare le attività di gestione delle vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="bf58e-113">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="bf58e-114">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="bf58e-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="bf58e-115">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="bf58e-115">Column name</span></span> | <span data-ttu-id="bf58e-116">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="bf58e-116">Data type</span></span> | <span data-ttu-id="bf58e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf58e-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="bf58e-118">stringa</span><span class="sxs-lookup"><span data-stu-id="bf58e-118">string</span></span> | <span data-ttu-id="bf58e-119">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="bf58e-119">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="bf58e-120">stringa</span><span class="sxs-lookup"><span data-stu-id="bf58e-120">string</span></span> | <span data-ttu-id="bf58e-121">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="bf58e-121">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="bf58e-122">stringa</span><span class="sxs-lookup"><span data-stu-id="bf58e-122">string</span></span> | <span data-ttu-id="bf58e-123">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bf58e-123">Platform of the operating system running on the device.</span></span> <span data-ttu-id="bf58e-124">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="bf58e-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="bf58e-125">stringa</span><span class="sxs-lookup"><span data-stu-id="bf58e-125">string</span></span> | <span data-ttu-id="bf58e-126">Versione del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="bf58e-126">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="bf58e-127">stringa</span><span class="sxs-lookup"><span data-stu-id="bf58e-127">string</span></span> | <span data-ttu-id="bf58e-128">Architettura del sistema operativo in esecuzione nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="bf58e-128">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="bf58e-129">stringa</span><span class="sxs-lookup"><span data-stu-id="bf58e-129">string</span></span> | <span data-ttu-id="bf58e-130">Nome del fornitore del software</span><span class="sxs-lookup"><span data-stu-id="bf58e-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="bf58e-131">stringa</span><span class="sxs-lookup"><span data-stu-id="bf58e-131">string</span></span> | <span data-ttu-id="bf58e-132">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="bf58e-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="bf58e-133">stringa</span><span class="sxs-lookup"><span data-stu-id="bf58e-133">string</span></span> | <span data-ttu-id="bf58e-134">Numero della versione del prodotto software</span><span class="sxs-lookup"><span data-stu-id="bf58e-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="bf58e-135">stringa</span><span class="sxs-lookup"><span data-stu-id="bf58e-135">string</span></span> | <span data-ttu-id="bf58e-136">Indica la fase del ciclo di vita del prodotto software rispetto alla data di fine del supporto (EOS) o di fine vita (EOL) specificata</span><span class="sxs-lookup"><span data-stu-id="bf58e-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="bf58e-137">stringa</span><span class="sxs-lookup"><span data-stu-id="bf58e-137">string</span></span> | <span data-ttu-id="bf58e-138">Data di fine del supporto (EOS) o fine vita (EOL) del prodotto software</span><span class="sxs-lookup"><span data-stu-id="bf58e-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="bf58e-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bf58e-139">Related topics</span></span>

- [<span data-ttu-id="bf58e-140">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="bf58e-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bf58e-141">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="bf58e-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bf58e-142">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="bf58e-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="bf58e-143">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="bf58e-143">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

