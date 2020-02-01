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
description: ''
ms.openlocfilehash: 5ab54e84de7434a16bdf7eb7d04fad7b9af05440
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600633"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="d4f04-102">Indicizzazione avanzata dei dati dei responsabili</span><span class="sxs-lookup"><span data-stu-id="d4f04-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="d4f04-103">Quando un custode viene aggiunto a un caso di eDiscovery avanzato, tutti i contenuti di Office 365 ritenuti parzialmente indicizzati vengono rielaborati in modo da renderli completamente ricercabili.</span><span class="sxs-lookup"><span data-stu-id="d4f04-103">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="d4f04-104">Questo processo è denominato *Advanced indicizzazione*.</span><span class="sxs-lookup"><span data-stu-id="d4f04-104">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="d4f04-105">Il contenuto può essere parzialmente indicizzato per una serie di motivi, tra cui l'esistenza di immagini, i tipi di file non supportati o l'indicizzazione dei limiti delle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="d4f04-105">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="d4f04-106">Per ulteriori informazioni sull'elaborazione del supporto in Office 365 e sugli elementi parzialmente indicizzati, vedere:</span><span class="sxs-lookup"><span data-stu-id="d4f04-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="d4f04-107">Tipi di file supportati in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d4f04-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- <span data-ttu-id="d4f04-108">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)</span><span class="sxs-lookup"><span data-stu-id="d4f04-108">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>
- [<span data-ttu-id="d4f04-109">Formati di file indicizzati dalla ricerca di Exchange</span><span class="sxs-lookup"><span data-stu-id="d4f04-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="d4f04-110">Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="d4f04-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="d4f04-111">Visualizzazione dei risultati di indicizzazione avanzati</span><span class="sxs-lookup"><span data-stu-id="d4f04-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="d4f04-112">Una volta completato il processo di indicizzazione avanzato, è possibile ottenere informazioni sull'efficacia del rielaborazione.</span><span class="sxs-lookup"><span data-stu-id="d4f04-112">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="d4f04-113">Nella visualizzazione di indicizzazione del custode, nel grafico vengono elencati tutti gli elementi aggiunti all' *Indice ibrido*.</span><span class="sxs-lookup"><span data-stu-id="d4f04-113">In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="d4f04-114">L'indice ibrido è la posizione in cui Advanced eDiscovery archivia il contenuto rielaborato.</span><span class="sxs-lookup"><span data-stu-id="d4f04-114">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="d4f04-115">Il grafico include anche il numero di elementi che richiedono la correzione e un altro grafico degli errori per tipo di file.</span><span class="sxs-lookup"><span data-stu-id="d4f04-115">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="d4f04-116">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="d4f04-116">For more information, see:</span></span>

- [<span data-ttu-id="d4f04-117">Correzione degli errori durante l'elaborazione dei dati</span><span class="sxs-lookup"><span data-stu-id="d4f04-117">Error remediation when processing data</span></span>](error-remediation.md)
- [<span data-ttu-id="d4f04-118">Correzione degli errori dei singoli elementi</span><span class="sxs-lookup"><span data-stu-id="d4f04-118">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="d4f04-119">Aggiornamento degli indici avanzati per i depositari</span><span class="sxs-lookup"><span data-stu-id="d4f04-119">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="d4f04-120">Quando un custode viene aggiunto a un caso di eDiscovery avanzato, tutti gli elementi parzialmente indicizzati vengono rielaborati.</span><span class="sxs-lookup"><span data-stu-id="d4f04-120">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="d4f04-121">Tuttavia, con il passare del tempo, è possibile aggiungere elementi indicizzati in modo più parziale alla cassetta postale o all'account di OneDrive di un utente.</span><span class="sxs-lookup"><span data-stu-id="d4f04-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="d4f04-122">Se necessario, è possibile aggiornare gli indici.</span><span class="sxs-lookup"><span data-stu-id="d4f04-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="d4f04-123">L'aggiornamento degli indici del custode è un processo di esecuzione prolungato.</span><span class="sxs-lookup"><span data-stu-id="d4f04-123">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="d4f04-124">Si consiglia di non aggiornare gli indici più di una volta al giorno in un caso.</span><span class="sxs-lookup"><span data-stu-id="d4f04-124">It's recommended that you don't update indexes more than once per day in a case.</span></span>
