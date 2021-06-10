---
title: Ottimizzare le immagini nelle pagine moderne di siti di SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Informazioni su come usare gli strumenti inclusi in SharePoint Online per ottimizzare le immagini nelle SharePoint siti moderni di SharePoint Online.
ms.openlocfilehash: a4f2def86e1378a9fb76ae9ecbe6a55da75ecffc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923017"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="dae2b-103">Ottimizzare le immagini nelle pagine moderne di siti di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dae2b-103">Optimize images in SharePoint Online modern site pages</span></span>

<span data-ttu-id="dae2b-104">Questo articolo spiega come ottimizzare le immagini nelle pagine moderne di siti di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="dae2b-104">This article will help you understand how to optimize images in SharePoint Online modern site pages.</span></span>

<span data-ttu-id="dae2b-105">Per informazioni su come ottimizzare le immagini in siti di pubblicazione classici, vedere [Ottimizzazione delle immagini per SharePoint Online](image-optimization-for-sharepoint-online.md).</span><span class="sxs-lookup"><span data-stu-id="dae2b-105">For information about optimizing images in classic publishing sites, see [Image optimization for SharePoint Online](image-optimization-for-sharepoint-online.md)..</span></span>

>[!NOTE]
><span data-ttu-id="dae2b-106">Per altre informazioni sulle prestazioni nei portali moderni di SharePoint Online, vedere [Prestazioni nell'esperienza moderna di SharePoint](/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="dae2b-106">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a><span data-ttu-id="dae2b-107">Usare lo strumento Diagnostica pagine per SharePoint per analizzare l'ottimizzazione delle immagini</span><span class="sxs-lookup"><span data-stu-id="dae2b-107">Use the Page Diagnostics for SharePoint tool to analyze image optimization</span></span>

<span data-ttu-id="dae2b-108">Lo strumento Diagnostica pagine per SharePoint è un'estensione del browser per il nuovo browser Microsoft Edge (https://www.microsoft.com/edge) e per Chrome che consente di analizzare le pagine del sito di pubblicazione di SharePoint Online sia classiche che dei portali moderni.</span><span class="sxs-lookup"><span data-stu-id="dae2b-108">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="dae2b-109">Per ogni pagina analizzata lo strumento fornisce un report che mostra le prestazioni della pagina rispetto a un set definiti di criteri delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="dae2b-109">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="dae2b-110">Per installare e conoscere lo strumento Diagnostica pagine per SharePoint, visitare [Usare lo strumento Diagnostica pagine per SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="dae2b-110">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="dae2b-111">Lo strumento Diagnostica pagine funziona solo per SharePoint Online e non può essere usato in una pagina di sistema di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="dae2b-111">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="dae2b-112">Quando si analizza un sito moderno di SharePoint con lo strumento Diagnostica pagine per SharePoint, è possibile visualizzare le informazioni sulle immagini di grandi dimensioni nel riquadro _Test diagnostici_.</span><span class="sxs-lookup"><span data-stu-id="dae2b-112">When you analyze a SharePoint modern site with the Page Diagnostics for SharePoint tool, you can see information about large images in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="dae2b-113">I risultati possibili includono:</span><span class="sxs-lookup"><span data-stu-id="dae2b-113">Possible results include:</span></span>

- <span data-ttu-id="dae2b-114">**Attenzione** (rosso): la pagina contiene **una o più** immagini di dimensioni superiori a 300 KB</span><span class="sxs-lookup"><span data-stu-id="dae2b-114">**Attention required** (red): The page contains **one or more** images over 300KB in size</span></span>
- <span data-ttu-id="dae2b-115">**Non è richiesto alcun intervento** (verde): la pagina non contiene immagini di dimensioni superiori a 300 KB</span><span class="sxs-lookup"><span data-stu-id="dae2b-115">**No action required** (green): The page contains no images over 300KB in size</span></span>

<span data-ttu-id="dae2b-116">Se nella sezione dei risultati **Attenzione** viene visualizzato il risultato **Sono state rilevate immagini di grandi dimensioni**, è possibile fare clic sul risultato per visualizzare altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="dae2b-116">If the **Large images detected** result appears in the **Attention required** section of the results, you can click the result to see additional details.</span></span>

![Risultati dello strumento Diagnostica pagine](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a><span data-ttu-id="dae2b-118">Risolvere i problemi relativi a immagini di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="dae2b-118">Remediate large image issues</span></span>

<span data-ttu-id="dae2b-119">Se una pagina contiene immagini di dimensioni superiori a 300 KB, selezionare il risultato **Sono state rilevate immagini di grandi dimensioni** per visualizzare le immagini di dimensioni eccessive.</span><span class="sxs-lookup"><span data-stu-id="dae2b-119">If a page contains images over 300KB in size, select the **Large images detected** result to see which images are too large.</span></span> <span data-ttu-id="dae2b-120">Nelle pagine moderne di SharePoint Online i rendering delle immagini vengono forniti e ridimensionati automaticamente a seconda delle dimensioni della finestra del browser e della risoluzione del monitor client.</span><span class="sxs-lookup"><span data-stu-id="dae2b-120">In modern SharePoint Online pages, renditions of images are automatically provided and sized depending on the size of the browser window and the resolution of the client monitor.</span></span> <span data-ttu-id="dae2b-121">È consigliabile ottimizzare sempre le immagini per l'uso Web prima di caricarle in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="dae2b-121">You should always optimize images for web use prior to upload to SharePoint Online.</span></span> <span data-ttu-id="dae2b-122">Le dimensioni e la risoluzione di immagini di grandi dimensioni verranno ridotte automaticamente e questa riduzione può influire sul rendering.</span><span class="sxs-lookup"><span data-stu-id="dae2b-122">Very large images will be automatically reduced in size and resolution which can result in unexpected rendering characteristics.</span></span>

<span data-ttu-id="dae2b-123">Prima di revisionare le pagine per correggere i problemi di prestazioni, prendere nota del tempo di caricamento delle pagine nei risultati dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="dae2b-123">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="dae2b-124">Eseguire di nuovo lo strumento dopo la revisione per verificare se il nuovo risultato è compreso nello standard di base e controllare il nuovo tempo di caricamento della pagina per verificare se c'è stato un miglioramento.</span><span class="sxs-lookup"><span data-stu-id="dae2b-124">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Risultati del tempo di caricamento delle pagine](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="dae2b-126">Il tempo di caricamento delle pagine dipende da numerosi fattori, ad esempio il carico di rete, l'ora del giorno e altre condizioni transitorie.</span><span class="sxs-lookup"><span data-stu-id="dae2b-126">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="dae2b-127">È consigliabile verificare il tempo di caricamento delle pagine alcune volte prima e dopo aver apportato modifiche in modo da ottenere una media dei risultati.</span><span class="sxs-lookup"><span data-stu-id="dae2b-127">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dae2b-128">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="dae2b-128">Related topics</span></span>

[<span data-ttu-id="dae2b-129">Ottimizzare le prestazioni di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dae2b-129">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="dae2b-130">Ottimizzare le prestazioni di Office 365</span><span class="sxs-lookup"><span data-stu-id="dae2b-130">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="dae2b-131">Prestazioni nell'esperienza moderna di SharePoint</span><span class="sxs-lookup"><span data-stu-id="dae2b-131">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)

[<span data-ttu-id="dae2b-132">Reti per la distribuzione di contenuti</span><span class="sxs-lookup"><span data-stu-id="dae2b-132">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="dae2b-133">Usare la rete per la distribuzione di contenuti di Office 365 con SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dae2b-133">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)