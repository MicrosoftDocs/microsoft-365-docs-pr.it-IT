---
title: Tabella DeviceTvmSecureConfigurationAssessment nello schema di Ricerca avanzata
description: Informazioni sugli eventi di & di valutazione della sicurezza di Gestione delle vulnerabilità nella tabella DeviceTvmSecureConfigurationAssessment dello schema di ricerca avanzata. Questi eventi forniscono informazioni sul dispositivo, nonché dettagli sulla configurazione della sicurezza, informazioni sull'impatto e sulla conformità.
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, gestione delle vulnerabilità del & delle minacce, TVM, gestione dei dispositivi, configurazione della sicurezza, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067010"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="dad58-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="dad58-105">DeviceTvmSecureConfigurationAssessment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dad58-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="dad58-106">**Applies to:**</span></span>
- [<span data-ttu-id="dad58-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="dad58-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="dad58-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="dad58-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dad58-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="dad58-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="dad58-110">Ogni riga della tabella `DeviceTvmSecureConfigurationAssessment` contiene un evento di valutazione per una specifica configurazione di sicurezza della [Gestione delle minacce e della vulnerabilità](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="dad58-110">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="dad58-111">Usare questo riferimento per controllare i risultati più recenti della valutazione e determinare se i dispositivi sono conformi.</span><span class="sxs-lookup"><span data-stu-id="dad58-111">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="dad58-112">Per informazioni su altre tabelle nello schema di Ricerca avanzata vedere [le informazioni di riferimento sulla Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="dad58-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="dad58-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="dad58-113">Column name</span></span> | <span data-ttu-id="dad58-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="dad58-114">Data type</span></span> | <span data-ttu-id="dad58-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dad58-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="dad58-116">stringa</span><span class="sxs-lookup"><span data-stu-id="dad58-116">string</span></span> | <span data-ttu-id="dad58-117">Identificatore univoco del dispositivo nel servizio</span><span class="sxs-lookup"><span data-stu-id="dad58-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="dad58-118">stringa</span><span class="sxs-lookup"><span data-stu-id="dad58-118">string</span></span> | <span data-ttu-id="dad58-119">Nome di dominio completo (FQDN) del dispositivo</span><span class="sxs-lookup"><span data-stu-id="dad58-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="dad58-120">stringa</span><span class="sxs-lookup"><span data-stu-id="dad58-120">string</span></span> | <span data-ttu-id="dad58-121">Piattaforma del sistema operativo in esecuzione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dad58-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="dad58-122">Ciò indica specifici sistemi operativi, incluse variazioni all'interno della stessa famiglia di prodotti, come Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="dad58-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="dad58-123">datetime</span><span class="sxs-lookup"><span data-stu-id="dad58-123">datetime</span></span> |<span data-ttu-id="dad58-124">Data e ora in cui è stato generato il record</span><span class="sxs-lookup"><span data-stu-id="dad58-124">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="dad58-125">stringa</span><span class="sxs-lookup"><span data-stu-id="dad58-125">string</span></span> | <span data-ttu-id="dad58-126">Identificatore univoco di una configurazione specifica</span><span class="sxs-lookup"><span data-stu-id="dad58-126">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="dad58-127">stringa</span><span class="sxs-lookup"><span data-stu-id="dad58-127">string</span></span> | <span data-ttu-id="dad58-128">Categoria o raggruppamento a cui appartiene la configurazione: Applicazione, Sistema operativo, Rete, Account, Controlli di sicurezza</span><span class="sxs-lookup"><span data-stu-id="dad58-128">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="dad58-129">stringa</span><span class="sxs-lookup"><span data-stu-id="dad58-129">string</span></span> |<span data-ttu-id="dad58-130">Sottocategoria o sottoraggruppamento a cui appartiene la configurazione.</span><span class="sxs-lookup"><span data-stu-id="dad58-130">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="dad58-131">In molti casi qui vengono descritte capacità o funzionalità specifiche.</span><span class="sxs-lookup"><span data-stu-id="dad58-131">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="dad58-132">stringa</span><span class="sxs-lookup"><span data-stu-id="dad58-132">string</span></span> | <span data-ttu-id="dad58-133">Impatto nominale della configurazione sul punteggio di configurazione complessivo (1-10)</span><span class="sxs-lookup"><span data-stu-id="dad58-133">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="dad58-134">booleano</span><span class="sxs-lookup"><span data-stu-id="dad58-134">boolean</span></span> | <span data-ttu-id="dad58-135">Indica se la configurazione o i criteri sono configurati correttamente</span><span class="sxs-lookup"><span data-stu-id="dad58-135">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="dad58-136">boolean</span><span class="sxs-lookup"><span data-stu-id="dad58-136">boolean</span></span> | <span data-ttu-id="dad58-137">Indica se la configurazione o il criterio si applica al dispositivo</span><span class="sxs-lookup"><span data-stu-id="dad58-137">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="dad58-138">stringa</span><span class="sxs-lookup"><span data-stu-id="dad58-138">string</span></span> | <span data-ttu-id="dad58-139">Informazioni contestuali aggiuntive sulla configurazione o sui criteri</span><span class="sxs-lookup"><span data-stu-id="dad58-139">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="dad58-140">boolean</span><span class="sxs-lookup"><span data-stu-id="dad58-140">boolean</span></span> | <span data-ttu-id="dad58-141">Indica se l'impatto dell'utente sarà negativo se viene applicata la configurazione o il criterio</span><span class="sxs-lookup"><span data-stu-id="dad58-141">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="dad58-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="dad58-142">Related topics</span></span>

- [<span data-ttu-id="dad58-143">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="dad58-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dad58-144">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="dad58-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dad58-145">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="dad58-145">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="dad58-146">Panoramica della Gestione della vulnerabilità e delle minacce</span><span class="sxs-lookup"><span data-stu-id="dad58-146">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)