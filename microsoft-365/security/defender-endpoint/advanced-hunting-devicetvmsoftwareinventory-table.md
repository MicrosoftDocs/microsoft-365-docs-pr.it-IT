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
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408624"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="25b83-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="25b83-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="25b83-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="25b83-105">**Applies to:**</span></span>
- [<span data-ttu-id="25b83-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="25b83-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="25b83-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="25b83-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="25b83-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="25b83-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="25b83-109">La tabella nello schema di ricerca avanzata contiene l'inventario di gestione delle minacce e delle vulnerabilità del software attualmente installato nei dispositivi della rete, incluse le informazioni sulla fine `DeviceTvmSoftwareInventory` del supporto. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="25b83-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="25b83-110">Puoi, ad esempio, cercare eventi che coinvolgono dispositivi installati con una versione software attualmente vulnerabile.</span><span class="sxs-lookup"><span data-stu-id="25b83-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="25b83-111">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="25b83-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="25b83-112">DeviceTVMSoftwareInventory contiene tutto il software che la gestione delle minacce e delle vulnerabilità è stata in grado di associare a un cpe (Common Platform Enumeration), sia esso vulnerabile o meno.</span><span class="sxs-lookup"><span data-stu-id="25b83-112">DeviceTVMSoftwareInventory contains all the software which threat and vulnerability management was able to match to a Common Platform Enumeration (CPE) – whether it is vulnerable or not.</span></span>

>[!NOTE]
><span data-ttu-id="25b83-113">Le `DeviceTvmSoftwareInventory` tabelle e hanno `DeviceTvmSoftwareVulnerabilities` sostituito la `DeviceTvmSoftwareInventoryVulnerabilities` tabella.</span><span class="sxs-lookup"><span data-stu-id="25b83-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="25b83-114">Insieme, le prime due tabelle includono più colonne che è possibile utilizzare per informare le attività di gestione delle vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="25b83-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="25b83-115">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="25b83-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="25b83-116">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="25b83-116">Column name</span></span> | <span data-ttu-id="25b83-117">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="25b83-117">Data type</span></span> | <span data-ttu-id="25b83-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25b83-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="25b83-119">stringa</span><span class="sxs-lookup"><span data-stu-id="25b83-119">string</span></span> | <span data-ttu-id="25b83-120">Identificatore univoco del dispositivo nel servizio.</span><span class="sxs-lookup"><span data-stu-id="25b83-120">Unique identifier for the device in the service.</span></span> |
| `DeviceName` | <span data-ttu-id="25b83-121">stringa</span><span class="sxs-lookup"><span data-stu-id="25b83-121">string</span></span> | <span data-ttu-id="25b83-122">Nome di dominio completo (FQDN) del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25b83-122">Fully qualified domain name (FQDN) of the device.</span></span> |
| `OSPlatform` | <span data-ttu-id="25b83-123">stringa</span><span class="sxs-lookup"><span data-stu-id="25b83-123">string</span></span> | <span data-ttu-id="25b83-124">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25b83-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="25b83-125">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="25b83-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="25b83-126">stringa</span><span class="sxs-lookup"><span data-stu-id="25b83-126">string</span></span> | <span data-ttu-id="25b83-127">Versione del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25b83-127">Version of the operating system running on the device.</span></span> |
| `OSArchitecture` | <span data-ttu-id="25b83-128">stringa</span><span class="sxs-lookup"><span data-stu-id="25b83-128">string</span></span> | <span data-ttu-id="25b83-129">Architettura del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25b83-129">Architecture of the operating system running on the device.</span></span> |
| `SoftwareVendor` | <span data-ttu-id="25b83-130">stringa</span><span class="sxs-lookup"><span data-stu-id="25b83-130">string</span></span> | <span data-ttu-id="25b83-131">Nome del fornitore del software.</span><span class="sxs-lookup"><span data-stu-id="25b83-131">Name of the software vendor.</span></span> |
| `SoftwareName` | <span data-ttu-id="25b83-132">stringa</span><span class="sxs-lookup"><span data-stu-id="25b83-132">string</span></span> | <span data-ttu-id="25b83-133">Nome del prodotto software.</span><span class="sxs-lookup"><span data-stu-id="25b83-133">Name of the software product.</span></span> |
| `SoftwareVersion` | <span data-ttu-id="25b83-134">stringa</span><span class="sxs-lookup"><span data-stu-id="25b83-134">string</span></span> | <span data-ttu-id="25b83-135">Numero di versione del prodotto software.</span><span class="sxs-lookup"><span data-stu-id="25b83-135">Version number of the software product.</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="25b83-136">stringa</span><span class="sxs-lookup"><span data-stu-id="25b83-136">string</span></span> | <span data-ttu-id="25b83-137">Indica la fase del ciclo di vita del prodotto software rispetto alla data di fine del supporto (EOS) o di fine vita (EOL) specificata.</span><span class="sxs-lookup"><span data-stu-id="25b83-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date.</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="25b83-138">stringa</span><span class="sxs-lookup"><span data-stu-id="25b83-138">string</span></span> | <span data-ttu-id="25b83-139">Data di fine del supporto (EOS) o di fine vita (EOL) del prodotto software.</span><span class="sxs-lookup"><span data-stu-id="25b83-139">End-of-support (EOS) or end-of-life (EOL) date of the software product.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="25b83-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="25b83-140">Related topics</span></span>

- [<span data-ttu-id="25b83-141">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="25b83-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="25b83-142">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="25b83-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="25b83-143">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="25b83-143">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="25b83-144">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="25b83-144">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
