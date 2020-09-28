---
title: Tassonomia dell'archivio termini di sfruttamento durante la creazione di un estrattore
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Tassonomia dei termini di sfruttamento dei dati durante la creazione di un estrattore nel modello di comprensione del documento in Microsoft SharePoint Syntex.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296014"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="ba3f3-103">Tassonomia dell'archivio termini di sfruttamento durante la creazione di un estrattore</span><span class="sxs-lookup"><span data-stu-id="ba3f3-103">Leverage term store taxonomy when creating an extractor</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="ba3f3-104">Quando si crea un estrattore nel modello di comprensione dei documenti in SharePoint Syntex, è possibile utilizzare la tassonomia archivio termini di [servizi metadati gestiti](https://docs.microsoft.com/sharepoint/managed-metadata#terms) per visualizzare le condizioni preferite per i dati estratti.</span><span class="sxs-lookup"><span data-stu-id="ba3f3-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="ba3f3-105">Ad esempio, il modello identifica e classifica tutti i documenti del **contratto** caricati nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="ba3f3-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="ba3f3-106">Inoltre, il modello estrae un valore del **servizio contratto** da ogni contratto e lo Visualizza in una colonna della visualizzazione libreria.</span><span class="sxs-lookup"><span data-stu-id="ba3f3-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="ba3f3-107">Tra i vari valori dei servizi contratto nei contratti, esistono diversi valori precedenti che la società non utilizza più e che sono stati rinominati.</span><span class="sxs-lookup"><span data-stu-id="ba3f3-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="ba3f3-108">Ad esempio, tutti i riferimenti ai termini *progettazione*, *grafica*o servizi contratto di *topografia* dovrebbero ora essere chiamati *creativi*.</span><span class="sxs-lookup"><span data-stu-id="ba3f3-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="ba3f3-109">Ogni volta che il modello estrae uno dei termini obsoleti da un documento del contratto, si desidera che visualizzi il termine-creatività corrente nella visualizzazione libreria.</span><span class="sxs-lookup"><span data-stu-id="ba3f3-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="ba3f3-110">Nell'esempio riportato di seguito, durante l'addestramento del modello viene visualizzato che un documento di esempio contiene il termine obsoleto di *progettazione*.</span><span class="sxs-lookup"><span data-stu-id="ba3f3-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Archivio termini](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a><span data-ttu-id="ba3f3-112">Sinonimi set di termini</span><span class="sxs-lookup"><span data-stu-id="ba3f3-112">Term set synonyms</span></span> 

<span data-ttu-id="ba3f3-113">I set di termini sono configurati nell'archivio termini dei servizi metadati gestiti nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ba3f3-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="ba3f3-114">Nell'esempio riportato di seguito, il [set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) di termini *Servizi contratto* è configurato per includere una serie di condizioni, tra cui la *creatività*.</span><span class="sxs-lookup"><span data-stu-id="ba3f3-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="ba3f3-115">I dettagli indicano che il termine ha tre sinonimi (*progettazione*, *grafica*e *topografia*) e che i sinonimi devono essere tradotti in *creatività*.</span><span class="sxs-lookup"><span data-stu-id="ba3f3-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span>

   ![Term set](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="ba3f3-117"><Mike, ecco dove non sono sicuro su come descriverlo.</span><span class="sxs-lookup"><span data-stu-id="ba3f3-117"><Mike, here is where I am unsure about how to describe this.</span></span>  <span data-ttu-id="ba3f3-118">Azione indica al modello che quando si crea un estrattore per estrarre e visualizzare una colonna di servizi contratto, come viene indicata la colonna "contrassegnato" per l'utilizzo del set di termini per i metadati gestiti per i servizi creativi? ></span><span class="sxs-lookup"><span data-stu-id="ba3f3-118">What action tells the model that when I create an extractor to extract and display a Contract Services column, how is that column "marked" to use the managed metadata term set for Creative Services?></span></span>

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a><span data-ttu-id="ba3f3-119">Configurare la colonna del sito della raccolta documenti per un campo metadati gestiti</span><span class="sxs-lookup"><span data-stu-id="ba3f3-119">Configure your document library site column for a managed metadata field</span></span>


   ![Creare metadati gestiti](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a><span data-ttu-id="ba3f3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba3f3-121">See Also</span></span>
[<span data-ttu-id="ba3f3-122">Introduzione ai metadati gestiti</span><span class="sxs-lookup"><span data-stu-id="ba3f3-122">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[<span data-ttu-id="ba3f3-123">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="ba3f3-123">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="ba3f3-124">Creare una colonna di metadati gestiti</span><span class="sxs-lookup"><span data-stu-id="ba3f3-124">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





