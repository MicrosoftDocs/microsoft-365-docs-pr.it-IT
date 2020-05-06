---
title: Eseguire analisi per velocizzare le indagini
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
description: Informazioni su come utilizzare gli strumenti analitici, come il rilevamento duplicato, il threading di posta elettronica e i temi per velocizzare le indagini.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e7c5103adabadf88028351f0314bcdfaa2cd4d0f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035848"
---
# <a name="run-analytics-to-investigate-faster"></a><span data-ttu-id="7b2e1-103">Eseguire analisi per velocizzare le indagini</span><span class="sxs-lookup"><span data-stu-id="7b2e1-103">Run analytics to investigate faster</span></span>

<span data-ttu-id="7b2e1-104">Quando un insieme Evidence è di grandi dimensioni, può essere difficile rivederle tutte.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-104">When an evidence collection is large, it can be difficult to review them all.</span></span> <span data-ttu-id="7b2e1-105">Un insieme di evidenze spesso include più copie dello stesso tipo o di messaggi di posta elettronica o documenti simili.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-105">A set of evidence often includes multiple copies of the same or similar email messages or documents.</span></span> <span data-ttu-id="7b2e1-106">Indagini sui dati (Preview) fornisce una serie di strumenti di analisi che consentono di ridurre il volume dei documenti che devono essere esaminati senza perdita di informazioni.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-106">Data Investigations (Preview) provides a number of analytics tools that can help you reduce the volume of documents that need to be reviewed without any loss in information.</span></span> <span data-ttu-id="7b2e1-107">Per ulteriori informazioni su queste funzionalità, vedere:</span><span class="sxs-lookup"><span data-stu-id="7b2e1-107">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="7b2e1-108">Rilevamento dei documenti simili</span><span class="sxs-lookup"><span data-stu-id="7b2e1-108">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="7b2e1-109">Threading posta elettronica</span><span class="sxs-lookup"><span data-stu-id="7b2e1-109">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="7b2e1-110">Temi</span><span class="sxs-lookup"><span data-stu-id="7b2e1-110">Themes</span></span>](themes.md)

<span data-ttu-id="7b2e1-111">Per analizzare i dati in un set di evidenze:</span><span class="sxs-lookup"><span data-stu-id="7b2e1-111">To analyze data in an evidence set:</span></span>

1. <span data-ttu-id="7b2e1-112">Configurare le impostazioni di analisi per l'indagine.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-112">Configure the analytics settings for your investigation.</span></span> <span data-ttu-id="7b2e1-113">Per ulteriori informazioni, vedere [configurare le impostazioni di ricerca e analisi](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7b2e1-113">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="7b2e1-114">Aprire il set di prove.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-114">Open the evidence set.</span></span>

3. <span data-ttu-id="7b2e1-115">Fare clic su **Gestisci evidenza**.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-115">Click **Manage evidence**.</span></span>

4. <span data-ttu-id="7b2e1-116">In **analisi**fare clic su **analizza**.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-116">Under **Analytics**, click **Analyze**.</span></span>

<span data-ttu-id="7b2e1-117">È possibile controllare lo stato di avanzamento dell'analisi nella scheda **processi** dell'indagine.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-117">You can check the progress of analysis on the **Jobs** tab in your investigation.</span></span> <span data-ttu-id="7b2e1-118">Il tipo di processo attivato è denominato **Running Analytics**.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-118">The job type that's triggered is named **Running analytics**.</span></span>

 <span data-ttu-id="7b2e1-119">Al termine dell'analisi, è possibile visualizzare un elenco di duplicati esatti o quasi duplicati del documento che si sta esaminando nel riquadro a destra.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-119">After analysis is completed, you can see a list of exact duplicates or near-duplicates of the document that you're reviewing located in the panel on the right.</span></span> <span data-ttu-id="7b2e1-120">Per selezionare tutti i duplicati del documento che si sta visualizzando, è possibile farlo facilmente usando questo pannello.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-120">To select all duplicates of the document you're viewing, you can easily do so using this panel.</span></span> <span data-ttu-id="7b2e1-121">Per ulteriori informazioni su altre caratteristiche di questo pannello, vedere [Review data in evidence](review-data-in-evidence.md).</span><span class="sxs-lookup"><span data-stu-id="7b2e1-121">To learn more about other features on this panel, see [Review data in evidence](review-data-in-evidence.md).</span></span> 

