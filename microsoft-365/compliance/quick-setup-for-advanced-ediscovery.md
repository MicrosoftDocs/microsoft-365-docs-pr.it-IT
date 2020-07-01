---
title: Configurazione rapida di Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: Informazioni su come accedere ad Advanced eDiscovery dal Centro sicurezza e conformità di &amp; e sul flusso di lavoro tipico per usare Advanced eDiscovery.
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936259"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a><span data-ttu-id="1629c-103">Configurazione rapida di Advanced eDiscovery (classico)</span><span class="sxs-lookup"><span data-stu-id="1629c-103">Quick setup Advanced eDiscovery (classic)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1629c-104">Microsoft continua a investire in nuove versioni di Advanced eDiscovery e annuncia il ritiro di Advanced eDiscovery, noto anche come *Advanced eDiscovery (classico)* o *Advanced eDiscovery v1.0*.</span><span class="sxs-lookup"><span data-stu-id="1629c-104">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="1629c-105">Se si usa ancora Advanced eDiscovery v 1.0, passare al più presto ad [Advanced eDiscovery v2.0](overview-ediscovery-20.md), noto anche come *soluzione Advanced eDiscovery in Microsoft 365*.</span><span class="sxs-lookup"><span data-stu-id="1629c-105">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="1629c-106">Advanced eDiscovery 2.0 contiene funzionalità simili a quelle disponibili in Advanced eDiscovery v1.0, ma offre anche numerose nuove caratteristiche, come gestione dei responsabili, gestione delle comunicazioni e insiemi da rivedere.</span><span class="sxs-lookup"><span data-stu-id="1629c-106">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="1629c-107">Per altre informazioni sul ritiro di Advanced eDiscovery v 1.0, vedere [Ritiro degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="1629c-107">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 

<span data-ttu-id="1629c-108">Questa sezione sulla configurazione mostra a un responsabile di eDiscovery del Centro sicurezza e conformità di Microsoft 365 come iniziare a usare Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1629c-108">This setup section shows an Microsoft 365 Security &amp; Compliance Center eDiscovery manager how to get started with Advanced eDiscovery.</span></span> <span data-ttu-id="1629c-109">Si presuppone una conoscenza di entrambi.</span><span class="sxs-lookup"><span data-stu-id="1629c-109">A working knowledge of both is assumed.</span></span>
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a><span data-ttu-id="1629c-110">Accedere a un caso in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="1629c-110">Accessing a case in Advanced eDiscovery</span></span>

<span data-ttu-id="1629c-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="1629c-111">You access Advanced eDiscovery from the Security &amp; Compliance Center.</span></span> <span data-ttu-id="1629c-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1629c-112">You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery.</span></span> <span data-ttu-id="1629c-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="1629c-113">For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md).</span></span> 
  
<span data-ttu-id="1629c-114">Per accedere a un caso in Advanced eDiscovery:</span><span class="sxs-lookup"><span data-stu-id="1629c-114">To go to a case in Advanced eDiscovery:</span></span> 
  
