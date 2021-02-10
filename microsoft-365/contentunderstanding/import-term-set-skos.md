---
title: Importare un set di termini con un formato basato su SKOS
description: Scopri come importare un set di termini con un formato basato su SKOS
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 3d6efce9b6414444793da54d9c6d7be47d6a9a5c
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145080"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="6ebe6-103">Importare un set di termini con un formato basato su SKOS</span><span class="sxs-lookup"><span data-stu-id="6ebe6-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="6ebe6-104">È possibile importare un set di termini con un formato basato su SKOS.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="6ebe6-105">Per informazioni dettagliate sul formato, vedere [Riferimenti sul formato SKOS per la tassonomia di SharePoint.](skos-format-reference.md)</span><span class="sxs-lookup"><span data-stu-id="6ebe6-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span> <span data-ttu-id="6ebe6-106">Con questa funzionalità è richiesta una licenza di [SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="6ebe6-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="6ebe6-107">Si consiglia di mantenere meno di 20.000 termini nei file di importazione.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-107">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="6ebe6-108">I file più grandi possono aumentare il tempo necessario per la convalida e l'importazione.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-108">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="6ebe6-109">Nell'interfaccia di amministrazione di SharePoint espandere i **Servizi per contenuti**, quindi fare clic su **Archivio termini**.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-109">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="6ebe6-110">Selezionare il gruppo di termini in cui si desidera importare il set di termini.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-110">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="6ebe6-111">Nella barra dei comandi, fare clic su **Importa set di termini**. </span><span class="sxs-lookup"><span data-stu-id="6ebe6-111">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="6ebe6-112">Se si vuole desidera scaricare un file di esempio da usare come modello, fare clic su **sample-metadata.ttl** per ottenere un file di esempio che usa il formato basato su SKOS.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-112">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="6ebe6-113">Creare il file di importazione contenente i set di termini e i termini che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-113">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="6ebe6-114">In **Formato file**, selezionare **SKOS (\*.ttl)**.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-114">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="6ebe6-115">Fare clic su **Sfoglia**, raggiungere e aggiungere il file di importazione.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-115">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="6ebe6-116">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-116">Click **Import**.</span></span> <span data-ttu-id="6ebe6-117">Non chiudere il pannello fino al completamento dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-117">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="6ebe6-118">Dopo l'importazione del file, viene visualizzato un messaggio di esito positivo, l'archivio termini viene aggiornato e sarà possibile passare al set di termini appena creato.</span><span class="sxs-lookup"><span data-stu-id="6ebe6-118">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ebe6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ebe6-119">See also</span></span>

[<span data-ttu-id="6ebe6-120">Introduzione ai metadati gestiti</span><span class="sxs-lookup"><span data-stu-id="6ebe6-120">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="6ebe6-121">Panoramica sull'interpretazione del documento</span><span class="sxs-lookup"><span data-stu-id="6ebe6-121">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="6ebe6-122">Importare set di termini (a livello di sito)</span><span class="sxs-lookup"><span data-stu-id="6ebe6-122">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
