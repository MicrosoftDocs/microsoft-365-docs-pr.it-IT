---
title: Sfruttare la tassonomia dell'archivio termini durante la creazione di un estrattore
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Sfruttare la tassonomia dell'archivio termini durante la creazione di un estrattore nel modello di analisi dei documenti in Microsoft SharePoint Syntex.
ms.openlocfilehash: 0008dd02ef46401e9f0c9414b8363cff034c18eb
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087322"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="f4bdd-103">Sfruttare la tassonomia dell'archivio termini durante la creazione di un estrattore</span><span class="sxs-lookup"><span data-stu-id="f4bdd-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>


<span data-ttu-id="f4bdd-104">Quando si crea un estrattore nel modello dianalisi dei documenti in SharePoint Syntex, è possibile sfruttare la tassonomia dell'archivio termini dei [Servizi di Metadati](https://docs.microsoft.com/sharepoint/managed-metadata#terms) gestiti per visualizzare i termini preferiti per i dati estratti.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="f4bdd-105">Ad esempio, il modello identifica e classifica tutti i documenti del **Contratto** caricati nella raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="f4bdd-106">Inoltre, il modello estrae anche un valore del **Servizio del contratto** da ogni contratto e lo visualizzerà in una colonna nella visualizzazione della libreria.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="f4bdd-107">Tra i vari valori dei Servizi del contratto nei contratti sono disponibili diversi valori meno recenti che non vengono più usati dall'azienda e sono stati rinominati.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="f4bdd-108">Ad esempio, tutti i riferimenti ai termini servizi del contratto come *Progettazione*, *Grafica* o *Topografia* saranno chiamati *Creativo*.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="f4bdd-109">Ogni volta che il modello estrae uno dei termini obsoleti da un documento contrattuale, si vuole che venga visualizzato il termine corrente - Creativo - nella visualizzazione della raccolta.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="f4bdd-110">Nell'esempio seguente, durante la formazione del modello, è possibile notare che un documento di esempio contiene il termine obsoleto *Progettazione*.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Archivio termini](../media/content-understanding/design.png)</br>


## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="f4bdd-112">Usare una colonna metadati gestiti nell'estrattore</span><span class="sxs-lookup"><span data-stu-id="f4bdd-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="f4bdd-113">I set di termini vengono configurati nell'archivio termini dei servizi metadati gestiti nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="f4bdd-114">Nell'esempio seguente, il *set di termini* per i [Servizi di contratto](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) è configurato per includere una serie di termini, tra cui *Creativo*.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="f4bdd-115">I dettagli mostrano che il termine ha tre sinonimi (*Progettazione*, *Grafica* e *Topografia*) e i sinonimi devono essere tradotti in *Creativo*.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![Set di termini](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="f4bdd-117">Ci sono diversi motivi per cui è consigliabile usare un sinonimo nel set di termini.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-117">There could be a number of reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="f4bdd-118">Ad esempio, potrebbero esserci termini obsoleti, termini rinominati o variazioni tra i reparti dell'organizzazione per quanto riguarda la denominazione.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-118">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="f4bdd-119">Per fare in modo che il campo metadati gestiti sia disponibile quando si crea l'estrazione nel modello, è necessario [aggiungerlo come colonna del sito metadati gestiti](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span><span class="sxs-lookup"><span data-stu-id="f4bdd-119">To make the managed metadata field available for you to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="f4bdd-120">Dopo aver aggiunto la colonna del sito, sarà disponibile per la selezione quando si crea l'estrattore per il modello.</span><span class="sxs-lookup"><span data-stu-id="f4bdd-120">After you add the site column, it will be available for you to select when you create the extractor for your model.</span></span>

   ![Servizio di contratto](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="f4bdd-122">Dopo aver applicato il modello alla raccolta documenti, quando i documenti vengono caricati nella raccolta, la colonna *Servizi creativi* mostrerà il termine preferito (*Creativo*) quando l'estrattore trova uno dei valori dei sinonimi (*Progettazione*, *Grafica* e *Topografia*).</span><span class="sxs-lookup"><span data-stu-id="f4bdd-122">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![Colonna Servizio di contratto](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="f4bdd-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4bdd-124">See Also</span></span>
[<span data-ttu-id="f4bdd-125">Introduzione ai metadati gestiti</span><span class="sxs-lookup"><span data-stu-id="f4bdd-125">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[<span data-ttu-id="f4bdd-126">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="f4bdd-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="f4bdd-127">Creare una colonna di metadati gestiti</span><span class="sxs-lookup"><span data-stu-id="f4bdd-127">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





