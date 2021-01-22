---
title: Modifiche di denominazione nello schema di ricerca avanzata di Microsoft 365 Defender
description: Tenere traccia e rivedere le tabelle e le colonne delle modifiche di denominazione nello schema di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, dati, modifiche dei nomi, rinominare, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932203"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="7e1ce-104">Schema ricerca avanzata - Modifiche alla denominazione</span><span class="sxs-lookup"><span data-stu-id="7e1ce-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7e1ce-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7e1ce-105">**Applies to:**</span></span>
- <span data-ttu-id="7e1ce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e1ce-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="7e1ce-107">Lo [schema di ricerca](advanced-hunting-schema-tables.md) avanzata viene aggiornato regolarmente per aggiungere nuove tabelle e colonne.</span><span class="sxs-lookup"><span data-stu-id="7e1ce-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="7e1ce-108">In alcuni casi, i nomi delle colonne esistenti vengono rinominati o sostituiti per migliorare l'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="7e1ce-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="7e1ce-109">Fare riferimento a questo articolo per esaminare le modifiche di denominazione che potrebbero influire sulle query.</span><span class="sxs-lookup"><span data-stu-id="7e1ce-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="7e1ce-110">Le modifiche di denominazione vengono applicate automaticamente alle query salvate nel Centro sicurezza, incluse le query utilizzate dalle regole di rilevamento personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7e1ce-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="7e1ce-111">Non è necessario aggiornare manualmente queste query.</span><span class="sxs-lookup"><span data-stu-id="7e1ce-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="7e1ce-112">Sarà tuttavia necessario aggiornare le query seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e1ce-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="7e1ce-113">Query eseguite con l'API</span><span class="sxs-lookup"><span data-stu-id="7e1ce-113">Queries that are run using the API</span></span>
- <span data-ttu-id="7e1ce-114">Query salvate altrove all'esterno del Centro sicurezza</span><span class="sxs-lookup"><span data-stu-id="7e1ce-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="7e1ce-115">Dicembre 2020</span><span class="sxs-lookup"><span data-stu-id="7e1ce-115">December 2020</span></span>

| <span data-ttu-id="7e1ce-116">Nome della tabella</span><span class="sxs-lookup"><span data-stu-id="7e1ce-116">Table name</span></span> | <span data-ttu-id="7e1ce-117">Nome colonna originale</span><span class="sxs-lookup"><span data-stu-id="7e1ce-117">Original column name</span></span> | <span data-ttu-id="7e1ce-118">Nome nuova colonna</span><span class="sxs-lookup"><span data-stu-id="7e1ce-118">New column name</span></span> | <span data-ttu-id="7e1ce-119">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="7e1ce-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="7e1ce-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="7e1ce-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="7e1ce-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="7e1ce-121">FinalEmailAction</span></span> | <span data-ttu-id="7e1ce-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="7e1ce-122">EmailAction</span></span> | <span data-ttu-id="7e1ce-123">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="7e1ce-123">Customer feedback</span></span> |
| [<span data-ttu-id="7e1ce-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="7e1ce-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="7e1ce-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="7e1ce-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="7e1ce-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="7e1ce-126">EmailActionPolicy</span></span> | <span data-ttu-id="7e1ce-127">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="7e1ce-127">Customer feedback</span></span> |
| [<span data-ttu-id="7e1ce-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="7e1ce-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="7e1ce-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="7e1ce-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="7e1ce-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="7e1ce-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="7e1ce-131">Feedback dei clienti</span><span class="sxs-lookup"><span data-stu-id="7e1ce-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7e1ce-132">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7e1ce-132">Related topics</span></span>
- [<span data-ttu-id="7e1ce-133">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7e1ce-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7e1ce-134">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="7e1ce-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)