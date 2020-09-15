---
title: Esaminare i dati nelle prove
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni sui metodi per esaminare i dati dell'evidenza, ad esempio la visualizzazione in formato nativo, testo o quasi nativo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9df5c1f0fd15cb320e8359d09ab39202700dbc4b
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816729"
---
# <a name="review-the-data-in-evidence"></a><span data-ttu-id="9313d-103">Esaminare i dati nelle prove</span><span class="sxs-lookup"><span data-stu-id="9313d-103">Review the data in evidence</span></span>

<span data-ttu-id="9313d-104">I dati di un set di evidenze in un'analisi dei dati sono uno snapshot dei risultati della ricerca raccolti e aggiunti al set di evidenze.</span><span class="sxs-lookup"><span data-stu-id="9313d-104">The data in an evidence set in a data investigation is a snapshot of the search results that you collected and added to the evidence set.</span></span> <span data-ttu-id="9313d-105">Quando si aggiungono i risultati della ricerca all'evidenza, viene attivato un processo per estrarre file, metadati e testo dagli elementi restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="9313d-105">When you add search results to evidence, a process is triggered to extract files, metadata, and text from the items returned by the search.</span></span> <span data-ttu-id="9313d-106">Successivamente, lo strumento indagini dati (Preview) crea un nuovo indice (tramite un processo denominato *Advanced indicizzazione*) di tutti i dati e aggiunge a un set di evidenze nella scheda **Evidence** .</span><span class="sxs-lookup"><span data-stu-id="9313d-106">Then the Data Investigations (Preview) tool then builds a new index (by a process called *Advanced indexing*) of all the data and adds to an evidence set on the **Evidence** tab.</span></span> 

<span data-ttu-id="9313d-107">Per le indagini sensibili al tempo, in questo modo è possibile contenere rapidamente l'ambiente eliminando i dati effettivamente versati o dannosi che si trovano nell'origine dati originale, mentre allo stesso tempo è possibile esaminare l'evidenza ricreata in un ambiente in quarantena, che in questo caso è la copia dei dati nel set di evidenze.</span><span class="sxs-lookup"><span data-stu-id="9313d-107">For time-sensitive investigations, this allows you to quickly contain the environment by deleting the actual spilled or malicious data located in the at original data source, while at the same time allowing you to investigate the re-created evidence in a quarantined environment, which in this case is the data copied to the evidence set).</span></span> <span data-ttu-id="9313d-108">Dopo la raccolta e l'aggiunta dell'evidenza al set di evidenze, è possibile esaminare i singoli documenti nel formato nativo, nel formato di testo o in un formato quasi nativo che è possibile utilizzare per annotare e redigere i documenti.</span><span class="sxs-lookup"><span data-stu-id="9313d-108">After the evidence is collected and added to the evidence set, you can review individual documents in their native format, text format, or a near-native format that you can use to annotate and redact documents.</span></span> <span data-ttu-id="9313d-109">È inoltre possibile eseguire query per limitare il set di dati in base a intervallo di tempo, tipi di file, proprietari di dati e molte altre proprietà e condizioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="9313d-109">Additionally, you can run queries to narrow the data set by time range, file types, data owners, and many other properties and search conditions.</span></span> <span data-ttu-id="9313d-110">Ad esempio, utilizzando le condizioni di autore, mittente o destinatario, è possibile identificare rapidamente le persone coinvolte nell'incidente e se i dati dell'organizzazione sono stati condivisi con utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="9313d-110">For example, by using the Author, Sender, or Recipient conditions, you can quickly identify the people are involved in the incident and if any data from your organization has been shared with external users.</span></span> <span data-ttu-id="9313d-111">Per ulteriori informazioni sulla ricerca di dati in un set di evidenze, vedere [query the data in evidence](evidence-query.md).</span><span class="sxs-lookup"><span data-stu-id="9313d-111">For more information about searching through data in an evidence set, see [Query the data in evidence](evidence-query.md).</span></span>

