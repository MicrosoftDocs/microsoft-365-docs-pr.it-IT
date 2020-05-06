---
title: Near duplicate detection-indagini sui dati
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
description: Quando si gestiscono indagini sui dati, è possibile utilizzare il rilevamento quasi duplicati per raggruppare documenti simili in formato testuale durante l'analisi dei dati del caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa451051c008f7a1614661d3bd66129cac6bb4ad
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036431"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="5f9e8-103">Rilevamento di documenti simili</span><span class="sxs-lookup"><span data-stu-id="5f9e8-103">Near duplicate detection</span></span>

<span data-ttu-id="5f9e8-104">Si consideri un insieme di documenti da rivedere in cui un sottoinsieme si basa sullo stesso modello e ha per lo più lo stesso linguaggio standard, con poche differenze qua e là.</span><span class="sxs-lookup"><span data-stu-id="5f9e8-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="5f9e8-105">Se un revisore è in grado di identificare questo sottoinsieme, esaminare uno di essi accuratamente ed esaminare le differenze per il resto, non avrebbero perso le informazioni univoche tenendo solo una frazione di tempo che li avrebbe necessari per leggere tutti i documenti da coprire.</span><span class="sxs-lookup"><span data-stu-id="5f9e8-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="5f9e8-106">Nei pressi dei gruppi di rilevamento duplicati, i documenti simili insieme consentono di rendere più efficiente il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="5f9e8-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="5f9e8-107">Come funziona</span><span class="sxs-lookup"><span data-stu-id="5f9e8-107">How does it work?</span></span>

<span data-ttu-id="5f9e8-108">Quando viene eseguito il rilevamento duplicato, il sistema analizza tutti i documenti con testo.</span><span class="sxs-lookup"><span data-stu-id="5f9e8-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="5f9e8-109">Viene quindi confrontato ogni documento uno rispetto all'altro per determinare se la loro somiglianza è maggiore rispetto alla soglia impostata.</span><span class="sxs-lookup"><span data-stu-id="5f9e8-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="5f9e8-110">In questo caso, i documenti vengono raggruppati.</span><span class="sxs-lookup"><span data-stu-id="5f9e8-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="5f9e8-111">Una volta che tutti i documenti sono stati confrontati e raggruppati, un documento di ogni gruppo viene contrassegnato come "pivot"; durante la revisione dei documenti, è possibile esaminare prima un pivot ed esaminare gli altri documenti nello stesso set di duplicati vicino, concentrandosi sulla differenza tra il pivot e il documento in esame.</span><span class="sxs-lookup"><span data-stu-id="5f9e8-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
