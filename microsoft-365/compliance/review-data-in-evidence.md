---
title: Esaminare i dati nelle prove
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
description: ''
ms.openlocfilehash: 20ac1adb67014439110e355025b31753a4a6bcfe
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084752"
---
# <a name="review-the-data-in-evidence"></a><span data-ttu-id="d0d41-102">Esaminare i dati nelle prove</span><span class="sxs-lookup"><span data-stu-id="d0d41-102">Review the data in evidence</span></span>

<span data-ttu-id="d0d41-103">I dati di un set di evidenze in un'analisi dei dati sono uno snapshot dei risultati della ricerca raccolti e aggiunti al set di evidenze.</span><span class="sxs-lookup"><span data-stu-id="d0d41-103">The data in an evidence set in a data investigation is a snapshot of the search results that you collected and added to the evidence set.</span></span> <span data-ttu-id="d0d41-104">Quando si aggiungono i risultati della ricerca all'evidenza, viene attivato un processo per estrarre file, metadati e testo dagli elementi restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="d0d41-104">When you add search results to evidence, a process is triggered to extract files, metadata, and text from the items returned by the search.</span></span> <span data-ttu-id="d0d41-105">Successivamente, lo strumento indagini dati (Preview) crea un nuovo indice (tramite un processo denominato *Advanced indicizzazione*) di tutti i dati e aggiunge a un set di evidenze nella scheda **Evidence** .</span><span class="sxs-lookup"><span data-stu-id="d0d41-105">Then the Data Investigations (Preview) tool then builds a new index (by a process called *Advanced indexing*) of all the data and adds to an evidence set on the **Evidence** tab.</span></span> 

<span data-ttu-id="d0d41-106">Per le indagini sensibili al tempo, in questo modo è possibile contenere rapidamente l'ambiente eliminando i dati effettivamente riversati o dannosi che si trovano nell'origine dati originale, mentre allo stesso tempo è possibile esaminare l'evidenza ricreata in un ambiente in quarantena, che in questo caso è il dato copiato nel set di evidenze.</span><span class="sxs-lookup"><span data-stu-id="d0d41-106">For time-sensitive investigations, this allows you to quickly contain the environment by deleting the actual spilled or malicious data located in the at original data source, while at the same time allowing you to investigate the re-created evidence in a quarantined environment, which in this case is the data copied to the evidence set).</span></span> <span data-ttu-id="d0d41-107">Dopo la raccolta e l'aggiunta dell'evidenza al set di evidenze, è possibile esaminare i singoli documenti nel formato nativo, nel formato di testo o in un formato quasi nativo che è possibile utilizzare per annotare e redigere i documenti.</span><span class="sxs-lookup"><span data-stu-id="d0d41-107">After the evidence is collected and added to the evidence set, you can review individual documents in their native format, text format, or a near-native format that you can use to annotate and redact documents.</span></span> <span data-ttu-id="d0d41-108">È inoltre possibile eseguire query per limitare il set di dati in base a intervallo di tempo, tipi di file, proprietari di dati e molte altre proprietà e condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d0d41-108">Additionally, you can run queries to narrow the data set by time range, file types, data owners, and many other properties and search conditions.</span></span> <span data-ttu-id="d0d41-109">Ad esempio, utilizzando le condizioni di autore, mittente o destinatario, è possibile identificare rapidamente le persone coinvolte nell'incidente e se i dati dell'organizzazione sono stati condivisi con utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="d0d41-109">For example, by using the Author, Sender, or Recipient conditions, you can quickly identify the people are involved in the incident and if any data from your organization has been shared with external users.</span></span> <span data-ttu-id="d0d41-110">Per ulteriori informazioni sulla ricerca di dati in un set di evidenze, vedere [query the data in evidence](evidence-query.md).</span><span class="sxs-lookup"><span data-stu-id="d0d41-110">For more information about searching through data in an evidence set, see [Query the data in evidence](evidence-query.md).</span></span>

