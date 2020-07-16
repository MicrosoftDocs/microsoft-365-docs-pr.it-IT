---
title: Visualizzare le attività delle etichette per i documenti
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 5/9/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Ottenere maggiori informazioni sull’uso di Esplora attività con etichette nel Centro sicurezza e conformità di Microsoft 365 per ricercare e consultare le attività delle etichette.
ms.openlocfilehash: e21bb867044b2a6644b125aad9983ce3518f70ee
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127273"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="67526-103">Visualizzare le attività delle etichette per i documenti</span><span class="sxs-lookup"><span data-stu-id="67526-103">View label activity for documents</span></span>

<span data-ttu-id="67526-p101">Dopo aver creato le etichette, è consigliabile verificare che vengano applicate al contenuto come previsto. Con Esplora attività con etichette nel Centro sicurezza e conformità, è possibile cercare e visualizzare rapidamente le attività con etichette per tutto il contenuto di SharePoint e OneDrive for Business degli ultimi 30 giorni. Si tratta di dati in tempo reale che offrono un quadro chiaro di ciò che accade nel tenant.</span><span class="sxs-lookup"><span data-stu-id="67526-p101">After you create your labels, you'll want to verify that they're being applied to content as you intended. With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days. This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="67526-107">Ad esempio, con Esplora attività con etichette è possibile:</span><span class="sxs-lookup"><span data-stu-id="67526-107">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="67526-108">Visualizzare la frequenza con cui ogni etichetta è stata applicata ogni giorno (fino a 30 giorni).</span><span class="sxs-lookup"><span data-stu-id="67526-108">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="67526-109">Vedere chi ha etichettato il file, quale file e in che data, visualizzando anche un collegamento al sito in cui si trova il file.</span><span class="sxs-lookup"><span data-stu-id="67526-109">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="67526-110">Visualizzare quali etichette di file sono state modificate o rimosse, quali sono le etichette vecchie o nuove e chi ha apportato la modifica.</span><span class="sxs-lookup"><span data-stu-id="67526-110">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="67526-p102">Filtrare i dati per visualizzare tutte le attività con etichette per un'etichetta, un file o un utente specifico. È anche possibile filtrare le attività con etichette in base alla posizione (SharePoint o OneDrive for Business) e in base a come è stata applicata l'etichetta, se manualmente o automaticamente.</span><span class="sxs-lookup"><span data-stu-id="67526-p102">Filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="67526-p103">Visualizzare le attività con etichette per le cartelle e i singoli documenti. A breve sarà possibile visualizzare il numero dei file nella cartella che sono stati denominati dopo aver assegnato un'etichetta alla cartella.</span><span class="sxs-lookup"><span data-stu-id="67526-p103">View label activity for folders as well as individual documents. Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="67526-115">Explorer attività etichette è disponibile nel &amp;Centro sicurezza e conformità > **Governance delle informazioni** > **Explorer attività etichette**.</span><span class="sxs-lookup"><span data-stu-id="67526-115">You can find the Label Activity Explorer in the Security &amp; Compliance Center > **Information governance** > **Label activity explorer**.</span></span>
  
<span data-ttu-id="67526-116">Esplora attività con etichette richiede un abbonamento a Office 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="67526-116">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![Esplora attività con etichette](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="67526-118">Visualizzare le attività con etichette per file o cartelle</span><span class="sxs-lookup"><span data-stu-id="67526-118">View label activities for files or folders</span></span>

<span data-ttu-id="67526-p104">Nella parte superiore di Esplora attività con etichette è possibile scegliere se visualizzare le attività per file o cartelle. Le attività della cartella riguardano solo la cartella, non i file al suo interno.</span><span class="sxs-lookup"><span data-stu-id="67526-p104">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders. Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="67526-p105">È consigliabile visualizzare le attività con etichette per le cartelle perché, se si etichetta una cartella, anche a tutti i file contenuti sarà applicata l'etichetta, ad eccezione di quelli a cui è già applicata esplicitamente un'etichetta. Di conseguenza, etichettare le cartelle potrebbe interessare un numero significativo di file. Per ulteriori informazioni, vedere [Applicazione di un'etichetta di conservazione predefinita a tutto il contenuto in una raccolta, una cartella o un set di documenti di SharePoint](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="67526-p105">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them). Therefore, labeling folders might affect a significant number of files. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](create-apply-retention-labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![Menu a discesa che mostra le attività con etichette per file e cartelle](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="67526-125">Attività con etichette</span><span class="sxs-lookup"><span data-stu-id="67526-125">Label activities</span></span>

 <span data-ttu-id="67526-p106">**Attività con etichette** include tutte le azioni relative alle etichette: **aggiunta**, **rimozione** o **modifica**. Questa visualizzazione può essere usata per ottenere un quadro completo del numero di file a cui, ogni giorno, è stata applicata una specifica etichetta.</span><span class="sxs-lookup"><span data-stu-id="67526-p106">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label. You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="67526-128">Modifiche di etichette</span><span class="sxs-lookup"><span data-stu-id="67526-128">Label changes</span></span>

 <span data-ttu-id="67526-p107">**Modifiche di etichette** include le azioni potenzialmente pericolose di **rimozione** o **modifica** di un'etichetta. È possibile usare questa visualizzazione per vedere rapidamente queste azioni rischiose e l'utente che le ha eseguite. Nell'elenco delle attività sotto il grafico è possibile selezionare un file e fare clic su un collegamento al file nel riquadro dei dettagli a destra.</span><span class="sxs-lookup"><span data-stu-id="67526-p107">**Label changes** includes the potentially risky actions of **removing** or **changing** a label. You can use this view to quickly see such risky actions and the user who performed them. In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![Riquadro dei dettagli per attività con etichette](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="67526-133">Filtrare le attività con etichette</span><span class="sxs-lookup"><span data-stu-id="67526-133">Filter label activity</span></span>

<span data-ttu-id="67526-p108">È possibile filtrare rapidamente i dati per visualizzare tutte le attività con etichette per un'etichetta, un file o un utente specifico. È anche possibile filtrare le attività con etichette in base alla posizione (SharePoint o OneDrive for Business) e in base a come è stata applicata l'etichetta, se manualmente o automaticamente.</span><span class="sxs-lookup"><span data-stu-id="67526-p108">You can quickly filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![Filtri per le attività con etichette](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

