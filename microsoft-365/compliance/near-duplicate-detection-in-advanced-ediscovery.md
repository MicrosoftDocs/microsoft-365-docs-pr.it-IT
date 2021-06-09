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
description: Utilizzare il rilevamento quasi duplicato per raggruppare documenti testualmente simili durante l'analisi dei dati del caso in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286022"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="69f88-103">Rilevamento quasi duplicato in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="69f88-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="69f88-104">Considerare un set di documenti da rivedere in cui un sottoinsieme è basato sullo stesso modello e ha principalmente lo stesso linguaggio boilerplate, con alcune differenze qua e là.</span><span class="sxs-lookup"><span data-stu-id="69f88-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="69f88-105">Se un revisore è in grado di identificare questo sottoinsieme, esaminarne uno a fondo ed esaminare le differenze per il resto, non avrebbe perso alcuna informazione univoca, pur occupando solo una frazione di tempo che li avrebbe portati a leggere tutti i documenti a copertura.</span><span class="sxs-lookup"><span data-stu-id="69f88-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="69f88-106">Il rilevamento di documenti simili raggruppa documenti con similarità testuali per contribuire a rendere più efficiente il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="69f88-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="69f88-107">Come funziona?</span><span class="sxs-lookup"><span data-stu-id="69f88-107">How does it work?</span></span>

<span data-ttu-id="69f88-108">Quando viene eseguito il rilevamento di documenti simili, il sistema analizza ogni documento con testo.</span><span class="sxs-lookup"><span data-stu-id="69f88-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="69f88-109">Confronta quindi ogni documento con gli altri per determinare se la similarità è maggiore della soglia impostata.</span><span class="sxs-lookup"><span data-stu-id="69f88-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="69f88-110">Se è questo il caso, i documenti vengono raggruppati.</span><span class="sxs-lookup"><span data-stu-id="69f88-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="69f88-111">Dopo aver confrontato e raggruppato tutti i documenti, un documento di ogni gruppo viene contrassegnato come "pivot"; durante la revisione dei documenti, è possibile esaminare prima il pivot e dopo gli altri documenti dello stesso insieme, concentrandosi sulla differenza tra il pivot e il documento in revisione.</span><span class="sxs-lookup"><span data-stu-id="69f88-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