<span data-ttu-id="d0d41-111">Per raggruppare i documenti e ottenere assistenza per la revisione, selezionare un set di evidenze nella scheda **Evidence** e quindi fare clic su **Gestisci prova**.</span><span class="sxs-lookup"><span data-stu-id="d0d41-111">To group documents and get more assistance for your review, select an evidence set on the **Evidence** tab, and then click **Manage evidence**.</span></span> <span data-ttu-id="d0d41-112">Nel riquadro **analisi** fare clic su **Ricostruisci analisi per l'intero set**.</span><span class="sxs-lookup"><span data-stu-id="d0d41-112">In the **Analytics** tile, click **Rebuild analytics for the whole set**.</span></span> <span data-ttu-id="d0d41-113">Verrà eseguito l'analisi avanzata, ad esempio il rilevamento duplicato, il threading di posta elettronica e l'analizzatore dei temi.</span><span class="sxs-lookup"><span data-stu-id="d0d41-113">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="d0d41-114">Successivamente, è possibile visualizzare i temi generali dei dati e anche organizzare i documenti tramite thread di posta elettronica, vicino a duplicati e duplicati esatti per facilitare l'indagine.</span><span class="sxs-lookup"><span data-stu-id="d0d41-114">Afterwards, you can see the general themes of the data and also organize documents by email threads, near duplicates, and exact duplicates to help your investigation.</span></span> <span data-ttu-id="d0d41-115">Per ulteriori informazioni, vedere [Run Analytics to investigate Faster](run-analytics-to-investigate-faster.md).</span><span class="sxs-lookup"><span data-stu-id="d0d41-115">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span>

## <a name="view-documents-in-evidence"></a><span data-ttu-id="d0d41-116">Visualizzare i documenti in evidenza</span><span class="sxs-lookup"><span data-stu-id="d0d41-116">View documents in evidence</span></span>

<span data-ttu-id="d0d41-117">Indagini sui dati (Preview) consente di visualizzare il contenuto in diversi visualizzatori, in cui ogni visualizzatore ha uno scopo diverso.</span><span class="sxs-lookup"><span data-stu-id="d0d41-117">Data Investigations (Preview) allows you to display content in several different viewers, with each viewer having a different purpose.</span></span> <span data-ttu-id="d0d41-118">Questi visualizzatori sono:</span><span class="sxs-lookup"><span data-stu-id="d0d41-118">These viewers are:</span></span>

- <span data-ttu-id="d0d41-119">Metadati dei file</span><span class="sxs-lookup"><span data-stu-id="d0d41-119">File metadata</span></span>
- <span data-ttu-id="d0d41-120">Visualizzazione nativa</span><span class="sxs-lookup"><span data-stu-id="d0d41-120">Native view</span></span>
- <span data-ttu-id="d0d41-121">Visualizzazione testo</span><span class="sxs-lookup"><span data-stu-id="d0d41-121">Text view</span></span>
- <span data-ttu-id="d0d41-122">Visualizzazione annotazioni</span><span class="sxs-lookup"><span data-stu-id="d0d41-122">Annotate view</span></span>

<span data-ttu-id="d0d41-123">Per accedere a uno di questi visualizzatori, è sufficiente selezionare un documento in un set di evidenze.</span><span class="sxs-lookup"><span data-stu-id="d0d41-123">To access any of these viewers, just select a document in an evidence set.</span></span>

## <a name="file-metadata"></a><span data-ttu-id="d0d41-124">Metadati dei file</span><span class="sxs-lookup"><span data-stu-id="d0d41-124">File metadata</span></span>

<span data-ttu-id="d0d41-125">In questa visualizzazione vengono visualizzate varie proprietà dei metadati associate al documento selezionato.</span><span class="sxs-lookup"><span data-stu-id="d0d41-125">This view displays various metadata properties associated with the selected document.</span></span> <span data-ttu-id="d0d41-126">È possibile attivare o disattivare questa visualizzazione facendo clic su **metadati file**.</span><span class="sxs-lookup"><span data-stu-id="d0d41-126">You can toggle this view on and off by clicking **File metadata**.</span></span> <span data-ttu-id="d0d41-127">Quando si esegue la revisione di un documento, è possibile visualizzare i metadati dei file e comunque cambiarli tra i diversi visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="d0d41-127">When reviewing a document, you can view the file metadata and still change between the different viewers.</span></span>

<span data-ttu-id="d0d41-128">Di seguito è riportato un esempio dei metadati di file per un documento.</span><span class="sxs-lookup"><span data-stu-id="d0d41-128">Here's an example of the file metadata for a document.</span></span> <span data-ttu-id="d0d41-129">Per ulteriori informazioni sui campi dei metadati, vedere [documento dei campi di metadati nelle indagini sui dati (Preview)](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="d0d41-129">For more information about the metadata fields, see [Document metadata fields in Data Investigations (Preview)](document-metadata-fields.md).</span></span>

