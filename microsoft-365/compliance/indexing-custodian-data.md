---
title: Indicizzazione avanzata dei dati dei responsabili
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
description: Quando un custode viene aggiunto a un caso di eDiscovery avanzato, tutti i contenuti di Office 365 ritenuti parzialmente indicizzati vengono rielaborati in modo da renderli completamente ricercabili.
ms.openlocfilehash: 3c1bead5f853a39410a6a018f170ee637dfcf84e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072893"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="c34c2-103">Indicizzazione avanzata dei dati dei responsabili</span><span class="sxs-lookup"><span data-stu-id="c34c2-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="c34c2-104">Quando un custode viene aggiunto a un caso di eDiscovery avanzato, tutti i contenuti di Office 365 ritenuti parzialmente indicizzati vengono rielaborati in modo da renderli completamente ricercabili.</span><span class="sxs-lookup"><span data-stu-id="c34c2-104">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="c34c2-105">Questo processo è denominato *Advanced indicizzazione*.</span><span class="sxs-lookup"><span data-stu-id="c34c2-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="c34c2-106">Il contenuto può essere parzialmente indicizzato per una serie di motivi, tra cui l'esistenza di immagini, i tipi di file non supportati o l'indicizzazione dei limiti delle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="c34c2-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="c34c2-107">Per ulteriori informazioni sull'elaborazione del supporto in Office 365 e sugli elementi parzialmente indicizzati, vedere:</span><span class="sxs-lookup"><span data-stu-id="c34c2-107">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="c34c2-108">Tipi di file supportati in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c34c2-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- <span data-ttu-id="c34c2-109">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)</span><span class="sxs-lookup"><span data-stu-id="c34c2-109">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>

- [<span data-ttu-id="c34c2-110">Formati di file indicizzati dalla ricerca di Exchange</span><span class="sxs-lookup"><span data-stu-id="c34c2-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="c34c2-111">Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="c34c2-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="c34c2-112">Visualizzazione dei risultati di indicizzazione avanzati</span><span class="sxs-lookup"><span data-stu-id="c34c2-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="c34c2-113">Una volta completato il processo di indicizzazione avanzato, è possibile ottenere informazioni sull'efficacia del rielaborazione.</span><span class="sxs-lookup"><span data-stu-id="c34c2-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="c34c2-114">Nella visualizzazione dei risultati di indicizzazione avanzata nella scheda **elaborazione** di un caso, il grafico elenca il numero di elementi aggiunti all' *Indice ibrido*.</span><span class="sxs-lookup"><span data-stu-id="c34c2-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="c34c2-115">L'indice ibrido è la posizione in cui Advanced eDiscovery archivia il contenuto rielaborato.</span><span class="sxs-lookup"><span data-stu-id="c34c2-115">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="c34c2-116">Questa visualizzazione include anche il numero di elementi che richiedono la correzione e un altro grafico degli errori in base al tipo di file.</span><span class="sxs-lookup"><span data-stu-id="c34c2-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="c34c2-117">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="c34c2-117">For more information, see:</span></span>

- [<span data-ttu-id="c34c2-118">Correzione degli errori durante l'elaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="c34c2-118">Error remediation when processing data</span></span>](error-remediation.md)

- [<span data-ttu-id="c34c2-119">Correzione degli errori dei singoli elementi</span><span class="sxs-lookup"><span data-stu-id="c34c2-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="c34c2-120">Aggiornamento dell'indice avanzato per i depositari</span><span class="sxs-lookup"><span data-stu-id="c34c2-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="c34c2-121">Quando un custode viene aggiunto a un caso di eDiscovery avanzato, tutti gli elementi parzialmente indicizzati vengono rielaborati.</span><span class="sxs-lookup"><span data-stu-id="c34c2-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="c34c2-122">Tuttavia, con il passare del tempo, è possibile aggiungere elementi indicizzati in modo più parziale alla cassetta postale o all'account di OneDrive di un utente.</span><span class="sxs-lookup"><span data-stu-id="c34c2-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="c34c2-123">Se necessario, è possibile aggiornare l'indice per una banca depositaria specifica.</span><span class="sxs-lookup"><span data-stu-id="c34c2-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="c34c2-124">Per ulteriori informazioni, vedere [gestire i depositari in un caso avanzato di eDiscovery](manage-new-custodians.md#re-index-custodian-data).</span><span class="sxs-lookup"><span data-stu-id="c34c2-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="c34c2-125">È inoltre possibile aggiornare l'indice per tutti i depositari in un caso facendo clic sull' **indice di aggiornamento** nella scheda **elaborazione** .</span><span class="sxs-lookup"><span data-stu-id="c34c2-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="c34c2-126">L'aggiornamento degli indici del custode è un processo di esecuzione prolungato.</span><span class="sxs-lookup"><span data-stu-id="c34c2-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="c34c2-127">Si consiglia di non aggiornare gli indici più di una volta al giorno in un caso.</span><span class="sxs-lookup"><span data-stu-id="c34c2-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>
