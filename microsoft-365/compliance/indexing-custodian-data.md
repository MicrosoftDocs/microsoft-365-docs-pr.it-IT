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
description: Quando un responsabile viene aggiunto a un caso Advanced eDiscovery, qualsiasi contenuto considerato parzialmente indicizzato viene rielaborato per renderlo completamente ricercabile.
ms.openlocfilehash: 34855eb168dd10fc500e2e57fe1d57ad81449452
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437977"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="1f515-103">Indicizzazione avanzata dei dati dei responsabili</span><span class="sxs-lookup"><span data-stu-id="1f515-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="1f515-104">Quando un responsabile viene aggiunto a un caso Advanced eDiscovery, tutti i contenuti che sono stati considerati parzialmente indicizzati o con cui si sono verificati errori di indicizzazione vengono reindicizzati per renderlo completamente ricercabile.</span><span class="sxs-lookup"><span data-stu-id="1f515-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed or had indexing errors with is reindexed to make it fully searchable.</span></span>  <span data-ttu-id="1f515-105">Questo processo di reindicizzazione è denominato *indicizzazione avanzata.*</span><span class="sxs-lookup"><span data-stu-id="1f515-105">This reindexing process is called *Advanced indexing*.</span></span> <span data-ttu-id="1f515-106">Esistono diversi motivi per cui il contenuto è parzialmente indicizzato o presenta errori di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f515-106">There are a number of reasons that content is partially indexed or has indexing errors.</span></span> <span data-ttu-id="1f515-107">Sono inclusi i file di immagine o la presenza di immagini in un file, tipi di file non supportati o limiti di indicizzazione delle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="1f515-107">This includes image files or the presence of images in a file, unsupported file types, or file sized indexing limits.</span></span> <span data-ttu-id="1f515-108">Per SharePoint file, l'indicizzazione avanzata viene eseguita solo sugli elementi contrassegnati come parzialmente indicizzati o con errori di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f515-108">For SharePoint files, Advanced indexing only runs on items are marked as partially indexed or that have indexing errors.</span></span> <span data-ttu-id="1f515-109">In Exchange, i messaggi di posta elettronica con allegati di immagine non vengono contrassegnati come parzialmente indicizzati o con errori di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f515-109">In Exchange, email messages that have image attachments are not marked as partially indexed or with indexing errors.</span></span> <span data-ttu-id="1f515-110">Ciò significa che tali file non verranno reindicizzati dal processo di indicizzazione avanzata.</span><span class="sxs-lookup"><span data-stu-id="1f515-110">This means that those files will not be reindexed by the Advanced indexing process.</span></span>

<span data-ttu-id="1f515-111">Per ulteriori informazioni sul supporto dell'elaborazione e sugli elementi parzialmente indicizzati, vedere:</span><span class="sxs-lookup"><span data-stu-id="1f515-111">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="1f515-112">Tipi di file supportati in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1f515-112">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- <span data-ttu-id="1f515-113">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)</span><span class="sxs-lookup"><span data-stu-id="1f515-113">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>

- [<span data-ttu-id="1f515-114">Formati di file indicizzati dalla ricerca di Exchange</span><span class="sxs-lookup"><span data-stu-id="1f515-114">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="1f515-115">Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="1f515-115">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="1f515-116">Visualizzazione dei risultati di indicizzazione avanzati</span><span class="sxs-lookup"><span data-stu-id="1f515-116">Viewing Advanced indexing results</span></span>

<span data-ttu-id="1f515-117">Al termine del processo di indicizzazione avanzata, è possibile comprendere l'efficacia della rielaborazione.</span><span class="sxs-lookup"><span data-stu-id="1f515-117">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="1f515-118">Nella visualizzazione Risultati di indicizzazione avanzata della scheda **Elaborazione** di un caso, nel grafico viene elencato il numero di elementi aggiunti all'indice *ibrido.*</span><span class="sxs-lookup"><span data-stu-id="1f515-118">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="1f515-119">L'indice ibrido è il Advanced eDiscovery il contenuto rielaborato.</span><span class="sxs-lookup"><span data-stu-id="1f515-119">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="1f515-120">Questa visualizzazione include anche il numero di elementi che richiedono la correzione e un altro grafico di errori per tipo di file.</span><span class="sxs-lookup"><span data-stu-id="1f515-120">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="1f515-121">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="1f515-121">For more information, see:</span></span>

- [<span data-ttu-id="1f515-122">Correzione degli errori durante l'elaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="1f515-122">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="1f515-123">Correzione degli errori dei singoli elementi</span><span class="sxs-lookup"><span data-stu-id="1f515-123">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="1f515-124">Aggiornamento dell'indice avanzato per i custodi</span><span class="sxs-lookup"><span data-stu-id="1f515-124">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="1f515-125">Quando un responsabile viene aggiunto a un caso Advanced eDiscovery, tutti gli elementi parzialmente indicizzati vengono rielaborati.</span><span class="sxs-lookup"><span data-stu-id="1f515-125">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="1f515-126">Tuttavia, con il passare del tempo, è possibile aggiungere elementi indicizzati più parzialmente alla cassetta postale o all'account OneDrive utente.</span><span class="sxs-lookup"><span data-stu-id="1f515-126">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="1f515-127">Se necessario, è possibile aggiornare l'indice per un responsabile specifico.</span><span class="sxs-lookup"><span data-stu-id="1f515-127">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="1f515-128">Per ulteriori informazioni, vedere [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span><span class="sxs-lookup"><span data-stu-id="1f515-128">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="1f515-129">È inoltre possibile aggiornare l'indice per tutti i custodi in un caso facendo clic su **Aggiorna indice** nella **scheda** Elaborazione.</span><span class="sxs-lookup"><span data-stu-id="1f515-129">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="1f515-130">L'aggiornamento degli indici di custodia è un processo a esecuzione lunga.</span><span class="sxs-lookup"><span data-stu-id="1f515-130">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="1f515-131">È consigliabile non aggiornare gli indici più di una volta al giorno in un caso.</span><span class="sxs-lookup"><span data-stu-id="1f515-131">It's recommended that you don't update indexes more than once a day in a case.</span></span>
