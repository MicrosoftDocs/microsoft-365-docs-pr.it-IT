---
title: Rilevamento di documenti simili
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
ms.openlocfilehash: e1a9ffe264925911f475732ffd98a43fa533e458
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071303"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="7b1f4-102">Rilevamento di documenti simili</span><span class="sxs-lookup"><span data-stu-id="7b1f4-102">Near duplicate detection</span></span>

<span data-ttu-id="7b1f4-103">Si consideri un insieme di documenti da rivedere in cui un sottoinsieme si basa sullo stesso modello e ha per lo più lo stesso linguaggio standard, con poche differenze qua e là.</span><span class="sxs-lookup"><span data-stu-id="7b1f4-103">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="7b1f4-104">Se un revisore è in grado di identificare questo sottoinsieme, esaminare uno di essi accuratamente ed esaminare le differenze per il resto, non avrebbero perso le informazioni univoche tenendo solo una frazione di tempo che li avrebbe necessari per leggere tutti i documenti da coprire.</span><span class="sxs-lookup"><span data-stu-id="7b1f4-104">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="7b1f4-105">Nei pressi dei gruppi di rilevamento duplicati, i documenti simili insieme consentono di rendere più efficiente il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="7b1f4-105">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="7b1f4-106">Come funziona</span><span class="sxs-lookup"><span data-stu-id="7b1f4-106">How does it work?</span></span>

<span data-ttu-id="7b1f4-107">Quando viene eseguito il rilevamento duplicato, il sistema analizza tutti i documenti con testo.</span><span class="sxs-lookup"><span data-stu-id="7b1f4-107">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="7b1f4-108">Viene quindi confrontato ogni documento uno rispetto all'altro per determinare se la loro somiglianza è maggiore rispetto alla soglia impostata.</span><span class="sxs-lookup"><span data-stu-id="7b1f4-108">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="7b1f4-109">In questo caso, i documenti vengono raggruppati.</span><span class="sxs-lookup"><span data-stu-id="7b1f4-109">If it is, the documents are grouped together.</span></span> <span data-ttu-id="7b1f4-110">Una volta che tutti i documenti sono stati confrontati e raggruppati, un documento di ogni gruppo viene contrassegnato come "pivot"; durante la revisione dei documenti, è possibile esaminare prima un pivot ed esaminare gli altri documenti nello stesso set di duplicati vicino, concentrandosi sulla differenza tra il pivot e il documento in esame.</span><span class="sxs-lookup"><span data-stu-id="7b1f4-110">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
