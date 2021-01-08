---
title: Denominazione delle modifiche apportate nello schema di ricerca avanzata di Microsoft 365 Defender
description: Monitorare e verificare le modifiche alle tabelle di denominazione e le colonne nello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, riferimento allo schema, kusto, Table, data, Naming changes, Rename, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780812"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="d41dc-104">Schema di caccia avanzato-modifiche dei nomi</span><span class="sxs-lookup"><span data-stu-id="d41dc-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d41dc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d41dc-105">**Applies to:**</span></span>
- <span data-ttu-id="d41dc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d41dc-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d41dc-107">Lo [schema di ricerca avanzata](advanced-hunting-schema-tables.md) viene aggiornato regolarmente per aggiungere nuove tabelle e colonne.</span><span class="sxs-lookup"><span data-stu-id="d41dc-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="d41dc-108">In alcuni casi, i nomi delle colonne esistenti vengono rinominati o sostituiti per migliorare l'esperienza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d41dc-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="d41dc-109">Fare riferimento a questo articolo per esaminare le modifiche di denominazione che potrebbero influire sulle query.</span><span class="sxs-lookup"><span data-stu-id="d41dc-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="d41dc-110">Le modifiche alla denominazione vengono applicate automaticamente alle query salvate nel centro sicurezza, incluse le query utilizzate dalle regole di rilevamento personalizzate.</span><span class="sxs-lookup"><span data-stu-id="d41dc-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="d41dc-111">Non è necessario aggiornare queste query manualmente.</span><span class="sxs-lookup"><span data-stu-id="d41dc-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="d41dc-112">Tuttavia, sarà necessario aggiornare le query seguenti:</span><span class="sxs-lookup"><span data-stu-id="d41dc-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="d41dc-113">Query eseguite utilizzando l'API</span><span class="sxs-lookup"><span data-stu-id="d41dc-113">Queries that are run using the API</span></span>
- <span data-ttu-id="d41dc-114">Query salvate altrove all'esterno del Centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="d41dc-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="d41dc-115">Dicembre 2020</span><span class="sxs-lookup"><span data-stu-id="d41dc-115">December 2020</span></span>

| <span data-ttu-id="d41dc-116">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="d41dc-116">Table name</span></span> | <span data-ttu-id="d41dc-117">Nome della colonna originale</span><span class="sxs-lookup"><span data-stu-id="d41dc-117">Original column name</span></span> | <span data-ttu-id="d41dc-118">Nuovo nome di colonna</span><span class="sxs-lookup"><span data-stu-id="d41dc-118">New column name</span></span> | <span data-ttu-id="d41dc-119">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="d41dc-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="d41dc-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="d41dc-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="d41dc-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="d41dc-121">FinalEmailAction</span></span> | <span data-ttu-id="d41dc-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="d41dc-122">EmailAction</span></span> | <span data-ttu-id="d41dc-123">Commenti e suggerimenti dei clienti</span><span class="sxs-lookup"><span data-stu-id="d41dc-123">Customer feedback</span></span> |
| [<span data-ttu-id="d41dc-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="d41dc-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="d41dc-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="d41dc-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="d41dc-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="d41dc-126">EmailActionPolicy</span></span> | <span data-ttu-id="d41dc-127">Commenti e suggerimenti dei clienti</span><span class="sxs-lookup"><span data-stu-id="d41dc-127">Customer feedback</span></span> |
| [<span data-ttu-id="d41dc-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="d41dc-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="d41dc-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="d41dc-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="d41dc-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="d41dc-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="d41dc-131">Commenti e suggerimenti dei clienti</span><span class="sxs-lookup"><span data-stu-id="d41dc-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d41dc-132">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d41dc-132">Related topics</span></span>
- [<span data-ttu-id="d41dc-133">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="d41dc-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d41dc-134">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="d41dc-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)