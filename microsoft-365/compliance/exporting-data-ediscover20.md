---
title: Esportare i dati del caso in Advanced eDiscovery
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
description: Informazioni su come esportare o scaricare contenuto da un set di revisione per presentazioni o recensioni esterne in un caso di eDiscovery avanzato.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 114264f342a51f3ce68696f321cf7c6e929dc6d1
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726471"
---
# <a name="export-case-data-in-advanced-ediscovery"></a><span data-ttu-id="8a0ad-103">Esportare i dati del caso in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8a0ad-103">Export case data in Advanced eDiscovery</span></span>

<span data-ttu-id="8a0ad-104">Esistono tre modi per esportare i dati da un set di Revisione:</span><span class="sxs-lookup"><span data-stu-id="8a0ad-104">There are three ways to export data from a review set:</span></span>

<span data-ttu-id="8a0ad-105">**Download:** Scaricare (utilizzando un browser) un piccolo insieme di file nativi.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-105">**Download:** Download (by using a browser) a small set of native files.</span></span> <span data-ttu-id="8a0ad-106">Questo è il modo più rapido per esportare un set di dati di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-106">This is the quickest way to export a small set of data.</span></span> <span data-ttu-id="8a0ad-107">Questo metodo conserva i nomi di file nativi.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-107">This method preserves the native file names.</span></span>

<span data-ttu-id="8a0ad-108">**Esporta:** Personalizzare i dati esportati.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-108">**Export:** Customize what data is exported.</span></span> <span data-ttu-id="8a0ad-109">Questo include l'esportazione di metadati di file, file nativi, file di testo e documenti redatti che sono stati salvati in un file PDF.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-109">This includes exporting file metadata, native files, text files, and redacted documents that have been saved to a PDF file.</span></span> <span data-ttu-id="8a0ad-110">Dopo aver caricato i dati esportati in un percorso di archiviazione di Azure, è possibile scaricarlo in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-110">After the exported data is uploaded to an Azure Storage location, you can download it to a local computer.</span></span> <span data-ttu-id="8a0ad-111">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="8a0ad-111">For more information, see:</span></span>

- [<span data-ttu-id="8a0ad-112">Esportare i documenti da un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="8a0ad-112">Export documents from a review set</span></span>](export-documents-from-review-set.md)

- [<span data-ttu-id="8a0ad-113">Scaricare i processi di esportazione</span><span class="sxs-lookup"><span data-stu-id="8a0ad-113">Download export jobs</span></span>](download-export-jobs.md)

<span data-ttu-id="8a0ad-114">**Aggiungere a un altro set di Revisione:** Copiare i dati da un set di revisione a un diverso set di revisione.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-114">**Add to another review set:** Copy data from one review set to a different review set.</span></span> <span data-ttu-id="8a0ad-115">Per ulteriori informazioni, vedere [aggiungere dati da un set di revisione a un altro set di revisione](add-data-to-review-set-from-another-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="8a0ad-115">For more information, see [Add data from one review set to another review set](add-data-to-review-set-from-another-review-set.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8a0ad-116">In Microsoft 365, i dati vengono sottoposto a hash e tali hash sono forniti nel file di output a scopo di verifica.</span><span class="sxs-lookup"><span data-stu-id="8a0ad-116">In Microsoft 365, data is hashed and those hashes are provided in the output file for verification purposes.</span></span> <span data-ttu-id="8a0ad-117">Questa operazione viene completata dai registri di controllo e dalla funzionalità di creazione di report, ad esempio le statistiche sugli insiemi, i report set di carico e i report di esportazione (incluso il file di caricamento di esportazione).</span><span class="sxs-lookup"><span data-stu-id="8a0ad-117">This is supplemented by audit logs and reporting functionality, such as collection statistics, load set reports, and export reports (including the export load file).</span></span>