<span data-ttu-id="7b2e1-122">È inoltre possibile eseguire query aggiuntive all'interno dell'evidenza utilizzando gli output dell'analisi, ad esempio i temi.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-122">You can also run additional queries within your evidence using the outputs of the analysis such as themes.</span></span> <span data-ttu-id="7b2e1-123">Per ulteriori informazioni, vedere [query the data in evidence](evidence-query.md).</span><span class="sxs-lookup"><span data-stu-id="7b2e1-123">For more information, see [Query the data in evidence](evidence-query.md).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="7b2e1-124">Report di analisi</span><span class="sxs-lookup"><span data-stu-id="7b2e1-124">Analytics report</span></span>

<span data-ttu-id="7b2e1-125">Per visualizzare un report di analisi per l'evidenza:</span><span class="sxs-lookup"><span data-stu-id="7b2e1-125">To view an analytics report for your evidence:</span></span>

1. <span data-ttu-id="7b2e1-126">Aprire il set di prove.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-126">Open the evidence set.</span></span>

2. <span data-ttu-id="7b2e1-127">Fare clic su **Gestisci evidenza**.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-127">Click **Manage evidence**.</span></span>

3. <span data-ttu-id="7b2e1-128">In **analisi**fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-128">Under **Analytics**, click **View report**.</span></span>

<span data-ttu-id="7b2e1-129">Il report ha quattro componenti dall'analisi:</span><span class="sxs-lookup"><span data-stu-id="7b2e1-129">The report has four components from analysis:</span></span>

- <span data-ttu-id="7b2e1-130">**Breakdown** : il numero di messaggi di posta elettronica, allegati e documenti RAW trovati nel set di evidenze.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-130">**Breakdown** - The number of raw emails, attachments, and documents found in the evidence set.</span></span>

- <span data-ttu-id="7b2e1-131">**Email** : il numero di messaggi di eamil che sono inclusivi, meno inclusi, copie inclusive o nessuno dei precedenti.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-131">**Emails** - The number of eamil messages that are inclusives, inclusive minuses, inclusive copies, or none of the above.</span></span>
   - <span data-ttu-id="7b2e1-132">Inclusive: l'ultimo messaggio nel thread di posta elettronica che contiene tutta la cronologia precedente e richiede la revisione.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-132">Inclusives: The last message in the email thread that contains all previous history and requires review.</span></span>
   - <span data-ttu-id="7b2e1-133">Svantaggi inclusi: il messaggio nel thread che contiene uno o più allegati diversi che richiedono la revisione.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-133">Inclusive minuses: The message in the thread that contains one or more different attachments that requires review.</span></span>
   - <span data-ttu-id="7b2e1-134">Copie Inclusive: il messaggio che rappresenta una copia di un altro messaggio con meno inclusivo o inclusivo (oggetto e corpo).</span><span class="sxs-lookup"><span data-stu-id="7b2e1-134">Inclusive copies: The message that is a copy of another inclusive or inclusive minus message (subject and body).</span></span>

- <span data-ttu-id="7b2e1-135">**Allegati** : il numero di allegati di posta elettronica che sono univoci o duplicati di un allegato di posta elettronica diverso all'interno dello stesso elemento di prova stesso.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-135">**Attachments** - The number of email attachments that are unique or duplicates of a different email attachment within the same evidence same.</span></span>

- <span data-ttu-id="7b2e1-136">**Documenti (esclusi gli allegati di posta elettronica)** -numero di documenti univoci che richiedono la revisione, ad esempio il documento più rappresentativo del set quasi duplicato o un duplicato esatto di un altro documento.</span><span class="sxs-lookup"><span data-stu-id="7b2e1-136">**Documents (excluding email attachments)** - The number of unique documents that require review, for example, the most representative document of the near-duplicate set or an exact duplicate of another document).</span></span>