1. <span data-ttu-id="1629c-115">[Passare al Centro sicurezza &amp; conformità](go-to-the-securitycompliance-center.md) .</span><span class="sxs-lookup"><span data-stu-id="1629c-115">[Go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="1629c-116">Nel Centro sicurezza e conformità, fare clic su **Ricerca e analisi** \> **eDiscovery** per visualizzare l'elenco di casi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1629c-116">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
3. <span data-ttu-id="1629c-117">Nella pagina **eDiscovery**, fare clic su **Apri** accanto al caso a cui accedere in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1629c-117">On the **eDiscovery** page, click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span>
    
4. <span data-ttu-id="1629c-118">Nella **Home** page del caso, fare clic su **Passa ad Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="1629c-118">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span>
    
    <span data-ttu-id="1629c-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span><span class="sxs-lookup"><span data-stu-id="1629c-119">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="1629c-120">When you're connected, the case is opened in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1629c-120">When you're connected, the case is opened in Advanced eDiscovery.</span></span> 
    
## <a name="workflow"></a><span data-ttu-id="1629c-121">Flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1629c-121">Workflow</span></span>

<span data-ttu-id="1629c-122">Il seguente diagramma illustra il flusso di lavoro comune per gestire e usare i casi di eDiscovery nel Centro sicurezza e conformità e in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1629c-122">The following diagram illustrates the common workflow for managing and using eDiscovery cases in the Security &amp; Compliance Center and Advanced eDiscovery.</span></span>
  
![Il diagramma mostra il flusso di lavoro di Advanced eDiscovery di quattro fasi: installazione, inclusa l'impostazione di utenti &amp; casi, identificazione di dati sui casi, esportazione ed elaborazione. Mostra quindi le fasi di analisi ed esportazione in un computer locale.](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
<span data-ttu-id="1629c-124">This setup section describes the first four steps in the workflow.</span><span class="sxs-lookup"><span data-stu-id="1629c-124">This setup section describes the first four steps in the workflow.</span></span> <span data-ttu-id="1629c-125">For a description of the other steps in the workflow, see the following.</span><span class="sxs-lookup"><span data-stu-id="1629c-125">For a description of the other steps in the workflow, see the following.</span></span>
  
## <a name="analyze"></a><span data-ttu-id="1629c-126">Analisi</span><span class="sxs-lookup"><span data-stu-id="1629c-126">Analyze</span></span>

<span data-ttu-id="1629c-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span><span class="sxs-lookup"><span data-stu-id="1629c-127">[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results.</span></span> <span data-ttu-id="1629c-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span><span class="sxs-lookup"><span data-stu-id="1629c-128">Analyze functionality can be customized by the user in order to achieve enhanced results.</span></span> 
  
## <a name="relevance-setup-and-relevance"></a><span data-ttu-id="1629c-129">Configurazione della pertinenza e pertinenza</span><span class="sxs-lookup"><span data-stu-id="1629c-129">Relevance Setup and Relevance</span></span>

<span data-ttu-id="1629c-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span><span class="sxs-lookup"><span data-stu-id="1629c-130">[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process.</span></span> <span data-ttu-id="1629c-131">Calculates and displays interim results while monitoring statistical validity of the process.</span><span class="sxs-lookup"><span data-stu-id="1629c-131">Calculates and displays interim results while monitoring statistical validity of the process.</span></span> <span data-ttu-id="1629c-132">Displays the results to facilitate in making review decisions.</span><span class="sxs-lookup"><span data-stu-id="1629c-132">Displays the results to facilitate in making review decisions.</span></span> 
  
## <a name="export"></a><span data-ttu-id="1629c-133">Esportazione</span><span class="sxs-lookup"><span data-stu-id="1629c-133">Export</span></span>

<span data-ttu-id="1629c-134">[Esportazione dei dati dei casi](export-case-data-in-advanced-ediscovery.md) Consente di esportare i contenuti di Advanced eDiscovery e dei risultati per la revisione esterna.</span><span class="sxs-lookup"><span data-stu-id="1629c-134">[Exporting case data](export-case-data-in-advanced-ediscovery.md) Enables the exporting of Advanced eDiscovery content and results for external review.</span></span> 
  
## <a name="report"></a><span data-ttu-id="1629c-135">Report</span><span class="sxs-lookup"><span data-stu-id="1629c-135">Report</span></span>

<span data-ttu-id="1629c-136">[Esecuzione di report](run-reports-in-advanced-ediscovery.md) Consente la generazione di report selezionato correlati all'elaborazione di Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="1629c-136">[Running reports](run-reports-in-advanced-ediscovery.md) Enables the generation of selected reports related to Advanced eDiscovery processing.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1629c-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1629c-137">See also</span></span>

[<span data-ttu-id="1629c-138">Advanced eDiscovery (classico)</span><span class="sxs-lookup"><span data-stu-id="1629c-138">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="1629c-139">Configurazione di utenti e casi</span><span class="sxs-lookup"><span data-stu-id="1629c-139">Setting up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1629c-140">Preparazione dei dati</span><span class="sxs-lookup"><span data-stu-id="1629c-140">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)

