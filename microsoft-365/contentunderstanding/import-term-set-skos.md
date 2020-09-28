---
title: Importare un set di termini utilizzando un formato basato su SKOS
description: Informazioni su come importare un set di termini utilizzando un formato basato su SKOS
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296079"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="03406-103">Importare un set di termini utilizzando un formato basato su SKOS</span><span class="sxs-lookup"><span data-stu-id="03406-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="03406-104">È possibile importare un set di termini utilizzando un formato basato su SKOS.</span><span class="sxs-lookup"><span data-stu-id="03406-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="03406-105">Per informazioni dettagliate sul formato, vedere [SharePoint tassonomia SKOS format reference](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="03406-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="03406-106">È consigliabile mantenere i file di importazione su un valore inferiore a 20.000 termini.</span><span class="sxs-lookup"><span data-stu-id="03406-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="03406-107">I file di grandi dimensioni possono aumentare il tempo necessario per la convalida e l'importazione.</span><span class="sxs-lookup"><span data-stu-id="03406-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="03406-108">Nell'interfaccia di amministrazione di SharePoint espandere **servizi di contenuto**e quindi fare clic su **archivio termini**.</span><span class="sxs-lookup"><span data-stu-id="03406-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="03406-109">Selezionare il gruppo di termini in cui si desidera importare il set di termini.</span><span class="sxs-lookup"><span data-stu-id="03406-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="03406-110">Nella barra dei comandi, fare clic su **Importa set di termini**.</span><span class="sxs-lookup"><span data-stu-id="03406-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="03406-111">Se si desidera scaricare un file di esempio da utilizzare come modello, fare clic su **Sample-Metadata. TTL** per ottenere un file di esempio che utilizza il formato basato su SKOS.</span><span class="sxs-lookup"><span data-stu-id="03406-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="03406-112">Creare il file di importazione contenente i set di termini & condizioni che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="03406-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="03406-113">In **formato file**selezionare **SKOS (\*. TTL)**.</span><span class="sxs-lookup"><span data-stu-id="03406-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="03406-114">Fare clic su **Sfoglia** e passare a e aggiungere il file di importazione.</span><span class="sxs-lookup"><span data-stu-id="03406-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="03406-115">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="03406-115">Click **Import**.</span></span> <span data-ttu-id="03406-116">Non chiudere il pannello fino a quando non viene completata l'importazione.</span><span class="sxs-lookup"><span data-stu-id="03406-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="03406-117">Al termine dell'importazione del file verrà visualizzato un messaggio di esito positivo e l'archivio termini verrà aggiornato ed è possibile passare ai set di termini appena creati.</span><span class="sxs-lookup"><span data-stu-id="03406-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="03406-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03406-118">See also</span></span>

[<span data-ttu-id="03406-119">Introduzione ai metadati gestiti</span><span class="sxs-lookup"><span data-stu-id="03406-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="03406-120">Panoramica della comprensione del documento</span><span class="sxs-lookup"><span data-stu-id="03406-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="03406-121">Set di termini di importazione (livello di sito)</span><span class="sxs-lookup"><span data-stu-id="03406-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)