![Pannello metadati file](media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="d0d41-131">Visualizzazione nativa</span><span class="sxs-lookup"><span data-stu-id="d0d41-131">Native view</span></span>

<span data-ttu-id="d0d41-132">Il Visualizzatore nativo Visualizza la visualizzazione più accurata di un documento nel formato nativo.</span><span class="sxs-lookup"><span data-stu-id="d0d41-132">The Native viewer displays the most accurate view of a document in it's native format.</span></span> <span data-ttu-id="d0d41-133">La visualizzazione nativa è supportata per centinaia di tipi di file ed è destinata a visualizzare i documenti in una delle più vere esperienze native possibili.</span><span class="sxs-lookup"><span data-stu-id="d0d41-133">Native view is supported for hundreds of file types and is meant to display documents in the truest native experience possible.</span></span> <span data-ttu-id="d0d41-134">Per i file di Microsoft Office, il Visualizzatore nativo utilizza la versione Web delle app di Office.</span><span class="sxs-lookup"><span data-stu-id="d0d41-134">For Microsoft Office files, the Native viewer uses the web version of Office apps.</span></span> <span data-ttu-id="d0d41-135">In questo modo è possibile visualizzare il contenuto, ad esempio i commenti in documenti di Office, formule e righe/colonne nascoste in Excel, e la visualizzazione note in PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d0d41-135">This allows you to view content such as comments in different Office documents, formulas and hidden rows/columns in Excel, and the Notes view in PowerPoint.</span></span>

![<span data-ttu-id="d0d41-136">Visualizzazione nativa</span><span class="sxs-lookup"><span data-stu-id="d0d41-136">Native view</span></span>
](media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="d0d41-137">Visualizzazione testo</span><span class="sxs-lookup"><span data-stu-id="d0d41-137">Text view</span></span>

<span data-ttu-id="d0d41-138">Il Visualizzatore di testo consente di visualizzare il testo estratto di un file.</span><span class="sxs-lookup"><span data-stu-id="d0d41-138">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="d0d41-139">Ignora tutte le immagini e la formattazione incorporate, ma questa visualizzazione è molto utile se si sta tentando di esaminare e comprendere rapidamente il contenuto di un documento.</span><span class="sxs-lookup"><span data-stu-id="d0d41-139">It ignores any embedded images and formatting, but this view is very useful if you're trying to quickly review and understand the content in a document.</span></span> <span data-ttu-id="d0d41-140">La visualizzazione del testo include anche queste caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="d0d41-140">Text view also includes these features:</span></span>

  - <span data-ttu-id="d0d41-141">Un contatore di linea, che rende più facile fare riferimento a parti specifiche di un documento.</span><span class="sxs-lookup"><span data-stu-id="d0d41-141">A line counter, which makes it easier to reference specific portions of a document.</span></span>

  - <span data-ttu-id="d0d41-142">Ricerca hit highlighting che evidenzia i termini del documento e della barra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="d0d41-142">Search hit highlighting that highlight terms in the document as well as on the scrollbar</span></span>

  - <span data-ttu-id="d0d41-143">Una visualizzazione diff fornisce una visualizzazione di confronto in cui vengono evidenziate le differenze di testo quando si visualizzano i documenti utilizzando il riquadro **quasi duplicati** .</span><span class="sxs-lookup"><span data-stu-id="d0d41-143">A diff view provides a comparison view that highlights the text differences when viewing documents using the **Near duplicates** panel.</span></span>

<span data-ttu-id="d0d41-144">**Esempio di contatore di riga e di evidenziazione dei risultati della ricerca in testo e barra di scorrimento**</span><span class="sxs-lookup"><span data-stu-id="d0d41-144">**Example of line counter and search hit highlighting in text and scrollbar**</span></span>

![<span data-ttu-id="d0d41-145">Visualizzazione testo</span><span class="sxs-lookup"><span data-stu-id="d0d41-145">Text view</span></span>
](media/Reviewimage4.png)

<span data-ttu-id="d0d41-146">**Esempio di visualizzazione diff**</span><span class="sxs-lookup"><span data-stu-id="d0d41-146">**Example of the diff view**</span></span>

![<span data-ttu-id="d0d41-147">Visualizzazione diff</span><span class="sxs-lookup"><span data-stu-id="d0d41-147">Diff view</span></span>
](media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="d0d41-148">Visualizzazione annotazioni</span><span class="sxs-lookup"><span data-stu-id="d0d41-148">Annotate view</span></span>

<span data-ttu-id="d0d41-149">La visualizzazione annotazioni fornisce caratteristiche che consentono di applicare il markup su un documento durante il processo di revisione. sono inclusi gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0d41-149">The Annotate view provides features that allow you to apply markup on a document during the review process; this  includes these tools:</span></span>

  - <span data-ttu-id="d0d41-150">**Redazioni area** : è possibile disegnare una casella opaca nel documento che nasconde contenuto sensibile.</span><span class="sxs-lookup"><span data-stu-id="d0d41-150">**Area redactions** – You can draw an opaque box on the document that hides sensitive content.</span></span>

  - <span data-ttu-id="d0d41-151">**Matita** – è possibile disegnare a mano libera su un documento per attirare l'attenzione su determinate parti del contenuto.</span><span class="sxs-lookup"><span data-stu-id="d0d41-151">**Pencil** – You can free-hand draw on a document to bring attention to certain portions of the content</span></span>

  - <span data-ttu-id="d0d41-152">**Seleziona annotazioni** : è possibile selezionare ed eliminare le annotazioni in un documento.</span><span class="sxs-lookup"><span data-stu-id="d0d41-152">**Select annotations** - You can select and delete annotations in a document.</span></span>

  - <span data-ttu-id="d0d41-153">**Toggle Transparency Annotation** – è possibile alternare la trasparenza delle annotazioni (tra opaco e semitrasparente) in modo da poter visualizzare il contenuto dietro l'annotazione.</span><span class="sxs-lookup"><span data-stu-id="d0d41-153">**Toggle annotation transparency** – You can toggle the transparency of annotations (between opaque and semi-transparent)so you can view the content behind the annotation.</span></span> <span data-ttu-id="d0d41-154">Questo include l'attivazione della trasparenza delle annotazioni e dei redazioni di matite.</span><span class="sxs-lookup"><span data-stu-id="d0d41-154">This includes toggling the transparency of pencil annotations and redactions.</span></span>

<span data-ttu-id="d0d41-155">La visualizzazione annotazioni fornisce anche la funzionalità di spostamento seguente:</span><span class="sxs-lookup"><span data-stu-id="d0d41-155">The Annotate view also provides the following navigation functionality:</span></span>

  - <span data-ttu-id="d0d41-156">**Pagina precedente**, **pagina successiva**e **passare ai** controlli di spostamento della pagina da utilizzare per i documenti a più pagine.</span><span class="sxs-lookup"><span data-stu-id="d0d41-156">**Previous page**, **Next page**, and **Go to page** - Navigation controls to use for multi-page documents.</span></span>

  - <span data-ttu-id="d0d41-157">**Zoom** : aumenta o diminuisce le dimensioni dei documenti nella visualizzazione annotazioni.</span><span class="sxs-lookup"><span data-stu-id="d0d41-157">**Zoom** – Increases or decreases the size of documents in Annotate view.</span></span>

  - <span data-ttu-id="d0d41-158">**Ruota** – ruota i documenti in senso orario.</span><span class="sxs-lookup"><span data-stu-id="d0d41-158">**Rotate** – Rotate documents clockwise.</span></span>

  - <span data-ttu-id="d0d41-159">**Ricerca** : cercare le parole chiave in un documento e quindi utilizzare i controlli precedenti e successivi per visualizzare i risultati evidenziati all'interno del documento.</span><span class="sxs-lookup"><span data-stu-id="d0d41-159">**Search** – Search for keywords in a document, and then use Previous and Next controls to view the hits (which are highlighted) within the document.</span></span>

<span data-ttu-id="d0d41-160">**Esempio di visualizzazione annotazioni**</span><span class="sxs-lookup"><span data-stu-id="d0d41-160">**Example of Annotate view**</span></span>

![Visualizzazione annotazioni](media/Reviewimage1.png)

> [!NOTE]
> <span data-ttu-id="d0d41-162">Le annotazioni vengono applicate a una copia del documento che è stato aggiunto al set di evidenze.</span><span class="sxs-lookup"><span data-stu-id="d0d41-162">Annotations are applied to a copy of the document that was added to the evidence set.</span></span> <span data-ttu-id="d0d41-163">I documenti originali del servizio Live non vengono annotati.</span><span class="sxs-lookup"><span data-stu-id="d0d41-163">The original documents in the live service aren't annotated.</span></span>
