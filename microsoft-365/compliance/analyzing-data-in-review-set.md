---
title: Analizzare i dati in un set di revisione in Advanced eDiscovery
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
ms.openlocfilehash: b331bba76f45a11a4d1c8c0552b27759cf49608a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083347"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="6b7de-102">Analizzare i dati in un set di revisione in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6b7de-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="6b7de-103">Quando il numero di documenti raccolti è di grandi dimensioni, può essere molto difficile rivederli tutti.</span><span class="sxs-lookup"><span data-stu-id="6b7de-103">When the number of collected documents is large, it can be quite difficult to review them all.</span></span> <span data-ttu-id="6b7de-104">Advanced eDiscovery fornisce una serie di strumenti per analizzare i documenti in modo da ridurre il volume dei documenti da rivedere senza perdite di informazioni e per facilitare l'organizzazione dei documenti in maniera coerente.</span><span class="sxs-lookup"><span data-stu-id="6b7de-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="6b7de-105">Per ulteriori informazioni su queste funzionalità, vedere:</span><span class="sxs-lookup"><span data-stu-id="6b7de-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="6b7de-106">Rilevamento dei documenti simili</span><span class="sxs-lookup"><span data-stu-id="6b7de-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="6b7de-107">Threading posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6b7de-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="6b7de-108">Temi</span><span class="sxs-lookup"><span data-stu-id="6b7de-108">Themes</span></span>](themes.md)

<span data-ttu-id="6b7de-109">Per analizzare i dati in un set di Revisione:</span><span class="sxs-lookup"><span data-stu-id="6b7de-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="6b7de-110">Configurare le impostazioni di analisi per il caso.</span><span class="sxs-lookup"><span data-stu-id="6b7de-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="6b7de-111">Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analisi](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6b7de-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="6b7de-112">Aprire il set di revisione che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="6b7de-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="6b7de-113">Fare clic su **Gestisci Revisione set**.</span><span class="sxs-lookup"><span data-stu-id="6b7de-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="6b7de-114">Fare clic su **Esegui analisi per il set di revisione**.</span><span class="sxs-lookup"><span data-stu-id="6b7de-114">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="6b7de-115">È possibile controllare lo stato di avanzamento dell'analisi nella scheda **processi** del caso.</span><span class="sxs-lookup"><span data-stu-id="6b7de-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="6b7de-116">Dopo aver completato l'analisi, è possibile visualizzare il report di analisi, eseguire query all'interno del set di recensioni sugli output dell'analisi (vedere [query nel set di recensioni](review-set-search.md)) e vedere i documenti correlati di un documento specifico (vedere [revisione dei dati nel set](reviewing-data-in-review-set.md)di analisi).</span><span class="sxs-lookup"><span data-stu-id="6b7de-116">After analysis is completed, you can view analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="6b7de-117">Report di analisi</span><span class="sxs-lookup"><span data-stu-id="6b7de-117">Analytics report</span></span>

<span data-ttu-id="6b7de-118">Per visualizzare un report di analisi per un set di Revisione:</span><span class="sxs-lookup"><span data-stu-id="6b7de-118">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="6b7de-119">Aprire il set di revisione.</span><span class="sxs-lookup"><span data-stu-id="6b7de-119">Open the review set.</span></span>

2. <span data-ttu-id="6b7de-120">Fare clic su **Gestisci Revisione set**.</span><span class="sxs-lookup"><span data-stu-id="6b7de-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="6b7de-121">Fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="6b7de-121">Click **View report**.</span></span>

<span data-ttu-id="6b7de-122">Il report ha quattro componenti dall'analisi:</span><span class="sxs-lookup"><span data-stu-id="6b7de-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="6b7de-123">**Breakdown** : il numero di messaggi di posta elettronica, allegati e documenti sciolti è stato trovato nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="6b7de-123">**Breakdown** - How many email messages, attachments, and loose documents were found in the review set.</span></span>

- <span data-ttu-id="6b7de-124">**Documenti (esclusi gli allegati)** -quanti documenti sfusi sono stati pivot, unici in prossimità di duplicati di un pivot o duplicati esatti di un altro documento.</span><span class="sxs-lookup"><span data-stu-id="6b7de-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="6b7de-125">**Messaggi di posta elettronica-il** numero di email sono stati inclusivi, copie inclusive, svantaggi inclusi o nessuno di questi.</span><span class="sxs-lookup"><span data-stu-id="6b7de-125">**Emails** - How many email messages were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="6b7de-126">**Allegati** -quanti allegati di posta elettronica sono stati univoci o duplicati di un altro allegato di posta elettronica nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="6b7de-126">**Attachments** - How many email attachments were unique or duplicates of a another email attachment in the review set.</span></span>