<span data-ttu-id="9313d-112">Per raggruppare i documenti e ottenere assistenza per la revisione, selezionare un set di evidenze nella scheda **Evidence** e quindi fare clic su **Gestisci prova**.</span><span class="sxs-lookup"><span data-stu-id="9313d-112">To group documents and get more assistance for your review, select an evidence set on the **Evidence** tab, and then click **Manage evidence**.</span></span> <span data-ttu-id="9313d-113">Nel riquadro **analisi** fare clic su **Ricostruisci analisi per l'intero set**.</span><span class="sxs-lookup"><span data-stu-id="9313d-113">In the **Analytics** tile, click **Rebuild analytics for the whole set**.</span></span> <span data-ttu-id="9313d-114">Verrà eseguito l'analisi avanzata, ad esempio il rilevamento duplicato, il threading di posta elettronica e l'analizzatore dei temi.</span><span class="sxs-lookup"><span data-stu-id="9313d-114">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="9313d-115">Successivamente, è possibile visualizzare i temi generali dei dati e anche organizzare i documenti tramite thread di posta elettronica, vicino a duplicati e duplicati esatti per facilitare l'indagine.</span><span class="sxs-lookup"><span data-stu-id="9313d-115">Afterwards, you can see the general themes of the data and also organize documents by email threads, near duplicates, and exact duplicates to help your investigation.</span></span> <span data-ttu-id="9313d-116">Per ulteriori informazioni, vedere [Run Analytics to investigate Faster](run-analytics-to-investigate-faster.md).</span><span class="sxs-lookup"><span data-stu-id="9313d-116">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span>

## <a name="view-documents-in-evidence"></a><span data-ttu-id="9313d-117">Visualizzare i documenti in evidenza</span><span class="sxs-lookup"><span data-stu-id="9313d-117">View documents in evidence</span></span>

<span data-ttu-id="9313d-118">Lo strumento di analisi dei dati (Preview) consente di visualizzare il contenuto in diversi visualizzatori, in cui ogni visualizzatore ha uno scopo diverso.</span><span class="sxs-lookup"><span data-stu-id="9313d-118">The Data Investigations (preview) tool allows you to display content in several different viewers, with each viewer having a different purpose.</span></span> <span data-ttu-id="9313d-119">Questi visualizzatori sono:</span><span class="sxs-lookup"><span data-stu-id="9313d-119">These viewers are:</span></span>

- <span data-ttu-id="9313d-120">Metadati dei file</span><span class="sxs-lookup"><span data-stu-id="9313d-120">File metadata</span></span>
- <span data-ttu-id="9313d-121">Visualizzazione nativa</span><span class="sxs-lookup"><span data-stu-id="9313d-121">Native view</span></span>
- <span data-ttu-id="9313d-122">Visualizzazione testo</span><span class="sxs-lookup"><span data-stu-id="9313d-122">Text view</span></span>
- <span data-ttu-id="9313d-123">Visualizzazione annotazioni</span><span class="sxs-lookup"><span data-stu-id="9313d-123">Annotate view</span></span>

<span data-ttu-id="9313d-124">Per accedere a uno di questi visualizzatori, è sufficiente selezionare un documento in un set di evidenze.</span><span class="sxs-lookup"><span data-stu-id="9313d-124">To access any of these viewers, just select a document in an evidence set.</span></span>

## <a name="file-metadata"></a><span data-ttu-id="9313d-125">Metadati dei file</span><span class="sxs-lookup"><span data-stu-id="9313d-125">File metadata</span></span>

<span data-ttu-id="9313d-126">In questa visualizzazione vengono visualizzate varie proprietà dei metadati associate al documento selezionato.</span><span class="sxs-lookup"><span data-stu-id="9313d-126">This view displays various metadata properties associated with the selected document.</span></span> <span data-ttu-id="9313d-127">È possibile attivare o disattivare questa visualizzazione facendo clic su **metadati file**.</span><span class="sxs-lookup"><span data-stu-id="9313d-127">You can toggle this view on and off by clicking **File metadata**.</span></span> <span data-ttu-id="9313d-128">Quando si esegue la revisione di un documento, è possibile visualizzare i metadati dei file e comunque cambiarli tra i diversi visualizzatori.</span><span class="sxs-lookup"><span data-stu-id="9313d-128">When reviewing a document, you can view the file metadata and still change between the different viewers.</span></span>

<span data-ttu-id="9313d-129">Di seguito è riportato un esempio dei metadati di file per un documento.</span><span class="sxs-lookup"><span data-stu-id="9313d-129">Here's an example of the file metadata for a document.</span></span> <span data-ttu-id="9313d-130">Per ulteriori informazioni sui campi dei metadati, vedere [documento dei campi di metadati nelle indagini sui dati (Preview)](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="9313d-130">For more information about the metadata fields, see [Document metadata fields in Data Investigations (Preview)](document-metadata-fields.md).</span></span>

