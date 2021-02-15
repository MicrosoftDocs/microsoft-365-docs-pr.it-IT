---
title: Decisione basata sui risultati di Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: Informazioni su come la scheda Decide in Advanced eDiscovery fornisce dati che consentono di determinare le dimensioni corrette del set di file del caso da rivedere.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769151"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="2a834-103">Decisioni basate sui risultati di pertinenza in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2a834-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="2a834-104">Nel modulo Rilevanza in Advanced eDiscovery, la scheda Decide fornisce informazioni aggiuntive per la visualizzazione e l'utilizzo delle statistiche di supporto decisionale per determinare le dimensioni del set di file del caso da rivedere.</span><span class="sxs-lookup"><span data-stu-id="2a834-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="2a834-105">Uso della scheda Decide</span><span class="sxs-lookup"><span data-stu-id="2a834-105">Using the Decide tab</span></span>

![Decisione di pertinenza](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="2a834-107">Questa scheda include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a834-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="2a834-108">**Problema:** da qui è possibile selezionare l'emissione di interesse dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="2a834-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="2a834-109">**Rapporto revisione-richiamo**: confronti della revisione di Advanced eDiscovery in base ai punteggi di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="2a834-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="2a834-110">Il punto di taglio nel grafico rappresenta la percentuale di file da esaminare, mappata a un punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="2a834-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="2a834-111">Viene usato nella fase di test di pertinenza e come soglia di esportazione per il culling.</span><span class="sxs-lookup"><span data-stu-id="2a834-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="2a834-112">Il punto di taglio predefinito, per il numero di file da esaminare, è il punto in cui il bilanciamento tra richiamo e precisione è ottimale.</span><span class="sxs-lookup"><span data-stu-id="2a834-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="2a834-113">Il punto di taglio effettivo deve essere determinato dall'utente in base agli obiettivi e al compromesso dei costi (%review) e del rischio (%recall).</span><span class="sxs-lookup"><span data-stu-id="2a834-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="2a834-114">Usando il dispositivo di scorrimento, puoi regolare il punto di taglio e vedere l'effetto sul grafico e sui parametri, quando regola la percentuale di file rilevanti da recuperare e prima di convalidare una decisione.</span><span class="sxs-lookup"><span data-stu-id="2a834-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="2a834-115">**Parametri**: i parametri Review, Recall, Next relevant e Total cost sono statistiche calcolate cumulative relative alla revisione impostata in relazione alla raccolta per l'intero caso.</span><span class="sxs-lookup"><span data-stu-id="2a834-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="2a834-116">Le definizioni per questi parametri sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a834-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="2a834-117">**Review:** percentuale di file da esaminare in base a questa riduzione.</span><span class="sxs-lookup"><span data-stu-id="2a834-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="2a834-118">**Richiamo:** percentuale di file rilevanti nel set da rivedere.</span><span class="sxs-lookup"><span data-stu-id="2a834-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="2a834-119">**Successivo pertinente:** Costo per la revisione e l'identificazione di un altro file rilevante che non è attualmente presente nel set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="2a834-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="2a834-120">**Costo totale:** costo per la revisione di questa percentuale dei file dei casi.</span><span class="sxs-lookup"><span data-stu-id="2a834-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="2a834-121">Le impostazioni dei parametri dei costi possono essere impostate dal responsabile del caso.</span><span class="sxs-lookup"><span data-stu-id="2a834-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="2a834-122">**Distribuzione in base al punteggio di** pertinenza: i file nella visualizzazione grigio scuro a sinistra sono al di sotto del punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="2a834-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="2a834-123">Una descrizione comando visualizza il punteggio di pertinenza e la percentuale correlata di file nel set di file da rivedere in relazione al totale dei file.</span><span class="sxs-lookup"><span data-stu-id="2a834-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="2a834-124">Nel riquadro **dettagli** espanso vengono visualizzati altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="2a834-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="2a834-125">I file nelle figure della raccolta non includono file vuoti o nebulosi.</span><span class="sxs-lookup"><span data-stu-id="2a834-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="2a834-126">Le figure dei file di famiglia rappresentano i file non caricati in Rilevanza, ma ancora conteggiati come parte della famiglia.</span><span class="sxs-lookup"><span data-stu-id="2a834-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
