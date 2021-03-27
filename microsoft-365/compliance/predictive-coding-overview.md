---
title: Modulo di codifica predittiva per Advanced eDiscovery (anteprima)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Il nuovo modulo di codifica predittiva in Advanced eDiscovery utilizza l'apprendimento automatico per analizzare i documenti in un set di revisione per prevedere quali documenti sono rilevanti per il caso o l'indagine.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382974"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a><span data-ttu-id="835c8-103">Modulo di codifica predittiva per Advanced eDiscovery (anteprima)</span><span class="sxs-lookup"><span data-stu-id="835c8-103">Predictive coding module for Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="835c8-104">Utilizzando il nuovo modulo di codifica predittiva in Advanced eDiscovery, è possibile creare e creare un modello per assegnare priorità alla revisione dei documenti a partire dai documenti più rilevanti.</span><span class="sxs-lookup"><span data-stu-id="835c8-104">Using the new predictive coding module in Advanced eDiscovery, you can create and build a model to prioritize review of documents starting with the most relevant documents.</span></span> <span data-ttu-id="835c8-105">Per iniziare, è possibile creare un modello, etichettare fino a 50 documenti e quindi filtrare i documenti in base ai punteggi di previsione del modello per esaminare i documenti non rilevanti.</span><span class="sxs-lookup"><span data-stu-id="835c8-105">To get started, you can create a model, label as few as 50 documents, and then filter documents by model prediction scores to review relevant non-relevant documents.</span></span>

<span data-ttu-id="835c8-106">Ecco una breve panoramica del flusso di lavoro:</span><span class="sxs-lookup"><span data-stu-id="835c8-106">Here’s a quick overview of the workflow:</span></span>

1. <span data-ttu-id="835c8-107">Aprire il modulo di codifica predittiva in un set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="835c8-107">Open the predictive coding module in a review set.</span></span>

   ![Fare clic sull'elenco a discesa Analizza in una recensione per passare al modulo di codifica predittiva](..\media\PredictiveCoding1.png)

2. <span data-ttu-id="835c8-109">Nella pagina **Modelli di codifica predittiva** fare clic su **Nuovo modello** per creare un nuovo modello di codifica predittiva.</span><span class="sxs-lookup"><span data-stu-id="835c8-109">On the **Predictive coding models** page, click **New model** to create a new predictive coding model.</span></span>

   ![Creare un nuovo modello](..\media\PredictiveCoding2.png)

3. <span data-ttu-id="835c8-111">Etichettare almeno 50 documenti come **rilevanti** o **non rilevanti.**</span><span class="sxs-lookup"><span data-stu-id="835c8-111">Label at least 50 documents as **Relevant** or **Not relevant**.</span></span> <span data-ttu-id="835c8-112">Questa etichettatura viene utilizzata per eseguire il training del sistema.</span><span class="sxs-lookup"><span data-stu-id="835c8-112">This labeling is used to train the system.</span></span>

   ![Etichettare i documenti come rilevanti o non rilevanti per la formazione del sistema](..\media\PredictiveCoding3.png)

4. <span data-ttu-id="835c8-114">Applica il **filtro Punteggio previsione** per il modello al set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="835c8-114">Apply the **Prediction score** filter for your model to the review set.</span></span> <span data-ttu-id="835c8-115">Per eseguire l'operazione:</span><span class="sxs-lookup"><span data-stu-id="835c8-115">To do this:</span></span>

   1. <span data-ttu-id="835c8-116">Nell'insieme di revisioni fare clic su **Filtri.**</span><span class="sxs-lookup"><span data-stu-id="835c8-116">In the review set, click **Filters**.</span></span>
   2. <span data-ttu-id="835c8-117">Nella pagina **a** comparsa Filtri espandi la **sezione Analytics/ML** e quindi seleziona la casella di controllo **Punteggio** di previsione per il modello che vuoi applicare.</span><span class="sxs-lookup"><span data-stu-id="835c8-117">In the **Filters** flyout page, expand the **Analytics/ML** section and then select **Prediction score** checkbox for the model you want to apply.</span></span>
   3. <span data-ttu-id="835c8-118">Nel filtro **Punteggio di previsione** specificare un punteggio di previsione.</span><span class="sxs-lookup"><span data-stu-id="835c8-118">In the **Prediction score** filter, specify a prediction score.</span></span> <span data-ttu-id="835c8-119">Il filtro visualizza i documenti nel set di revisione che corrispondono al punteggio di previsione.</span><span class="sxs-lookup"><span data-stu-id="835c8-119">The filter will display the documents in the review set that match the prediction score.</span></span>

      ![Specificare un punteggio di previsione per filtrare i documenti](..\media\PredictiveCoding4.png)

5. <span data-ttu-id="835c8-121">Monitorare le prestazioni, lo stato e la stabilità del modello.</span><span class="sxs-lookup"><span data-stu-id="835c8-121">Monitor the performance, status, and stability of your model.</span></span>

   ![Monitorare le prestazioni, lo stato e la stabilità del modello](..\media\PredictiveCoding5.png)
