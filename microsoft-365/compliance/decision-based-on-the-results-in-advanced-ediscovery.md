---
title: Decisione basata sui risultati in Advanced eDiscovery
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
description: Informazioni su come la scheda decidere in Advanced eDiscovery fornisce dati che consentono di determinare le dimensioni corrette del set di revisione dei file di caso.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769151"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="331c0-103">Decisioni basate sui risultati di pertinenza in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="331c0-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="331c0-104">Nel modulo pertinenza in Advanced eDiscovery, la scheda decidere fornisce informazioni aggiuntive per la visualizzazione e l'utilizzo delle statistiche del supporto decisionale per determinare le dimensioni del set di revisione dei file di caso.</span><span class="sxs-lookup"><span data-stu-id="331c0-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="331c0-105">Utilizzo della scheda decide</span><span class="sxs-lookup"><span data-stu-id="331c0-105">Using the Decide tab</span></span>

![Decisione di pertinenza](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="331c0-107">In questa scheda sono inclusi i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="331c0-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="331c0-108">**Problema**: da qui, è possibile selezionare il problema di interesse dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="331c0-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="331c0-109">**Rapporto Revisione-richiamo**: confronto tra la revisione avanzata di eDiscovery in base ai punteggi di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="331c0-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="331c0-110">Il punto di taglio nel grafico rappresenta la percentuale di file da esaminare, mappata a un punteggio di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="331c0-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="331c0-111">Questo valore viene utilizzato nella fase di test di pertinenza e come soglia di esportazione per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="331c0-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="331c0-112">Il punto di taglio predefinito per il numero di file da esaminare è il punto in cui il bilanciamento tra richiamo e precisione è ottimale.</span><span class="sxs-lookup"><span data-stu-id="331c0-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="331c0-113">Il punto di taglio effettivo dovrebbe essere determinato dall'utente a seconda degli obiettivi e del compromesso dei costi (% revisione) e del rischio (% Recall).</span><span class="sxs-lookup"><span data-stu-id="331c0-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="331c0-114">Utilizzando il dispositivo di scorrimento, è possibile regolare il punto di taglio e vedere l'effetto sul grafico e sui parametri, quando si modifica la percentuale di file rilevanti da recuperare e prima di convalidare una decisione.</span><span class="sxs-lookup"><span data-stu-id="331c0-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="331c0-115">**Parametri**: Review, Recall, Next rilevanti and Total cost Parameters sono statistiche calcolate cumulative relative al set di revisione in relazione alla raccolta per l'intero caso.</span><span class="sxs-lookup"><span data-stu-id="331c0-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="331c0-116">Le definizioni per questi parametri sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="331c0-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="331c0-117">**Recensione**: percentuale di file da esaminare in base a questo cutoff.</span><span class="sxs-lookup"><span data-stu-id="331c0-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="331c0-118">**Richiamo**: percentuale dei file rilevanti nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="331c0-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="331c0-119">**Next pertinente**: costo per la revisione e l'identificazione di un altro file pertinente che non è attualmente incluso nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="331c0-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="331c0-120">**Costo totale**: costo per la revisione di questa percentuale dei file del caso.</span><span class="sxs-lookup"><span data-stu-id="331c0-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="331c0-121">Le impostazioni dei parametri di costo possono essere impostate dal responsabile del caso.</span><span class="sxs-lookup"><span data-stu-id="331c0-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="331c0-122">**Distribuzione per Punteggio di pertinenza**: i file nel display grigio scuro a sinistra sono al di sotto del Punteggio di taglio.</span><span class="sxs-lookup"><span data-stu-id="331c0-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="331c0-123">Un suggerimento per gli strumenti Visualizza il Punteggio di pertinenza e la percentuale relativa di file nel set di file di revisione in relazione ai file totali.</span><span class="sxs-lookup"><span data-stu-id="331c0-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="331c0-124">Nel riquadro **Dettagli** espansi vengono visualizzati ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="331c0-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="331c0-125">I file nelle figure delle raccolte non includono file vuoti o nebulosi.</span><span class="sxs-lookup"><span data-stu-id="331c0-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="331c0-126">Le figure dei file di famiglia rappresentano i file che non sono caricati in rilevanza, ma vengono comunque conteggiati come parte della famiglia.</span><span class="sxs-lookup"><span data-stu-id="331c0-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
