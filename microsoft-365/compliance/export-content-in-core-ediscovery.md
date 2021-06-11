---
title: Esportare e scaricare contenuto da un caso di Core eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Descrive come esportare e scaricare contenuto da un caso di eDiscovery di base in Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310843"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="43751-103">Esportare contenuti da un caso di Core eDiscovery</span><span class="sxs-lookup"><span data-stu-id="43751-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="43751-104">Dopo aver eseguito correttamente una ricerca associata a un caso di eDiscovery di base, è possibile esportare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="43751-104">After a search associated with a Core eDiscovery case is successfully run, you can export the search results.</span></span> <span data-ttu-id="43751-105">Quando si esportano i risultati della ricerca, gli elementi delle cassette postali vengono scaricati nei file PST o come singoli messaggi.</span><span class="sxs-lookup"><span data-stu-id="43751-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="43751-106">Quando si esporta contenuto da SharePoint e OneDrive for Business, vengono esportate copie di documenti Office nativi e altri documenti.</span><span class="sxs-lookup"><span data-stu-id="43751-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="43751-107">Viene esportato Results.csv file contenente informazioni su ogni elemento esportato e un file manifesto (in formato XML) contenente informazioni su ogni risultato della ricerca.</span><span class="sxs-lookup"><span data-stu-id="43751-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
## <a name="export-search-results"></a><span data-ttu-id="43751-108">Esportare i risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="43751-108">Export search results</span></span>

1. <span data-ttu-id="43751-109">Accedere a e accedere utilizzando le credenziali per l'account utente a cui sono state assegnate [https://compliance.microsoft.com](https://compliance.microsoft.com) le autorizzazioni di eDiscovery appropriate.</span><span class="sxs-lookup"><span data-stu-id="43751-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="43751-110">Nel riquadro di spostamento sinistro del Centro Microsoft 365 conformità fare clic su **Mostra** tutto e quindi su **eDiscovery > Core**.</span><span class="sxs-lookup"><span data-stu-id="43751-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="43751-111">Nella pagina **Core eDiscovery** fare clic sul nome del caso in cui si desidera creare il blocco.</span><span class="sxs-lookup"><span data-stu-id="43751-111">On the **Core eDiscovery** page, click the name of the case that you want to create the hold in.</span></span>

4. <span data-ttu-id="43751-112">Nella **home** page del caso fare clic sulla **scheda** Ricerche.</span><span class="sxs-lookup"><span data-stu-id="43751-112">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="43751-113">Scegliere **Esporta** risultati dal menu Azioni nella parte inferiore della pagina a **comparsa.**</span><span class="sxs-lookup"><span data-stu-id="43751-113">On the **Actions** menu at the bottom of the flyout page, click **Export results**.</span></span>

   ![Opzione Esporta risultati nel menu Azioni](../media/ActionMenuExportResults.png)

   <span data-ttu-id="43751-115">Il flusso di lavoro per esportare i risultati di una ricerca associata a un caso di eDiscovery di base corrisponde all'esportazione dei risultati della ricerca per una ricerca nella **pagina Ricerca contenuto.**</span><span class="sxs-lookup"><span data-stu-id="43751-115">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="43751-116">Per istruzioni dettagliate, vedere Export [content search results](export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="43751-116">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="43751-117">Quando si esportano i risultati della ricerca, è possibile abilitare la deduplicazione in modo che venga esportata solo una copia di un messaggio di posta elettronica anche se nelle cassette postali in cui è stata ricercata potrebbero essere state trovate più istanze dello stesso messaggio.</span><span class="sxs-lookup"><span data-stu-id="43751-117">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="43751-118">Per ulteriori informazioni sulla deduplicazione e su come vengono identificati gli elementi duplicati, vedere [De-duplicazione nei risultati della ricerca eDiscovery.](de-duplication-in-ediscovery-search-results.md)</span><span class="sxs-lookup"><span data-stu-id="43751-118">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

   <span data-ttu-id="43751-119">Dopo aver avviato l'esportazione, i risultati della ricerca vengono preparati per il download, il che significa che vengono trasferiti in un percorso di Archiviazione di Azure fornito da Microsoft nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="43751-119">After you start the export, the search results are prepared for downloading, which means they are transferred to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="43751-120">Fare clic **sulla scheda** Esportazioni nel caso in cui si desidera visualizzare l'elenco dei processi di esportazione.</span><span class="sxs-lookup"><span data-stu-id="43751-120">Click the **Exports** tab in the case to display the list of export jobs.</span></span>
  
   ![Esportare processi nella scheda Esporta nel caso di Core eDiscovery](../media/CoreeDiscoveryExport.png)

   <span data-ttu-id="43751-122">Potrebbe essere necessario fare clic **su Aggiorna** per aggiornare l'elenco dei processi di esportazione in modo che venga visualizzato il processo di esportazione creato.</span><span class="sxs-lookup"><span data-stu-id="43751-122">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="43751-123">I processi di esportazione hanno lo stesso nome della ricerca corrispondente **con _Export** aggiunto al nome di ricerca.</span><span class="sxs-lookup"><span data-stu-id="43751-123">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="43751-124">Fare clic sul processo di esportazione creato per visualizzare le informazioni sullo stato nella pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="43751-124">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="43751-125">Queste informazioni includono la percentuale di elementi che sono stati trasferiti nell'Archiviazione di Azure locale.</span><span class="sxs-lookup"><span data-stu-id="43751-125">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="43751-126">Dopo aver trasferito tutti gli elementi, fare clic **su Scarica risultati** per scaricare i risultati della ricerca nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="43751-126">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="43751-127">Per ulteriori informazioni sul download dei risultati della ricerca, vedere Passaggio 2 in [Esportare i risultati della ricerca di contenuto](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="43751-127">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

### <a name="more-information-about-exporting-searches-from-a-case"></a><span data-ttu-id="43751-128">Ulteriori informazioni sull'esportazione di ricerche da un caso</span><span class="sxs-lookup"><span data-stu-id="43751-128">More information about exporting searches from a case</span></span>

- <span data-ttu-id="43751-129">Per ulteriori informazioni sui file di esportazione inclusi quando si esportano i risultati della ricerca, vedere [Export a Content search report.](export-a-content-search-report.md#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="43751-129">For more information about the export files that are included when you export search results, see [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span></span>

- <span data-ttu-id="43751-130">Se si riavvia l'esportazione, le modifiche apportate alle query delle ricerche che costituiscono il processo di esportazione non influiranno sui risultati della ricerca recuperati.</span><span class="sxs-lookup"><span data-stu-id="43751-130">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="43751-131">Quando si riavvia un'esportazione, verrà eseguito di nuovo lo stesso processo di query di ricerca combinato eseguito al momento della creazione del processo di esportazione.</span><span class="sxs-lookup"><span data-stu-id="43751-131">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="43751-132">Inoltre, se si riavvia un'esportazione, i risultati della ricerca copiati nel percorso Archiviazione di Azure sovrascrivono i risultati precedenti.</span><span class="sxs-lookup"><span data-stu-id="43751-132">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="43751-133">I risultati precedenti copiati non saranno disponibili per il download.</span><span class="sxs-lookup"><span data-stu-id="43751-133">The previous results that were copied won't be available to be downloaded.</span></span>
