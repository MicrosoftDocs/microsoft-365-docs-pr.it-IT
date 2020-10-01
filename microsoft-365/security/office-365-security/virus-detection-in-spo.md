---
title: Protezione antivirus integrata in SharePoint Online, OneDrive e Microsoft Teams
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
ms.openlocfilehash: 38d6111fe665e0af79cbd93f534b1058881ff76c
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327988"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="9dfba-103">Protezione antivirus integrata in SharePoint Online, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9dfba-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9dfba-104">Microsoft 365 utilizza un motore di rilevamento virus comune per l'analisi dei file caricati dagli utenti in SharePoint Online, OneDrive e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="9dfba-104">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="9dfba-105">Questa protezione è inclusa in tutti gli abbonamenti che includono SharePoint Online, OneDrive e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="9dfba-105">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dfba-106">Le funzionalità di protezione da virus predefinite sono un modo per contribuire a contenere virus.</span><span class="sxs-lookup"><span data-stu-id="9dfba-106">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="9dfba-107">Non sono intese come un singolo punto di difesa contro il malware per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="9dfba-107">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="9dfba-108">Si consiglia a tutti i clienti di analizzare e implementare la protezione antimalware in vari livelli e applicare le procedure consigliate per la protezione dell'infrastruttura aziendale.</span><span class="sxs-lookup"><span data-stu-id="9dfba-108">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="9dfba-109">Per ulteriori informazioni sulle strategie e sulle procedure consigliate, vedere [Security roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="9dfba-109">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="9dfba-110">Cosa succede quando un file infetto viene caricato in SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="9dfba-110">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="9dfba-111">Il motore di rilevamento virus Microsoft 365 viene eseguito in modo asincrono all'interno di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9dfba-111">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="9dfba-112">**Tutti i file non vengono analizzati automaticamente al momento del caricamento**.</span><span class="sxs-lookup"><span data-stu-id="9dfba-112">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="9dfba-113">Gli euristici determinano i file da analizzare.</span><span class="sxs-lookup"><span data-stu-id="9dfba-113">Heuristics determine the files to scan.</span></span> <span data-ttu-id="9dfba-114">Quando viene trovato un file che contiene un virus, il file viene contrassegnato in modo che non possa essere scaricato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="9dfba-114">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="9dfba-115">Nel 2018 aprile, è stato rimosso il limite di 25 MB per i file analizzati.</span><span class="sxs-lookup"><span data-stu-id="9dfba-115">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="9dfba-116">Ecco cosa succede:</span><span class="sxs-lookup"><span data-stu-id="9dfba-116">Here's what happens:</span></span>

1. <span data-ttu-id="9dfba-117">Un utente carica un file in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9dfba-117">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="9dfba-118">SharePoint Online determina se il file soddisfa i criteri per un'analisi.</span><span class="sxs-lookup"><span data-stu-id="9dfba-118">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="9dfba-119">Il motore di rilevamento dei virus analizza il file.</span><span class="sxs-lookup"><span data-stu-id="9dfba-119">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="9dfba-120">Se viene trovato un virus, il motore di virus imposta una proprietà sul file che indica che è infetto.</span><span class="sxs-lookup"><span data-stu-id="9dfba-120">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="9dfba-121">Cosa succede quando un utente tenta di scaricare un file infetto tramite il browser?</span><span class="sxs-lookup"><span data-stu-id="9dfba-121">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="9dfba-122">Se un file è infetto, gli utenti non possono scaricare il file da SharePoint Online utilizzando un browser.</span><span class="sxs-lookup"><span data-stu-id="9dfba-122">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="9dfba-123">Ecco cosa succede:</span><span class="sxs-lookup"><span data-stu-id="9dfba-123">Here's what happens:</span></span>

1. <span data-ttu-id="9dfba-124">Un utente apre un Web browser e tenta di scaricare un file infetto da SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9dfba-124">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="9dfba-125">All'utente viene fornito un avviso che è stato rilevato un virus.</span><span class="sxs-lookup"><span data-stu-id="9dfba-125">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="9dfba-126">Per impostazione predefinita, all'utente viene data la possibilità di scaricare il file e tentare di pulirlo usando il software antivirus sul proprio dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9dfba-126">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="9dfba-127">Gli amministratori possono utilizzare il parametro *DisallowInfectedFileDownload* nel cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in PowerShell di SharePoint Online per impedire agli utenti di scaricare file infetti, anche nella finestra di avviso antivirus.</span><span class="sxs-lookup"><span data-stu-id="9dfba-127">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="9dfba-128">Per istruzioni, vedere [utilizzare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="9dfba-128">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="9dfba-129">Non appena si Abilita il parametro *DisallowInfectedFileDownload* , l'accesso ai file rilevati o bloccati viene completamente bloccato per gli utenti e gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="9dfba-129">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="9dfba-130">Cosa succede quando il client di sincronizzazione di OneDrive tenta di sincronizzare un file infetto?</span><span class="sxs-lookup"><span data-stu-id="9dfba-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="9dfba-131">I client di sincronizzazione di OneDrive non scaricheranno file che contengono virus.</span><span class="sxs-lookup"><span data-stu-id="9dfba-131">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="9dfba-132">Il client di sincronizzazione visualizzerà una notifica che non è possibile sincronizzare il file.</span><span class="sxs-lookup"><span data-stu-id="9dfba-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-advanced-threat-protection"></a><span data-ttu-id="9dfba-133">Funzionalità estese con Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="9dfba-133">Extended capabilities with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="9dfba-134">Microsoft 365 organizzazioni che dispongono di [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) incluse nell'abbonamento o acquistate come componente aggiuntivo possono abilitare ATP per SharePoint, OneDrive e Microsoft teams per la protezione e la creazione di report avanzati.</span><span class="sxs-lookup"><span data-stu-id="9dfba-134">Microsoft 365 organizations that have [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) included in their subscription or purchased as an add-on can enable ATP for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="9dfba-135">Per ulteriori informazioni, vedere [ATP for SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9dfba-135">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="9dfba-136">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="9dfba-136">More information</span></span>

<span data-ttu-id="9dfba-137">Per ulteriori informazioni sull'antivirus in SharePoint Online, OneDrive e Microsoft teams, vedere [protezione dalle minacce](protect-against-threats.md) e attivazione di [ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9dfba-137">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
