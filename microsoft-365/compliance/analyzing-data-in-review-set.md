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
description: Informazioni sugli strumenti disponibili per organizzare i set di documenti durante l'analisi di un caso di eDiscovery avanzato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 87788e444a5ef671586567510448dab8b9deddcd
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033820"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="167eb-103">Analizzare i dati in un set di revisione in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="167eb-103">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="167eb-104">Quando il numero di documenti raccolti è di grandi dimensioni, può essere difficile rivederli tutti.</span><span class="sxs-lookup"><span data-stu-id="167eb-104">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="167eb-105">Advanced eDiscovery fornisce una serie di strumenti per analizzare i documenti in modo da ridurre il volume dei documenti da rivedere senza perdite di informazioni e per facilitare l'organizzazione dei documenti in maniera coerente.</span><span class="sxs-lookup"><span data-stu-id="167eb-105">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="167eb-106">Per ulteriori informazioni su queste funzionalità, vedere:</span><span class="sxs-lookup"><span data-stu-id="167eb-106">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="167eb-107">Rilevamento dei documenti simili</span><span class="sxs-lookup"><span data-stu-id="167eb-107">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="167eb-108">Threading posta elettronica</span><span class="sxs-lookup"><span data-stu-id="167eb-108">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="167eb-109">Temi</span><span class="sxs-lookup"><span data-stu-id="167eb-109">Themes</span></span>](themes.md)

<span data-ttu-id="167eb-110">Per analizzare i dati in un set di Revisione:</span><span class="sxs-lookup"><span data-stu-id="167eb-110">To analyze data in a review set:</span></span>

1. <span data-ttu-id="167eb-111">Configurare le impostazioni di analisi per il caso.</span><span class="sxs-lookup"><span data-stu-id="167eb-111">Configure analytics settings for your case.</span></span> <span data-ttu-id="167eb-112">Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analisi](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="167eb-112">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="167eb-113">Aprire il set di revisione che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="167eb-113">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="167eb-114">Fare clic su **Gestisci Revisione set**.</span><span class="sxs-lookup"><span data-stu-id="167eb-114">Click **Manage review set**.</span></span>

4. <span data-ttu-id="167eb-115">Fare clic su **Esegui analisi per il set di revisione**.</span><span class="sxs-lookup"><span data-stu-id="167eb-115">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="167eb-116">È possibile controllare lo stato di avanzamento dell'analisi nella scheda **processi** del caso.</span><span class="sxs-lookup"><span data-stu-id="167eb-116">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="167eb-117">Dopo aver completato l'analisi, è possibile visualizzare il rapporto analitico, eseguire query all'interno del set di recensioni sugli output dell'analisi (vedere [query nel set di recensioni](review-set-search.md)) e vedere i documenti correlati di un documento specifico (vedere [reviewing data in Review set](reviewing-data-in-review-set.md)).</span><span class="sxs-lookup"><span data-stu-id="167eb-117">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="167eb-118">Report di analisi</span><span class="sxs-lookup"><span data-stu-id="167eb-118">Analytics report</span></span>

<span data-ttu-id="167eb-119">Per visualizzare un report di analisi per un set di Revisione:</span><span class="sxs-lookup"><span data-stu-id="167eb-119">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="167eb-120">Aprire il set di revisione.</span><span class="sxs-lookup"><span data-stu-id="167eb-120">Open the review set.</span></span>

2. <span data-ttu-id="167eb-121">Fare clic su **Gestisci Revisione set**.</span><span class="sxs-lookup"><span data-stu-id="167eb-121">Click **Manage review set**.</span></span>

3. <span data-ttu-id="167eb-122">Fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="167eb-122">Click **View report**.</span></span>

<span data-ttu-id="167eb-123">Il report contiene sette componenti dall'analisi:</span><span class="sxs-lookup"><span data-stu-id="167eb-123">The report has seven components from analysis:</span></span>

- <span data-ttu-id="167eb-124">**Popolazione target:** Il numero di messaggi di posta elettronica, allegati e documenti sciolti trovati nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="167eb-124">**Target population:** The number of email messages, attachments, and loose documents found in the review set.</span></span>

- <span data-ttu-id="167eb-125">**Documenti (esclusi gli allegati):** Il numero di documenti sciolti che sono pivot, unici in prossimità di duplicati di un pivot o un duplicato esatto di un altro documento.</span><span class="sxs-lookup"><span data-stu-id="167eb-125">**Documents (excluding attachments):** The number of loose documents that are pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="167eb-126">**Messaggi di posta elettronica:** Il numero di messaggi di posta elettronica inclusi, copie inclusive, svantaggi inclusi o nessuno di questi.</span><span class="sxs-lookup"><span data-stu-id="167eb-126">**Emails:** The number of email messages that are inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="167eb-127">**Allegati:** Il numero di allegati di posta elettronica che sono univoci o duplicati di un altro allegato di posta elettronica nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="167eb-127">**Attachments:** The number of email attachments that are unique or duplicates of another email attachment in the review set.</span></span>

- <span data-ttu-id="167eb-128">**Numero di file per tipo:** Il numero di file identificati dall'estensione di file.</span><span class="sxs-lookup"><span data-stu-id="167eb-128">**Number of files by type:** The number of files, identified by file extension.</span></span>

- <span data-ttu-id="167eb-129">**Documenti in base all'origine:** Riepilogo del contenuto in base all'origine dati originale.</span><span class="sxs-lookup"><span data-stu-id="167eb-129">**Documents by source:** A summary of content by its original data source.</span></span>

- <span data-ttu-id="167eb-130">**Documenti aggregati in base al processo:** Riepilogo del contenuto dei processi dei set di revisione.</span><span class="sxs-lookup"><span data-stu-id="167eb-130">**Documents aggregated by process:** A summary of content by review set processes.</span></span> 
