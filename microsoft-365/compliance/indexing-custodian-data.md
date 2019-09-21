---
title: Indicizzazione avanzata dei dati dei responsabili
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
ms.openlocfilehash: ba85ef90570dfbf2228148bf5211a4b041a1cb61
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082856"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="63775-102">Indicizzazione avanzata dei dati dei responsabili</span><span class="sxs-lookup"><span data-stu-id="63775-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="63775-103">Quando un custode viene aggiunto a un caso di eDiscovery avanzato, tutti i contenuti di Office 365 ritenuti parzialmente indicizzati vengono rielaborati in modo da renderli completamente ricercabili.</span><span class="sxs-lookup"><span data-stu-id="63775-103">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="63775-104">Questo processo è denominato *Advanced indicizzazione*.</span><span class="sxs-lookup"><span data-stu-id="63775-104">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="63775-105">Il contenuto può essere parzialmente indicizzato per una serie di motivi, tra cui l'esistenza di immagini, i tipi di file non supportati o l'indicizzazione dei limiti delle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="63775-105">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="63775-106">Per ulteriori informazioni sull'elaborazione del supporto in Office 365 e sugli elementi parzialmente indicizzati, vedere:</span><span class="sxs-lookup"><span data-stu-id="63775-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="63775-107">Tipi di file supportati in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="63775-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- <span data-ttu-id="63775-108">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md) (Elementi parzialmente indicizzati in Ricerca contenuto in Office 365)</span><span class="sxs-lookup"><span data-stu-id="63775-108">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>
- [<span data-ttu-id="63775-109">Formati di file indicizzati dalla ricerca di Exchange</span><span class="sxs-lookup"><span data-stu-id="63775-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="63775-110">Estensioni dei nomi di file sottoposti a ricerca per indicizzazione e tipi di file analizzati predefiniti in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="63775-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="63775-111">Visualizzazione dei risultati di indicizzazione avanzati</span><span class="sxs-lookup"><span data-stu-id="63775-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="63775-112">Una volta completato il processo di indicizzazione avanzato, è possibile ottenere informazioni sull'efficacia del rielaborazione.</span><span class="sxs-lookup"><span data-stu-id="63775-112">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="63775-113">Nella visualizzazione di indicizzazione del custode, nel grafico vengono elencati tutti gli elementi aggiunti all' *Indice ibrido*.</span><span class="sxs-lookup"><span data-stu-id="63775-113">In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="63775-114">L'indice ibrido è la posizione in cui Advanced eDiscovery archivia il contenuto rielaborato.</span><span class="sxs-lookup"><span data-stu-id="63775-114">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="63775-115">Il grafico include anche il numero di elementi che richiedono la correzione e un altro grafico degli errori per tipo di file.</span><span class="sxs-lookup"><span data-stu-id="63775-115">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="63775-116">Per ulteriori informazioni, vedere [correzione degli errori durante l'elaborazione dei dati](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="63775-116">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="63775-117">Aggiornamento degli indici avanzati per i depositari</span><span class="sxs-lookup"><span data-stu-id="63775-117">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="63775-118">Quando un custode viene aggiunto a un caso di eDiscovery avanzato, tutti gli elementi parzialmente indicizzati vengono rielaborati.</span><span class="sxs-lookup"><span data-stu-id="63775-118">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="63775-119">Tuttavia, con il passare del tempo, è possibile aggiungere elementi indicizzati in modo più parziale alla cassetta postale o all'account di OneDrive di un utente.</span><span class="sxs-lookup"><span data-stu-id="63775-119">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="63775-120">Se necessario, è possibile aggiornare gli indici.</span><span class="sxs-lookup"><span data-stu-id="63775-120">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="63775-121">L'aggiornamento degli indici del custode è un processo di esecuzione prolungato.</span><span class="sxs-lookup"><span data-stu-id="63775-121">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="63775-122">Si consiglia di non aggiornare gli indici più di una volta al giorno in un caso.</span><span class="sxs-lookup"><span data-stu-id="63775-122">It's recommended that you don't update indexes more than once per day in a case.</span></span>
