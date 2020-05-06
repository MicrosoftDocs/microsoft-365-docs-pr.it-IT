---
title: Indicizzazione avanzata dei dati per un'indagine
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
description: Informazioni su come utilizzare l'indicizzazione avanzata per assicurarsi che la ricerca acquisisca tutti i dati che si desidera esaminare.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dc7d73c233aa48b88e9dce32fad613ccc5e19333
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035062"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="06c0f-103">Indicizzazione avanzata dei dati per un'indagine</span><span class="sxs-lookup"><span data-stu-id="06c0f-103">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="06c0f-104">Il contenuto del sistema attivo può essere parzialmente indicizzato per una serie di motivi, tra cui l'esistenza di immagini, tipi di file non supportati o durante l'indicizzazione dei limiti delle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="06c0f-104">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="06c0f-105">Quando si ha a che fare con la fuoriuscita di dati ad alto rischio, è necessario assicurarsi che la ricerca abbia acquisito tutti i dati che si desidera esaminare.</span><span class="sxs-lookup"><span data-stu-id="06c0f-105">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="06c0f-106">Quando una persona di interesse viene aggiunta a un'analisi dei dati, il contenuto ritenuto come parzialmente indicizzato viene rielaborato per renderlo completamente ricercabile.</span><span class="sxs-lookup"><span data-stu-id="06c0f-106">When a person of interest is added to a Data investigation, any content that was deemed as partially indexed is re-processed to make it fully searchable.</span></span> <span data-ttu-id="06c0f-107">Questo processo è denominato *Advanced indicizzazione*.</span><span class="sxs-lookup"><span data-stu-id="06c0f-107">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="06c0f-108">Per ulteriori informazioni sul supporto di elaborazione e sugli elementi parzialmente indicizzati, vedere:</span><span class="sxs-lookup"><span data-stu-id="06c0f-108">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="06c0f-109">Tipi di file supportati nelle indagini sui dati</span><span class="sxs-lookup"><span data-stu-id="06c0f-109">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- <span data-ttu-id="06c0f-110">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)</span><span class="sxs-lookup"><span data-stu-id="06c0f-110">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>

- [<span data-ttu-id="06c0f-111">Formati di file indicizzati dalla ricerca di Exchange</span><span class="sxs-lookup"><span data-stu-id="06c0f-111">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="06c0f-112">Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="06c0f-112">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="06c0f-113">Visualizzazione dei risultati di indicizzazione avanzati</span><span class="sxs-lookup"><span data-stu-id="06c0f-113">Viewing Advanced indexing results</span></span>

<span data-ttu-id="06c0f-114">Una volta completato il processo di indicizzazione avanzato, è possibile ottenere informazioni sull'efficacia del rielaborazione.</span><span class="sxs-lookup"><span data-stu-id="06c0f-114">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="06c0f-115">Nella visualizzazione indicizzazione persone di interesse, nel grafico vengono elencati tutti gli elementi aggiunti all' *Indice ibrido*.</span><span class="sxs-lookup"><span data-stu-id="06c0f-115">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="06c0f-116">L'indice ibrido è la posizione in cui l'analisi dei dati (Preview) archivia il contenuto rielaborato.</span><span class="sxs-lookup"><span data-stu-id="06c0f-116">The hybrid index is where Data Investigations (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="06c0f-117">Il grafico include anche il numero di elementi che richiedono la correzione e un altro grafico degli errori per tipo di file.</span><span class="sxs-lookup"><span data-stu-id="06c0f-117">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="06c0f-118">Per ulteriori informazioni, vedere [correzione degli errori durante l'elaborazione dei dati](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="06c0f-118">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="06c0f-119">Aggiornamento degli indici avanzati per gli utenti interessati</span><span class="sxs-lookup"><span data-stu-id="06c0f-119">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="06c0f-120">Quando una persona di interesse viene aggiunta a un'analisi dei dati, tutti gli elementi parzialmente indicizzati vengono rielaborati.</span><span class="sxs-lookup"><span data-stu-id="06c0f-120">When a person of interest is added to a data investigation, all partially indexed items are re-processed.</span></span> <span data-ttu-id="06c0f-121">Tuttavia, con il passare del tempo, è possibile aggiungere elementi indicizzati in modo più parziale alla cassetta postale o all'account di OneDrive di un utente.</span><span class="sxs-lookup"><span data-stu-id="06c0f-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="06c0f-122">Se necessario, è possibile aggiornare gli indici.</span><span class="sxs-lookup"><span data-stu-id="06c0f-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="06c0f-123">L'aggiornamento degli indici degli utenti è un processo a esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="06c0f-123">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="06c0f-124">Si consiglia di non aggiornare gli indici più di una volta al giorno in un'indagine.</span><span class="sxs-lookup"><span data-stu-id="06c0f-124">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