![Pannello metadati file](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="9313d-132">Visualizzazione nativa</span><span class="sxs-lookup"><span data-stu-id="9313d-132">Native view</span></span>

<span data-ttu-id="9313d-133">Il Visualizzatore nativo Visualizza la visualizzazione più accurata di un documento nel formato nativo.</span><span class="sxs-lookup"><span data-stu-id="9313d-133">The Native viewer displays the most accurate view of a document in its native format.</span></span> <span data-ttu-id="9313d-134">La visualizzazione nativa è supportata per centinaia di tipi di file ed è destinata a visualizzare i documenti in una delle più vere esperienze native possibili.</span><span class="sxs-lookup"><span data-stu-id="9313d-134">Native view is supported for hundreds of file types and is meant to display documents in the truest native experience possible.</span></span> <span data-ttu-id="9313d-135">Per i file di Microsoft Office, il Visualizzatore nativo utilizza la versione Web delle app di Office.</span><span class="sxs-lookup"><span data-stu-id="9313d-135">For Microsoft Office files, the Native viewer uses the web version of Office apps.</span></span> <span data-ttu-id="9313d-136">In questo modo è possibile visualizzare il contenuto, ad esempio i commenti in documenti di Office, formule e righe/colonne nascoste in Excel, e la visualizzazione note in PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="9313d-136">This allows you to view content such as comments in different Office documents, formulas and hidden rows/columns in Excel, and the Notes view in PowerPoint.</span></span>

![<span data-ttu-id="9313d-137">Visualizzazione nativa</span><span class="sxs-lookup"><span data-stu-id="9313d-137">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="9313d-138">Visualizzazione testo</span><span class="sxs-lookup"><span data-stu-id="9313d-138">Text view</span></span>

<span data-ttu-id="9313d-139">Il Visualizzatore di testo consente di visualizzare il testo estratto di un file.</span><span class="sxs-lookup"><span data-stu-id="9313d-139">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="9313d-140">Ignora tutte le immagini e la formattazione incorporate, ma questa visualizzazione è utile se si sta tentando di esaminare e comprendere rapidamente il contenuto di un documento.</span><span class="sxs-lookup"><span data-stu-id="9313d-140">It ignores any embedded images and formatting, but this view is useful if you're trying to quickly review and understand the content in a document.</span></span> <span data-ttu-id="9313d-141">La visualizzazione del testo include anche queste caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="9313d-141">Text view also includes these features:</span></span>

  - <span data-ttu-id="9313d-142">Un contatore di linea, che rende più facile fare riferimento a parti specifiche di un documento.</span><span class="sxs-lookup"><span data-stu-id="9313d-142">A line counter, which makes it easier to reference specific portions of a document.</span></span>

  - <span data-ttu-id="9313d-143">Ricerca hit highlighting che evidenzia i termini del documento e della barra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="9313d-143">Search hit highlighting that highlight terms in the document as well as on the scrollbar</span></span>

  - <span data-ttu-id="9313d-144">Una visualizzazione diff fornisce una visualizzazione di confronto in cui vengono evidenziate le differenze di testo quando si visualizzano i documenti utilizzando il riquadro **quasi duplicati** .</span><span class="sxs-lookup"><span data-stu-id="9313d-144">A diff view provides a comparison view that highlights the text differences when viewing documents using the **Near duplicates** panel.</span></span>

<span data-ttu-id="9313d-145">**Esempio di contatore di riga e di evidenziazione dei risultati della ricerca in testo e barra di scorrimento**</span><span class="sxs-lookup"><span data-stu-id="9313d-145">**Example of line counter and search hit highlighting in text and scrollbar**</span></span>

![<span data-ttu-id="9313d-146">Visualizzazione testo</span><span class="sxs-lookup"><span data-stu-id="9313d-146">Text view</span></span>
](../media/Reviewimage4.png)

<span data-ttu-id="9313d-147">**Esempio di visualizzazione diff**</span><span class="sxs-lookup"><span data-stu-id="9313d-147">**Example of the diff view**</span></span>

![<span data-ttu-id="9313d-148">Visualizzazione diff</span><span class="sxs-lookup"><span data-stu-id="9313d-148">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="9313d-149">Visualizzazione annotazioni</span><span class="sxs-lookup"><span data-stu-id="9313d-149">Annotate view</span></span>

<span data-ttu-id="9313d-150">La visualizzazione annotazioni fornisce caratteristiche che consentono di applicare il markup su un documento durante il processo di revisione. sono inclusi gli strumenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9313d-150">The Annotate view provides features that allow you to apply markup on a document during the review process; this  includes these tools:</span></span>

  - <span data-ttu-id="9313d-151">**Redazioni area** : è possibile disegnare una casella opaca nel documento che nasconde contenuto sensibile.</span><span class="sxs-lookup"><span data-stu-id="9313d-151">**Area redactions** – You can draw an opaque box on the document that hides sensitive content.</span></span>

  - <span data-ttu-id="9313d-152">**Matita** – è possibile disegnare a mano libera su un documento per attirare l'attenzione su determinate parti del contenuto.</span><span class="sxs-lookup"><span data-stu-id="9313d-152">**Pencil** – You can free-hand draw on a document to bring attention to certain portions of the content</span></span>

  - <span data-ttu-id="9313d-153">**Seleziona annotazioni** : è possibile selezionare ed eliminare le annotazioni in un documento.</span><span class="sxs-lookup"><span data-stu-id="9313d-153">**Select annotations** - You can select and delete annotations in a document.</span></span>

  - <span data-ttu-id="9313d-154">**Toggle Transparency Annotation** – è possibile alternare la trasparenza delle annotazioni (tra opaco e semitrasparente) in modo da poter visualizzare il contenuto dietro l'annotazione.</span><span class="sxs-lookup"><span data-stu-id="9313d-154">**Toggle annotation transparency** – You can toggle the transparency of annotations (between opaque and semi-transparent) so you can view the content behind the annotation.</span></span> <span data-ttu-id="9313d-155">Questo include l'attivazione della trasparenza delle annotazioni e dei redazioni di matite.</span><span class="sxs-lookup"><span data-stu-id="9313d-155">This includes toggling the transparency of pencil annotations and redactions.</span></span>

<span data-ttu-id="9313d-156">La visualizzazione annotazioni fornisce anche la funzionalità di spostamento seguente:</span><span class="sxs-lookup"><span data-stu-id="9313d-156">The Annotate view also provides the following navigation functionality:</span></span>

  - <span data-ttu-id="9313d-157">**Pagina precedente**, **pagina successiva**e **passare ai** controlli di spostamento della pagina da utilizzare per i documenti a più pagine.</span><span class="sxs-lookup"><span data-stu-id="9313d-157">**Previous page**, **Next page**, and **Go to page** - Navigation controls to use for multi-page documents.</span></span>

  - <span data-ttu-id="9313d-158">**Zoom** : aumenta o diminuisce le dimensioni dei documenti nella visualizzazione annotazioni.</span><span class="sxs-lookup"><span data-stu-id="9313d-158">**Zoom** – Increases or decreases the size of documents in Annotate view.</span></span>

  - <span data-ttu-id="9313d-159">**Ruota** – ruota i documenti in senso orario.</span><span class="sxs-lookup"><span data-stu-id="9313d-159">**Rotate** – Rotate documents clockwise.</span></span>

  - <span data-ttu-id="9313d-160">**Ricerca** : cercare le parole chiave in un documento e quindi utilizzare i controlli precedenti e successivi per visualizzare i risultati evidenziati all'interno del documento.</span><span class="sxs-lookup"><span data-stu-id="9313d-160">**Search** – Search for keywords in a document, and then use Previous and Next controls to view the hits (which are highlighted) within the document.</span></span>

<span data-ttu-id="9313d-161">**Esempio di visualizzazione annotazioni**</span><span class="sxs-lookup"><span data-stu-id="9313d-161">**Example of Annotate view**</span></span>

![Visualizzazione annotazioni](../media/Reviewimage1.png)

> [!NOTE]
> <span data-ttu-id="9313d-163">Le annotazioni vengono applicate a una copia del documento che è stato aggiunto al set di evidenze.</span><span class="sxs-lookup"><span data-stu-id="9313d-163">Annotations are applied to a copy of the document that was added to the evidence set.</span></span> <span data-ttu-id="9313d-164">I documenti originali del servizio Live non vengono annotati.</span><span class="sxs-lookup"><span data-stu-id="9313d-164">The original documents in the live service aren't annotated.</span></span>
