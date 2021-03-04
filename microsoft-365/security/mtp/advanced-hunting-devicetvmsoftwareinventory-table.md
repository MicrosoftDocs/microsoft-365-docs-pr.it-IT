---
title: Tabella DeviceTvmSoftwareInventory nello schema di ricerca avanzata
description: Informazioni sull'inventario del software nei dispositivi nella tabella DeviceTvmSoftwareInventory dello schema di ricerca avanzata.
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, software, inventario, vulnerabilità, ID CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 445e6f767cc2269315a0b280df2f4deefa2faa08
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423976"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="dac26-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="dac26-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dac26-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="dac26-105">**Applies to:**</span></span>
- <span data-ttu-id="dac26-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dac26-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="dac26-107">Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato.</span><span class="sxs-lookup"><span data-stu-id="dac26-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dac26-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="dac26-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="dac26-109">La tabella nello schema di ricerca avanzata contiene l'inventario threat & Vulnerability Management del software attualmente installato nei dispositivi della rete, incluse le informazioni sulla `DeviceTvmSoftwareInventory` [fine](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) del supporto.</span><span class="sxs-lookup"><span data-stu-id="dac26-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="dac26-110">Ad esempio, puoi cercare eventi che coinvolgono dispositivi installati con una versione software attualmente vulnerabile.</span><span class="sxs-lookup"><span data-stu-id="dac26-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="dac26-111">Utilizzare questo riferimento per creare query che forniscano informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="dac26-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="dac26-112">La `DeviceTvmSoftwareInventory` tabella e le tabelle sono state `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` sostituite.</span><span class="sxs-lookup"><span data-stu-id="dac26-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="dac26-113">Insieme, le prime due tabelle includono più colonne che puoi usare per informare le attività di gestione della volgarità o cercare dispositivi vulnerabili.</span><span class="sxs-lookup"><span data-stu-id="dac26-113">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="dac26-114">Per informazioni sulle altre tabelle nello schema per Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="dac26-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="dac26-115">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="dac26-115">Column name</span></span> | <span data-ttu-id="dac26-116">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="dac26-116">Data type</span></span> | <span data-ttu-id="dac26-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dac26-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="dac26-118">stringa</span><span class="sxs-lookup"><span data-stu-id="dac26-118">string</span></span> | <span data-ttu-id="dac26-119">Identificatore univoco per il computer nel servizio</span><span class="sxs-lookup"><span data-stu-id="dac26-119">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="dac26-120">stringa</span><span class="sxs-lookup"><span data-stu-id="dac26-120">string</span></span> | <span data-ttu-id="dac26-121">Nome di dominio completo (FQDN) del computer</span><span class="sxs-lookup"><span data-stu-id="dac26-121">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="dac26-122">stringa</span><span class="sxs-lookup"><span data-stu-id="dac26-122">string</span></span> | <span data-ttu-id="dac26-123">Piattaforma del sistema operativo in esecuzione sul computer.</span><span class="sxs-lookup"><span data-stu-id="dac26-123">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="dac26-124">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="dac26-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="dac26-125">stringa</span><span class="sxs-lookup"><span data-stu-id="dac26-125">string</span></span> | <span data-ttu-id="dac26-126">Versione del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="dac26-126">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="dac26-127">stringa</span><span class="sxs-lookup"><span data-stu-id="dac26-127">string</span></span> | <span data-ttu-id="dac26-128">Architettura del sistema operativo in esecuzione sul computer</span><span class="sxs-lookup"><span data-stu-id="dac26-128">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="dac26-129">stringa</span><span class="sxs-lookup"><span data-stu-id="dac26-129">string</span></span> | <span data-ttu-id="dac26-130">Nome del fornitore del software</span><span class="sxs-lookup"><span data-stu-id="dac26-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="dac26-131">stringa</span><span class="sxs-lookup"><span data-stu-id="dac26-131">string</span></span> | <span data-ttu-id="dac26-132">Nome del prodotto software</span><span class="sxs-lookup"><span data-stu-id="dac26-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="dac26-133">stringa</span><span class="sxs-lookup"><span data-stu-id="dac26-133">string</span></span> | <span data-ttu-id="dac26-134">Numero della versione del prodotto software</span><span class="sxs-lookup"><span data-stu-id="dac26-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="dac26-135">stringa</span><span class="sxs-lookup"><span data-stu-id="dac26-135">string</span></span> | <span data-ttu-id="dac26-136">Indica la fase del ciclo di vita del prodotto software rispetto alla data di fine del supporto (EOS) o fine del ciclo di vita (EOL) specificata</span><span class="sxs-lookup"><span data-stu-id="dac26-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="dac26-137">stringa</span><span class="sxs-lookup"><span data-stu-id="dac26-137">string</span></span> | <span data-ttu-id="dac26-138">Data di fine del supporto (EOS) o fine del ciclo di vita (EOL) del prodotto software</span><span class="sxs-lookup"><span data-stu-id="dac26-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="dac26-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="dac26-139">Related topics</span></span>

- [<span data-ttu-id="dac26-140">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="dac26-140">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dac26-141">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="dac26-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dac26-142">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="dac26-142">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="dac26-143">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="dac26-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="dac26-144">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="dac26-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="dac26-145">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="dac26-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="dac26-146">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="dac26-146">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)