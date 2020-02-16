---
title: Preparare i dati per Office 365 Advanced eDiscovery
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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: "Informazioni su come utilizzare Microsoft 365 Security &amp; Compliance Center per preparare i dati di Office 365 per l'analisi con Office 365 Advanced eDiscovery. "
ms.openlocfilehash: 028cdb48e5ece2509d175a363c19beb6c2fafa19
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071033"
---
# <a name="prepare-data-for-office-365-advanced-ediscovery"></a><span data-ttu-id="b9cc8-103">Preparare i dati per Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b9cc8-103">Prepare data for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="b9cc8-104">In questo argomento viene descritto come caricare i risultati di una ricerca di contenuto in un caso in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-104">This topic describes how to load the results of a Content Search in to a case in Advanced eDiscovery.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b9cc8-105">Microsoft continua a investire in nuove versioni di Advanced eDiscovery e annuncia il ritiro di Office 365 Advanced eDiscovery, noto anche come *Advanced eDiscovery v1.0*.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery (also known as *Advanced eDiscovery v1.0*).</span></span> <span data-ttu-id="b9cc8-106">Se si usa ancora Advanced eDiscovery v 1.0, passare al più presto ad [Advanced eDiscovery v2.0](overview-ediscovery-20.md), noto anche come *soluzione Advanced eDiscovery in Microsoft 365*.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="b9cc8-107">Advanced eDiscovery 2.0 contiene funzionalità simili a quelle disponibili in Advanced eDiscovery v1.0, ma offre anche numerose nuove caratteristiche, come gestione dei responsabili, gestione delle comunicazioni e insiemi da rivedere.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="b9cc8-108">Per altre informazioni sul ritiro di Advanced eDiscovery v 1.0, vedere [Ritiro degli strumenti di eDiscovery legacy](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="b9cc8-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span>  
  
## <a name="step-1-prepare-office-365-data-for-advanced-ediscovery"></a><span data-ttu-id="b9cc8-109">Passaggio 1: preparare i dati di Office 365 per Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b9cc8-109">Step 1: Prepare Office 365 data for Advanced eDiscovery</span></span>

<span data-ttu-id="b9cc8-110">Per analizzare i dati con Advanced eDiscovery, è possibile utilizzare i risultati di una ricerca di contenuto eseguita nel centro &amp; sicurezza e conformità di Microsoft 365 (elencata nella pagina **Ricerca contenuto** nel centro sicurezza &amp; e conformità di Microsoft 365) oppure una ricerca associata a un caso eDiscovery (elencato nella pagina **eDiscovery** nel centro &amp; sicurezza e conformità).</span><span class="sxs-lookup"><span data-stu-id="b9cc8-110">To analyze data with Advanced eDiscovery, you can use the results of a Content Search that you run in the Microsoft 365 Security &amp; Compliance Center (listed on the **Content search** page in the Microsoft 365 Security &amp; Compliance Center) or a search associated with an eDiscovery case (listed on the **eDiscovery** page in the Security &amp; Compliance Center).</span></span> 
  
<span data-ttu-id="b9cc8-111">Per la procedura dettagliata relativa alla preparazione dei risultati della ricerca per l'analisi in Advanced eDiscovery, vedere [Prepare search results for Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="b9cc8-111">For the detailed steps on preparing search results for analysis in Advanced eDiscovery, see [Prepare search results for Office 365 Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9cc8-112">Se si dispone di dati al di fuori di Office 365 e si desidera importarlo in Office 365 in modo che sia possibile prepararlo e analizzarlo in Advanced eDiscovery, vedere [Overview of import PST files to office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) e [Archiving Third-Party data in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).</span><span class="sxs-lookup"><span data-stu-id="b9cc8-112">If you have data outside of Office 365 and want to import it to Office 365 so that you can prepare and analyze it in Advanced eDiscovery, a see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84) and [Archiving third-party data in Office 365](https://go.microsoft.com/fwlink/p/?linkid=716918).</span></span> 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a><span data-ttu-id="b9cc8-113">Passaggio 2: caricare i dati dei risultati della ricerca in un caso in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b9cc8-113">Step 2: Load search result data in to a case in Advanced eDiscovery</span></span>

