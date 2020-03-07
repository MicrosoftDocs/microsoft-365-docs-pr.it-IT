---
title: Comprendere la somiglianza del documento in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'Esaminare in che modo il valore di somiglianza del documento, il livello minimo di somiglianza per due file da considerare quasi duplicati, è compatibile con Office 365 Advanced eDiscovery. '
ms.openlocfilehash: e15eb119a569c7cd296f9d3546969848808652da
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557666"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a><span data-ttu-id="53f47-103">Comprendere la somiglianza del documento in Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="53f47-103">Understand document similarity in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="53f47-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="53f47-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="53f47-106">In Advanced eDiscovery, la somiglianza dei documenti è il livello minimo di somiglianza necessario per due documenti che devono essere considerati quasi duplicati.</span><span class="sxs-lookup"><span data-stu-id="53f47-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="53f47-107">Per la maggior parte delle applicazioni aziendali, è consigliabile utilizzare un valore di somiglianza pari a 60%-75%.</span><span class="sxs-lookup"><span data-stu-id="53f47-107">For most business applications, it is recommended to use a Similarity value of 60%-75%.</span></span> <span data-ttu-id="53f47-108">Per il materiale OCR (Optical Character Recognition) di qualità molto scadente, è possibile applicare valori di similitudine inferiori.</span><span class="sxs-lookup"><span data-stu-id="53f47-108">For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="53f47-109">Dopo che è stato impostato ed eseguito per un determinato caso, il valore di somiglianza non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="53f47-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="53f47-110">All'interno di un insieme quasi duplicato, possono essere presenti documenti con un livello di somiglianza inferiore alla soglia di somiglianza.</span><span class="sxs-lookup"><span data-stu-id="53f47-110">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold.</span></span> <span data-ttu-id="53f47-111">Affinché un documento venga unito a un set ND, è necessario che sia presente almeno un documento nel set ND con un livello di somiglianza superiore alla somiglianza.</span><span class="sxs-lookup"><span data-stu-id="53f47-111">For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="53f47-112">Si supponga, ad esempio, che la somiglianza sia impostata su 80%, che Document F1 sia simile al documento F2 al livello 85% e che il documento F2 sia analogo al documento F3 al livello del 90%.</span><span class="sxs-lookup"><span data-stu-id="53f47-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="53f47-113">Tuttavia, il documento F1 può essere simile a quello F3 al livello di soli 70%, che è al di sotto della soglia.</span><span class="sxs-lookup"><span data-stu-id="53f47-113">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold.</span></span> <span data-ttu-id="53f47-114">Tuttavia, in questo esempio, i documenti F1, F2 e F3 vengono visualizzati tutti nel set ND.</span><span class="sxs-lookup"><span data-stu-id="53f47-114">Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set.</span></span> <span data-ttu-id="53f47-115">Analogamente, se si utilizza un valore di somiglianza pari a 80%, è possibile che siano stati creati due insiemi, EquiSet-1 e EquiSet-2.</span><span class="sxs-lookup"><span data-stu-id="53f47-115">Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2.</span></span> <span data-ttu-id="53f47-116">EquiSet-1 contiene i documenti E1 ed E2.</span><span class="sxs-lookup"><span data-stu-id="53f47-116">EquiSet-1 contains documents E1 and E2.</span></span> <span data-ttu-id="53f47-117">Equiset-2 contiene i documenti F1, F2 e F3.</span><span class="sxs-lookup"><span data-stu-id="53f47-117">Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="53f47-118">I livelli di somiglianza sono illustrati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="53f47-118">The levels of resemblance are illustrated as follows:</span></span>
  
![Somiglianza documento](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="53f47-120">Si supponga che un altro documento, x1, sia stato inserito.</span><span class="sxs-lookup"><span data-stu-id="53f47-120">Assume that another document, X1, is now inserted.</span></span> <span data-ttu-id="53f47-121">La somiglianza tra x1 e E3 è 87%.</span><span class="sxs-lookup"><span data-stu-id="53f47-121">The resemblance between X1 and E3 is 87%.</span></span> <span data-ttu-id="53f47-122">Analogamente, la somiglianza tra x1 e F1 è 92%.</span><span class="sxs-lookup"><span data-stu-id="53f47-122">Similarly, the resemblance between X1 and F1 is 92%.</span></span> <span data-ttu-id="53f47-123">Di conseguenza, EquiSet-1, EquiSet-2 e X1 vengono ora combinati in un solo set ND.</span><span class="sxs-lookup"><span data-stu-id="53f47-123">As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![Somiglianza documento](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="53f47-125">Se i due documenti vengono assegnati a un set ND, rimarranno insieme nello stesso set ND, anche se sono stati aggiunti altri documenti al set o se i set sono Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="53f47-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="53f47-126">Dopo la fusione dei set, il documento pivot può variare quando vengono aggiunti nuovi documenti a un set.</span><span class="sxs-lookup"><span data-stu-id="53f47-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="53f47-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53f47-127">See also</span></span>

[<span data-ttu-id="53f47-128">Advanced eDiscovery (classica)</span><span class="sxs-lookup"><span data-stu-id="53f47-128">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="53f47-129">Impostazione delle opzioni di analisi</span><span class="sxs-lookup"><span data-stu-id="53f47-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="53f47-130">Impostazione Ignora testo</span><span class="sxs-lookup"><span data-stu-id="53f47-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="53f47-131">Impostazione analisi impostazioni avanzate</span><span class="sxs-lookup"><span data-stu-id="53f47-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="53f47-132">Visualizzazione dei risultati dell'analisi</span><span class="sxs-lookup"><span data-stu-id="53f47-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

