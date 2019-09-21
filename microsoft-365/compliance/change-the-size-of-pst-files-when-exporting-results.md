---
title: Modificare le dimensioni dei file PST quando si esportano i risultati della ricerca di eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: È possibile modificare le dimensioni predefinite dei file PST scaricati nel computer quando si esportano i risultati della ricerca di eDiscovery.
ms.openlocfilehash: 82a3d80cae04cd8d08b126c800ec2b4a1995f262
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083254"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="11908-103">Modificare le dimensioni dei file PST quando si esportano i risultati della ricerca di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="11908-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="11908-104">Quando si utilizza lo strumento di esportazione di eDiscovery di Office 365 per esportare i risultati di una ricerca di eDiscovery dai diversi strumenti di eDiscovery di Microsoft, le dimensioni predefinite di un file PST che può essere esportato sono 10 GB.</span><span class="sxs-lookup"><span data-stu-id="11908-104">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="11908-105">Se si desidera modificare queste dimensioni predefinite, è possibile modificare il registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="11908-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="11908-106">Un motivo per farlo è un file PST che può essere adattato ai supporti rimovibili, ad esempio un DVD, un disco compatto o un'unità USB.</span><span class="sxs-lookup"><span data-stu-id="11908-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="11908-107">Lo strumento di esportazione di Office 365 eDiscovery viene utilizzato per esportare i risultati della ricerca quando si utilizza lo strumento di ricerca contenuto nel centro sicurezza e conformità, eDiscovery in locale in Exchange Online e il centro eDiscovery in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="11908-107">The Office 365 eDiscovery Export tool is used to export the search results when using the Content Search tool in the security and compliance center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="11908-108">Creare un'impostazione del registro di sistema per modificare le dimensioni dei file PST quando si esportano i risultati della ricerca di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="11908-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="11908-109">Eseguire la procedura seguente nel computer che verrà utilizzato per esportare i risultati di una ricerca di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="11908-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="11908-110">Chiudere lo strumento di esportazione di Office 365 eDiscovery se è aperto.</span><span class="sxs-lookup"><span data-stu-id="11908-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="11908-111">Salvare il testo seguente in un file del registro di sistema di Windows utilizzando un suffisso FileName di. reg. ad esempio, PstExportSize. reg.</span><span class="sxs-lookup"><span data-stu-id="11908-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="11908-112">Nell'esempio precedente, il `PstSizeLimitInBytes` valore è impostato su 1.073.741.824 byte o circa 1 GB.</span><span class="sxs-lookup"><span data-stu-id="11908-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="11908-113">Di seguito sono riportati alcuni altri valori di `PstSizeLimitInBytes` esempio per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="11908-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="11908-114">**Dimensioni in GB (circa)**</span><span class="sxs-lookup"><span data-stu-id="11908-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="11908-115">**Dimensioni in byte**</span><span class="sxs-lookup"><span data-stu-id="11908-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="11908-116">.7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="11908-116">.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="11908-117">751619277</span><span class="sxs-lookup"><span data-stu-id="11908-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="11908-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="11908-118">2 GB</span></span>  <br/> |<span data-ttu-id="11908-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="11908-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="11908-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="11908-120">4 GB</span></span>  <br/> |<span data-ttu-id="11908-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="11908-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="11908-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="11908-122">8 GB</span></span>  <br/> |<span data-ttu-id="11908-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="11908-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="11908-124">Quando si `PstSizeLimitInBytes` esportano i risultati della ricerca, modificare il valore con le dimensioni massime desiderate di un file PST e quindi salvare il file.</span><span class="sxs-lookup"><span data-stu-id="11908-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="11908-125">In Esplora risorse fare clic o fare doppio clic sul file con estensione reg creato nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="11908-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="11908-126">Nella finestra controllo di accesso utente fare clic su **Sì** per consentire all'editor del registro di sistema di apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="11908-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="11908-127">Quando viene richiesto di continuare, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="11908-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="11908-128">L'editor del registro di sistema Visualizza un messaggio in cui viene indicato che l'impostazione è stata aggiunta correttamente al registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="11908-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="11908-129">È possibile ripetere i passaggi 3-6 per modificare il valore per `PstSizeLimitInBytes` l'impostazione del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="11908-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="11908-130">Domande frequenti su come modificare le dimensioni predefinite dei file PST quando si esportano i risultati della ricerca di eDiscovery</span><span class="sxs-lookup"><span data-stu-id="11908-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="11908-131">**Perché è la dimensione predefinita 10 GB?**</span><span class="sxs-lookup"><span data-stu-id="11908-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="11908-132">Le dimensioni predefinite di 10 GB si basano sul feedback dei clienti; 10 GB è un buon bilanciamento tra la quantità ottimale di contenuto in un singolo file PST e la possibilità minima di danneggiamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="11908-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="11908-133">**È consigliabile aumentare o diminuire la dimensione predefinita dei file PST?**</span><span class="sxs-lookup"><span data-stu-id="11908-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="11908-134">I clienti tendono a ridurre il limite di dimensione, in modo che i risultati della ricerca possano adattarsi ai supporti rimovibili che possono inviare fisicamente altre posizioni all'interno della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="11908-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship other locations in their organization.</span></span> <span data-ttu-id="11908-135">Non è consigliabile aumentare le dimensioni predefinite perché i file PST di dimensioni superiori a 10 GB potrebbero avere problemi di danneggiamento.</span><span class="sxs-lookup"><span data-stu-id="11908-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="11908-136">**Per quale computer è necessario eseguire questa operazione?**</span><span class="sxs-lookup"><span data-stu-id="11908-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="11908-137">È necessario modificare l'impostazione del registro di sistema in un computer locale in cui viene eseguito lo strumento di esportazione di eDiscovery di Office 365.</span><span class="sxs-lookup"><span data-stu-id="11908-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="11908-138">**Dopo aver modificato questa impostazione, è necessario riavviare il computer?**</span><span class="sxs-lookup"><span data-stu-id="11908-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="11908-139">No, non è necessario riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="11908-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="11908-140">Tuttavia, se lo strumento di esportazione di Office 365 eDiscovery è in esecuzione, sarà necessario chiuderlo e riavviarlo dopo la modifica di questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="11908-140">But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="11908-141">**Una chiave del registro di sistema esistente viene modificata o viene creata una nuova chiave?**</span><span class="sxs-lookup"><span data-stu-id="11908-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="11908-142">La prima volta che si esegue il file con estensione reg creato in questa procedura viene creata una nuova chiave del registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="11908-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="11908-143">L'impostazione viene quindi modificata ogni volta che viene modificato e rieseguito il file. reg Edit.</span><span class="sxs-lookup"><span data-stu-id="11908-143">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
