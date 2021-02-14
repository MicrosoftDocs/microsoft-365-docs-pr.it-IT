---
title: Rilevamento quasi duplicato - eDiscovery
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
description: Utilizzare il rilevamento quasi duplicato per raggruppare documenti simili in formato testo durante l'analisi dei dati del caso in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286022"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="01903-103">Rilevamento quasi duplicato in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="01903-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="01903-104">È consigliabile esaminare un set di documenti in cui un sottoinsieme è basato sullo stesso modello e ha principalmente lo stesso linguaggio boilerplate, con alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="01903-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="01903-105">Se un revisore è in grado di identificare questo sottoinsieme, esaminarne accuratamente uno ed esaminare le differenze per il resto, non avrebbe perso informazioni univoche, occupando solo una frazione di tempo che li avrebbe portati a leggere tutte le copertine dei documenti da coprire.</span><span class="sxs-lookup"><span data-stu-id="01903-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="01903-106">I gruppi di rilevamento quasi duplicati sono in grado di riunire documenti simili in modo testuale per rendere più efficiente il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="01903-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="01903-107">Come funziona?</span><span class="sxs-lookup"><span data-stu-id="01903-107">How does it work?</span></span>

<span data-ttu-id="01903-108">Quando viene eseguito il rilevamento quasi duplicato, il sistema analizza ogni documento con testo.</span><span class="sxs-lookup"><span data-stu-id="01903-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="01903-109">Quindi, confronta ogni documento l'uno con l'altro per determinare se la loro similarità è maggiore della soglia impostata.</span><span class="sxs-lookup"><span data-stu-id="01903-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="01903-110">In caso contrario, i documenti vengono raggruppati.</span><span class="sxs-lookup"><span data-stu-id="01903-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="01903-111">Dopo che tutti i documenti sono stati confrontati e raggruppati, un documento di ogni gruppo viene contrassegnato come "pivot"; durante la revisione dei documenti, è possibile esaminare prima un pivot e gli altri documenti nello stesso set di duplicati vicini, concentrandosi sulla differenza tra il pivot e il documento in revisione.</span><span class="sxs-lookup"><span data-stu-id="01903-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
