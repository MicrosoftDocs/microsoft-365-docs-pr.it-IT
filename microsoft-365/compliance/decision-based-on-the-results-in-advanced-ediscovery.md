---
title: Decisione basata sui risultati in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: 'Informazioni su come la scheda decidere in Office 365 Advanced eDiscovery fornisce dati che consentono di determinare le dimensioni corrette del set di riesame dei file di caso. '
ms.openlocfilehash: 6d515305b01b0273bb2acffaad19c497fc5c82d2
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557544"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="2a7b1-103">Decisione basata sui risultati in Advanced eDiscovery (Classic)</span><span class="sxs-lookup"><span data-stu-id="2a7b1-103">Decision based on the results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="2a7b1-p101">Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="2a7b1-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="2a7b1-106">In Advanced eDiscovery, la scheda decide fornisce informazioni aggiuntive per la visualizzazione e l'utilizzo delle statistiche di supporto decisionale per determinare le dimensioni del set di riesame dei file di caso.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="2a7b1-107">Utilizzo della scheda decide</span><span class="sxs-lookup"><span data-stu-id="2a7b1-107">Using the Decide tab</span></span>

![Decisione di pertinenza](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="2a7b1-109">Questa scheda include gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a7b1-109">This tab includes the following:</span></span>
  
- <span data-ttu-id="2a7b1-110">**Problema**: da qui, è possibile selezionare il problema di interesse dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="2a7b1-111">**Rapporto Revisione-richiamo**: confronto tra la revisione avanzata di eDiscovery in base ai punteggi di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-111">**Review-recall ratio**: Comparison of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="2a7b1-112">Il punto di taglio nel grafico rappresenta la percentuale di file da esaminare, mappata a un punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-112">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="2a7b1-113">Questo valore viene utilizzato nella fase di test di pertinenza e come soglia di esportazione per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-113">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="2a7b1-114">Il punto di taglio predefinito per il numero di file da esaminare è il punto in cui il bilanciamento tra richiamo e precisione è ottimale.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-114">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="2a7b1-115">Il punto di taglio effettivo dovrebbe essere determinato dall'utente a seconda degli obiettivi e del compromesso dei costi (% revisione) e del rischio (% Recall). Utilizzando il dispositivo di scorrimento, è possibile regolare il punto di taglio e vedere l'effetto sul grafico e sui parametri, quando si modifica la percentuale di file rilevanti da recuperare e prima di convalidare una decisione.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-115">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="2a7b1-116">**Parametri**: Review, Recall, Next rilevanti and Total cost Parameters sono statistiche calcolate cumulative relative al set di revisione in relazione alla raccolta per l'intero caso.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-116">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="2a7b1-117">Le definizioni per questi parametri sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a7b1-117">Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="2a7b1-118">**Recensione**: percentuale di file da esaminare in base a questo cutoff.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-118">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="2a7b1-119">**Richiamo**: percentuale dei file rilevanti nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-119">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="2a7b1-120">**Next pertinente**: costo per la revisione e l'identificazione di un ulteriore file pertinente che non è attualmente incluso nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-120">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="2a7b1-121">**Costo totale**: costo per la revisione di questa percentuale dei file del caso.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-121">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="2a7b1-122">Le impostazioni dei parametri di costo possono essere impostate dal responsabile del caso.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-122">Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="2a7b1-123">**Distribuzione per Punteggio di pertinenza**: i file nel display grigio scuro a sinistra sono al di sotto del Punteggio di taglio.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-123">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="2a7b1-124">Un suggerimento per gli strumenti Visualizza il Punteggio di pertinenza e la percentuale relativa di file nel set di file di revisione in relazione ai file totali.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-124">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="2a7b1-125">Nel riquadro dettagli espansi vengono visualizzati ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-125">The expanded Details pane displays additional details.</span></span> <span data-ttu-id="2a7b1-126">I file nelle figure delle raccolte non includono file vuoti o nebulosi.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-126">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="2a7b1-127">Le figure dei file di famiglia rappresentano i file che non sono caricati in rilevanza, ma vengono comunque conteggiati come parte della famiglia.</span><span class="sxs-lookup"><span data-stu-id="2a7b1-127">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2a7b1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a7b1-128">See also</span></span>

[<span data-ttu-id="2a7b1-129">Advanced eDiscovery (classica)</span><span class="sxs-lookup"><span data-stu-id="2a7b1-129">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2a7b1-130">Informazioni sulla valutazione in rilevanza</span><span class="sxs-lookup"><span data-stu-id="2a7b1-130">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a7b1-131">Tagging e valutazione</span><span class="sxs-lookup"><span data-stu-id="2a7b1-131">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a7b1-132">Esecuzione della formazione sulla pertinenza</span><span class="sxs-lookup"><span data-stu-id="2a7b1-132">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a7b1-133">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="2a7b1-133">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2a7b1-134">Verifica dell'analisi della pertinenza</span><span class="sxs-lookup"><span data-stu-id="2a7b1-134">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

