---
title: Rilevamento dei virus in SharePoint Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Office 365 può aiutare a proteggere l'ambiente da malware, individuando i virus nei file caricati dagli utenti in SharePoint Online. I file vengono analizzati per i virus dopo che sono stati caricati. Se si trova un file infetto, viene impostata una proprietà in modo che gli utenti non possano scaricare o sincronizzare il file.
ms.openlocfilehash: 9776dd7791d8543e0fd401a3c21c95d9fbf60f09
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639826"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="1fcc6-105">Rilevamento dei virus in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1fcc6-105">Virus detection in SharePoint Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fcc6-106">Per utilizzare questa funzionalità, è necessario Office 365 Advanced Threat Protection (ATP).</span><span class="sxs-lookup"><span data-stu-id="1fcc6-106">To use this feature, Office 365 Advanced Threat Protection (ATP) is required.</span></span> <span data-ttu-id="1fcc6-107">Per altre informazioni, vedere [Office 365 ATP per SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="1fcc6-107">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="1fcc6-108">Office 365 può aiutare a proteggere l'ambiente da malware, individuando i virus nei file caricati dagli utenti in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-108">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="1fcc6-109">I file vengono analizzati per i virus dopo che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-109">Files are scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="1fcc6-110">Se si trova un file infetto, viene impostata una proprietà in modo che gli utenti non possano scaricare o sincronizzare il file.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-110">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1fcc6-111">Queste funzionalità antivirus in SharePoint Online sono un modo per contenere virus.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-111">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="1fcc6-112">Non sono intese come un singolo punto di difesa contro il malware per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-112">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="1fcc6-113">Si consiglia a tutti i clienti di valutare e implementare la protezione antimalware in vari livelli e applicare le procedure consigliate per la protezione dell'infrastruttura aziendale.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-113">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="1fcc6-114">Per ulteriori informazioni sulle strategie e sulle procedure consigliate, vedere [Security roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="1fcc6-114">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="1fcc6-115">Cosa succede quando un file infetto viene caricato in SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="1fcc6-115">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="1fcc6-116">Office 365 utilizza un motore di rilevamento virus comune.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-116">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="1fcc6-117">Il motore viene eseguito in modo asincrono all'interno di SharePoint Online e analizza i file dopo che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-117">The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded.</span></span> <span data-ttu-id="1fcc6-118">Quando un file viene trovato per contenere un virus, viene contrassegnato in modo che non possa essere scaricato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-118">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="1fcc6-119">Nel 2018 aprile, è stato rimosso il limite di 25 MB per i file analizzati.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-119">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="1fcc6-120">Ecco cosa succede:</span><span class="sxs-lookup"><span data-stu-id="1fcc6-120">Here's what happens:</span></span>
  
1. <span data-ttu-id="1fcc6-121">Un utente carica un file in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-121">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="1fcc6-122">Il motore di rilevamento dei virus analizza il file.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-122">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="1fcc6-123">Se viene trovato un virus, il motore di virus imposta una proprietà sul file che indica che è infetto.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-123">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="1fcc6-124">Cosa succede quando un utente tenta di scaricare un file infetto tramite il browser?</span><span class="sxs-lookup"><span data-stu-id="1fcc6-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="1fcc6-125">Se un file è infetto da un virus, gli utenti non possono scaricare il file da SharePoint Online utilizzando il browser.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-125">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="1fcc6-126">Ecco cosa succede:</span><span class="sxs-lookup"><span data-stu-id="1fcc6-126">Here's what happens:</span></span>
  
1. <span data-ttu-id="1fcc6-127">Un utente apre un Web browser e tenta di scaricare un file infetto da SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="1fcc6-128">All'utente viene fornito un avviso che è stato rilevato un virus.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="1fcc6-129">All'utente viene data la possibilità di scaricare il file e tentare di pulirlo usando il proprio software antivirus.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-129">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="1fcc6-130">È possibile utilizzare il cmdlet Set-SPOTenant con il parametro **DisallowInfectedFileDownload** per non consentire agli utenti di scaricare un file rilevato, anche nella finestra di avviso antivirus.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-130">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="1fcc6-131">Vedere [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="1fcc6-131">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="1fcc6-132">Cosa succede quando il client di sincronizzazione di OneDrive tenta di sincronizzare un file infetto?</span><span class="sxs-lookup"><span data-stu-id="1fcc6-132">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="1fcc6-133">Se gli utenti sincronizzano i file con il nuovo client di sincronizzazione di OneDrive (OneDrive. exe) o il client di sincronizzazione di OneDrive for business precedente (Groove. exe), se un file contiene un virus, il client di sincronizzazione non lo scaricherà.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-133">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="1fcc6-134">Il client di sincronizzazione visualizzerà una notifica che non è possibile sincronizzare il file.</span><span class="sxs-lookup"><span data-stu-id="1fcc6-134">The sync client will display a notification that the file can't be synced.</span></span>
  