<span data-ttu-id="b9cc8-114">Dopo aver preparato i risultati della ricerca nel centro &amp; sicurezza e conformità per l'analisi, il passaggio successivo consiste nel caricare i risultati della ricerca in un caso in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-114">After you prepare the search results in the Security &amp; Compliance Center for analysis, the next step is to load the search results in to a case in Advanced eDiscovery.</span></span> <span data-ttu-id="b9cc8-115">Per informazioni più dettagliate, vedere [Run the process Module](run-the-process-module-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="b9cc8-115">For more detailed information, see [Run the Process module](run-the-process-module-in-advanced-ediscovery.md).</span></span>
  
1. <span data-ttu-id="b9cc8-116">Passare a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="b9cc8-116">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="b9cc8-117">Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-117">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="b9cc8-118">Nel Centro sicurezza e conformità, fare clic su **Ricerca e analisi** \> **eDiscovery** per visualizzare l'elenco di casi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-118">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
4. <span data-ttu-id="b9cc8-119">Fare clic su **Apri** accanto al caso in cui si desidera caricare i dati in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-119">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
5. <span data-ttu-id="b9cc8-120">Nella **Home** page del caso, fare clic su **Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-120">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![Fare clic su passa a Advanced eDiscovery per aprire il caso in Advanced eDiscovery](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="b9cc8-122">Viene visualizzata la barra **di avanzamento per la connessione a Advanced eDiscovery** .</span><span class="sxs-lookup"><span data-stu-id="b9cc8-122">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="b9cc8-123">Quando si è connessi a Advanced eDiscovery, viene visualizzato un elenco di contenitori nella pagina di installazione del caso.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-123">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![Il caso viene visualizzato in Advanced eDiscovery](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="b9cc8-125">Questi contenitori rappresentano i risultati della ricerca preparati per l'analisi in Advanced eDiscovery nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-125">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="b9cc8-126">Si noti che il nome del contenitore ha lo stesso nome della ricerca di contenuto nel caso nel centro sicurezza &amp; e conformità.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-126">Note that the name of the container has the same name as the Content Search in the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="b9cc8-127">I contenitori presenti nell'elenco sono quelli che sono stati preparati.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-127">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="b9cc8-128">Se un utente diverso ha preparato i risultati della ricerca per Advanced eDiscovery, i contenitori corrispondenti non verranno inclusi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-128">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
6. <span data-ttu-id="b9cc8-129">Per caricare i dati dei risultati di ricerca da un contenitore al caso in Advanced eDiscovery, selezionare un contenitore e quindi fare clic su **processo**.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-129">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
<span data-ttu-id="b9cc8-130">Dopo aver aggiunto i risultati della ricerca &amp; dal centro sicurezza e conformità al caso in Advanced eDiscovery, il passaggio successivo consiste nell'utilizzare gli strumenti in Advanced eDiscovery per analizzare e abbattere i dati rilevanti per il caso.</span><span class="sxs-lookup"><span data-stu-id="b9cc8-130">After the search results from the Security &amp; Compliance Center are added to the case in Advanced eDiscovery, the next step is to use the tools in Advanced eDiscovery to analyze and cull the data that's relevant to the case.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b9cc8-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9cc8-131">See also</span></span>

[<span data-ttu-id="b9cc8-132">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b9cc8-132">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b9cc8-133">Configurare gli utenti e i casi</span><span class="sxs-lookup"><span data-stu-id="b9cc8-133">Set up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b9cc8-134">Analisi dei dati del caso</span><span class="sxs-lookup"><span data-stu-id="b9cc8-134">Analyzing case data</span></span>](analyze-case-data-with-advanced-ediscovery.md)
  
[<span data-ttu-id="b9cc8-135">Gestione della configurazione della pertinenza</span><span class="sxs-lookup"><span data-stu-id="b9cc8-135">Managing Relevance setup</span></span>](manage-relevance-setup-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b9cc8-136">Uso del modulo Rilevanza</span><span class="sxs-lookup"><span data-stu-id="b9cc8-136">Using the Relevance module</span></span>](use-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b9cc8-137">Esportazione dei dati del caso</span><span class="sxs-lookup"><span data-stu-id="b9cc8-137">Exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)

