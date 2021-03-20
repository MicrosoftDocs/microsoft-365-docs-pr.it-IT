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
description: Quando un responsabile viene aggiunto a un caso di Advanced eDiscovery, qualsiasi contenuto considerato parzialmente indicizzato viene rielaborato per renderlo completamente ricercabile.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911210"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="11775-103">Indicizzazione avanzata dei dati dei responsabili</span><span class="sxs-lookup"><span data-stu-id="11775-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="11775-104">Quando un responsabile viene aggiunto a un caso di Advanced eDiscovery, qualsiasi contenuto considerato parzialmente indicizzato viene rielaborato per renderlo completamente ricercabile.</span><span class="sxs-lookup"><span data-stu-id="11775-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="11775-105">Questo processo è denominato *indicizzazione avanzata.*</span><span class="sxs-lookup"><span data-stu-id="11775-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="11775-106">Il contenuto può essere parzialmente indicizzato per diversi motivi, tra cui l'esistenza di immagini, tipi di file non supportati o quando vengono rilevati limiti di dimensione dei file di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="11775-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="11775-107">Per ulteriori informazioni sul supporto dell'elaborazione e sugli elementi parzialmente indicizzati, vedere:</span><span class="sxs-lookup"><span data-stu-id="11775-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="11775-108">Tipi di file supportati in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="11775-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- <span data-ttu-id="11775-109">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)</span><span class="sxs-lookup"><span data-stu-id="11775-109">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>

- [<span data-ttu-id="11775-110">Formati di file indicizzati dalla ricerca di Exchange</span><span class="sxs-lookup"><span data-stu-id="11775-110">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="11775-111">Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="11775-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="11775-112">Visualizzazione dei risultati di indicizzazione avanzati</span><span class="sxs-lookup"><span data-stu-id="11775-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="11775-113">Al termine del processo di indicizzazione avanzata, è possibile comprendere l'efficacia della rielaborazione.</span><span class="sxs-lookup"><span data-stu-id="11775-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="11775-114">Nella visualizzazione Risultati di indicizzazione avanzata della scheda **Elaborazione** di un caso, nel grafico viene elencato il numero di elementi aggiunti all'indice *ibrido.*</span><span class="sxs-lookup"><span data-stu-id="11775-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="11775-115">L'indice ibrido è dove Advanced eDiscovery archivia il contenuto rielaborato.</span><span class="sxs-lookup"><span data-stu-id="11775-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="11775-116">Questa visualizzazione include anche il numero di elementi che richiedono la correzione e un altro grafico di errori per tipo di file.</span><span class="sxs-lookup"><span data-stu-id="11775-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="11775-117">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="11775-117">For more information, see:</span></span>

- [<span data-ttu-id="11775-118">Correzione degli errori durante l'elaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="11775-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="11775-119">Correzione degli errori dei singoli elementi</span><span class="sxs-lookup"><span data-stu-id="11775-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="11775-120">Aggiornamento dell'indice avanzato per i custodi</span><span class="sxs-lookup"><span data-stu-id="11775-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="11775-121">Quando un responsabile viene aggiunto a un caso advanced eDiscovery, tutti gli elementi parzialmente indicizzati vengono rielaborati.</span><span class="sxs-lookup"><span data-stu-id="11775-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="11775-122">Tuttavia, con il passare del tempo, è possibile aggiungere elementi indicizzati più parzialmente alla cassetta postale di un utente o all'account di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="11775-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="11775-123">Se necessario, è possibile aggiornare l'indice per un responsabile specifico.</span><span class="sxs-lookup"><span data-stu-id="11775-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="11775-124">Per ulteriori informazioni, vedere [Manage custodians in an Advanced eDiscovery case.](manage-new-custodians.md#re-index-custodian-data)</span><span class="sxs-lookup"><span data-stu-id="11775-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="11775-125">È inoltre possibile aggiornare l'indice per tutti i custodi in un caso facendo clic su **Aggiorna indice** nella **scheda** Elaborazione.</span><span class="sxs-lookup"><span data-stu-id="11775-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="11775-126">L'aggiornamento degli indici di custodia è un processo a esecuzione lunga.</span><span class="sxs-lookup"><span data-stu-id="11775-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="11775-127">È consigliabile non aggiornare gli indici più di una volta al giorno in un caso.</span><span class="sxs-lookup"><span data-stu-id="11775-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>