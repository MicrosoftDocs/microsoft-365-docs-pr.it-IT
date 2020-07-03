---
title: Rilevamento dei virus in SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
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
description: Informazioni sul modo in cui SharePoint Online rileva i virus nei file che gli utenti caricano e impediscono agli utenti di scaricare o sincronizzare i file.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60d696769ea402e6e2d0e52a1f6633e7962b8329
ms.sourcegitcommit: f2275d2fbc17a8b5b5da723c7353d3f36c6fb2a7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45029609"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="85057-103">Rilevamento dei virus in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="85057-103">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="85057-104">Microsoft 365 può aiutare a proteggere l'ambiente da malware, individuando i virus nei file caricati dagli utenti in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="85057-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="85057-105">I file possono essere analizzati per i virus dopo che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="85057-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="85057-106">Se si trova un file infetto, viene impostata una proprietà in modo che gli utenti non possano scaricare o sincronizzare il file.</span><span class="sxs-lookup"><span data-stu-id="85057-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85057-107">Queste funzionalità antivirus in SharePoint Online sono un modo per contenere virus.</span><span class="sxs-lookup"><span data-stu-id="85057-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="85057-108">Non sono intese come un singolo punto di difesa contro il malware per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="85057-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="85057-109">Si consiglia a tutti i clienti di valutare e implementare la protezione antimalware in vari livelli e applicare le procedure consigliate per la protezione dell'infrastruttura aziendale.</span><span class="sxs-lookup"><span data-stu-id="85057-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="85057-110">Per ulteriori informazioni sulle strategie e sulle procedure consigliate, vedere [Security roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="85057-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="85057-111">Cosa succede quando un file infetto viene caricato in SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="85057-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="85057-112">Microsoft 365 utilizza un motore di rilevamento virus comune.</span><span class="sxs-lookup"><span data-stu-id="85057-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="85057-113">Il motore viene eseguito in modo asincrono all'interno di SharePoint Online e analizza alcuni file dopo che sono stati caricati.</span><span class="sxs-lookup"><span data-stu-id="85057-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="85057-114">Per determinare quali file vengono analizzati, è possibile utilizzare l'euristica.</span><span class="sxs-lookup"><span data-stu-id="85057-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="85057-115">Quando un file viene trovato per contenere un virus, viene contrassegnato in modo che non possa essere scaricato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="85057-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="85057-116">Nel 2018 aprile, è stato rimosso il limite di 25 MB per i file analizzati.</span><span class="sxs-lookup"><span data-stu-id="85057-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="85057-117">Ecco cosa succede:</span><span class="sxs-lookup"><span data-stu-id="85057-117">Here's what happens:</span></span>

1. <span data-ttu-id="85057-118">Un utente carica un file in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="85057-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="85057-119">SharePoint Online determina se il file soddisfa i criteri per un'analisi.</span><span class="sxs-lookup"><span data-stu-id="85057-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="85057-120">Il motore di rilevamento dei virus analizza il file.</span><span class="sxs-lookup"><span data-stu-id="85057-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="85057-121">Se viene trovato un virus, il motore di virus imposta una proprietà sul file che indica che è infetto.</span><span class="sxs-lookup"><span data-stu-id="85057-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="85057-122">Cosa succede quando un utente tenta di scaricare un file infetto tramite il browser?</span><span class="sxs-lookup"><span data-stu-id="85057-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="85057-123">Se un file è infetto, gli utenti non possono scaricare il file da SharePoint Online utilizzando il browser.</span><span class="sxs-lookup"><span data-stu-id="85057-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="85057-124">Ecco cosa succede:</span><span class="sxs-lookup"><span data-stu-id="85057-124">Here's what happens:</span></span>

1. <span data-ttu-id="85057-125">Un utente apre un Web browser e tenta di scaricare un file infetto da SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="85057-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="85057-126">All'utente viene fornito un avviso che è stato rilevato un virus.</span><span class="sxs-lookup"><span data-stu-id="85057-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="85057-127">All'utente viene data la possibilità di scaricare il file e tentare di pulirlo usando il proprio software antivirus.</span><span class="sxs-lookup"><span data-stu-id="85057-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> <span data-ttu-id="85057-128">È possibile utilizzare il parametro *DisallowInfectedFileDownload* nel cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell per impedire agli utenti di scaricare un file infetto, anche nella finestra di avviso antivirus.</span><span class="sxs-lookup"><span data-stu-id="85057-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="85057-129">Cosa succede quando il client di sincronizzazione di OneDrive tenta di sincronizzare un file infetto?</span><span class="sxs-lookup"><span data-stu-id="85057-129">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="85057-130">Se gli utenti sincronizzano i file con il nuovo client di sincronizzazione di OneDrive (OneDrive.exe) o con il client di sincronizzazione di OneDrive for business precedente (Groove.exe), se un file contiene un virus, il client di sincronizzazione non lo scaricherà.</span><span class="sxs-lookup"><span data-stu-id="85057-130">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="85057-131">Il client di sincronizzazione visualizzerà una notifica che non è possibile sincronizzare il file.</span><span class="sxs-lookup"><span data-stu-id="85057-131">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="more-information"></a><span data-ttu-id="85057-132">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="85057-132">More information</span></span>

<span data-ttu-id="85057-133">Vedere [protezione dalle minacce](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) e [attivazione di ATP per SharePoint, OneDrive e Microsoft teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) per ulteriori informazioni su come configurare il programma antivirus di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="85057-133">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


