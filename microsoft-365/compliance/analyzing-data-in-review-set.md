---
title: Analizzare i dati in un set di revisione in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 0f9cb386ce57d6581ade5caa05e029511100d9b3
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42556784"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="0c4df-102">Analizzare i dati in un set di revisione in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0c4df-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="0c4df-103">Quando il numero di documenti raccolti è di grandi dimensioni, può essere difficile rivederli tutti.</span><span class="sxs-lookup"><span data-stu-id="0c4df-103">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="0c4df-104">Advanced eDiscovery fornisce una serie di strumenti per analizzare i documenti in modo da ridurre il volume dei documenti da rivedere senza perdite di informazioni e per facilitare l'organizzazione dei documenti in maniera coerente.</span><span class="sxs-lookup"><span data-stu-id="0c4df-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="0c4df-105">Per ulteriori informazioni su queste funzionalità, vedere:</span><span class="sxs-lookup"><span data-stu-id="0c4df-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="0c4df-106">Rilevamento dei documenti simili</span><span class="sxs-lookup"><span data-stu-id="0c4df-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="0c4df-107">Threading posta elettronica</span><span class="sxs-lookup"><span data-stu-id="0c4df-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="0c4df-108">Temi</span><span class="sxs-lookup"><span data-stu-id="0c4df-108">Themes</span></span>](themes.md)

<span data-ttu-id="0c4df-109">Per analizzare i dati in un set di Revisione:</span><span class="sxs-lookup"><span data-stu-id="0c4df-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="0c4df-110">Configurare le impostazioni di analisi per il caso.</span><span class="sxs-lookup"><span data-stu-id="0c4df-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="0c4df-111">Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analisi](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0c4df-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="0c4df-112">Aprire il set di revisione che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="0c4df-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="0c4df-113">Fare clic su **Gestisci Revisione set**.</span><span class="sxs-lookup"><span data-stu-id="0c4df-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="0c4df-114">Fare clic su **Esegui analisi per il set di revisione**.</span><span class="sxs-lookup"><span data-stu-id="0c4df-114">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="0c4df-115">È possibile controllare lo stato di avanzamento dell'analisi nella scheda **processi** del caso.</span><span class="sxs-lookup"><span data-stu-id="0c4df-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="0c4df-116">Dopo aver completato l'analisi, è possibile visualizzare il rapporto analitico, eseguire query all'interno del set di recensioni sugli output dell'analisi (vedere [query nel set di recensioni](review-set-search.md)) e vedere i documenti correlati di un documento specifico (vedere [reviewing data in Review set](reviewing-data-in-review-set.md)).</span><span class="sxs-lookup"><span data-stu-id="0c4df-116">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="0c4df-117">Report di analisi</span><span class="sxs-lookup"><span data-stu-id="0c4df-117">Analytics report</span></span>

<span data-ttu-id="0c4df-118">Per visualizzare un report di analisi per un set di Revisione:</span><span class="sxs-lookup"><span data-stu-id="0c4df-118">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="0c4df-119">Aprire il set di revisione.</span><span class="sxs-lookup"><span data-stu-id="0c4df-119">Open the review set.</span></span>

2. <span data-ttu-id="0c4df-120">Fare clic su **Gestisci Revisione set**.</span><span class="sxs-lookup"><span data-stu-id="0c4df-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="0c4df-121">Fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="0c4df-121">Click **View report**.</span></span>

<span data-ttu-id="0c4df-122">Il report contiene sette componenti dall'analisi:</span><span class="sxs-lookup"><span data-stu-id="0c4df-122">The report has seven components from analysis:</span></span>

- <span data-ttu-id="0c4df-123">**Popolazione target:** Il numero di messaggi di posta elettronica, allegati e documenti sciolti trovati nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="0c4df-123">**Target population:** The number of email messages, attachments, and loose documents found in the review set.</span></span>

- <span data-ttu-id="0c4df-124">**Documenti (esclusi gli allegati):** Il numero di documenti sciolti che sono pivot, unici in prossimità di duplicati di un pivot o un duplicato esatto di un altro documento.</span><span class="sxs-lookup"><span data-stu-id="0c4df-124">**Documents (excluding attachments):** The number of loose documents that are pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="0c4df-125">**Messaggi di posta elettronica:** Il numero di messaggi di posta elettronica inclusi, copie inclusive, svantaggi inclusi o nessuno di questi.</span><span class="sxs-lookup"><span data-stu-id="0c4df-125">**Emails:** The number of email messages that are inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="0c4df-126">**Allegati:** Il numero di allegati di posta elettronica che sono univoci o duplicati di un altro allegato di posta elettronica nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="0c4df-126">**Attachments:** The number of email attachments that are unique or duplicates of another email attachment in the review set.</span></span>

- <span data-ttu-id="0c4df-127">**Numero di file per tipo:** Il numero di file identificati dall'estensione di file.</span><span class="sxs-lookup"><span data-stu-id="0c4df-127">**Number of files by type:** The number of files, identified by file extension.</span></span>

- <span data-ttu-id="0c4df-128">**Documenti in base all'origine:** Riepilogo del contenuto in base all'origine dati originale.</span><span class="sxs-lookup"><span data-stu-id="0c4df-128">**Documents by source:** A summary of content by its original data source.</span></span>

- <span data-ttu-id="0c4df-129">**Documenti aggregati in base al processo:** Riepilogo del contenuto dei processi dei set di revisione.</span><span class="sxs-lookup"><span data-stu-id="0c4df-129">**Documents aggregated by process:** A summary of content by review set processes.</span></span> 
