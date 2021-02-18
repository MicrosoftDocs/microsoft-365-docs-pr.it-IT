---
title: Protezione da virus integrata in SharePoint Online, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Informazioni su come SharePoint Online rileva i virus nei file caricati dagli utenti e impedisce agli utenti di scaricare o sincronizzare i file.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0eafb9e5e2f0c9d86791fe83931276e420afcd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286502"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="38dbe-103">Protezione da virus integrata in SharePoint Online, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38dbe-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="38dbe-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="38dbe-104">**Applies to**</span></span>
- [<span data-ttu-id="38dbe-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="38dbe-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="38dbe-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="38dbe-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="38dbe-107">Microsoft 365 usa un motore di rilevamento virus comune per l'analisi dei file caricati dagli utenti in SharePoint Online, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38dbe-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="38dbe-108">Questa protezione è inclusa in tutti gli abbonamenti che includono SharePoint Online, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38dbe-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38dbe-109">Le funzionalità antivirus integrate sono un modo per contenere i virus.</span><span class="sxs-lookup"><span data-stu-id="38dbe-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="38dbe-110">Non sono concepiti come un unico punto di difesa contro il malware per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="38dbe-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="38dbe-111">Invitiamo tutti i clienti ad analizzare e implementare la protezione antimalware a vari livelli e ad applicare le procedure consigliate per la protezione dell'infrastruttura aziendale.</span><span class="sxs-lookup"><span data-stu-id="38dbe-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="38dbe-112">Per ulteriori informazioni sulle strategie e sulle procedure consigliate, vedere [Security roadmap.](security-roadmap.md)</span><span class="sxs-lookup"><span data-stu-id="38dbe-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="38dbe-113">Cosa succede quando un file infetto viene caricato in SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="38dbe-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="38dbe-114">Il motore di rilevamento virus di Microsoft 365 viene eseguito in modo asincrono all'interno di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="38dbe-114">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="38dbe-115">**Tutti i file non vengono analizzati automaticamente al caricamento.**</span><span class="sxs-lookup"><span data-stu-id="38dbe-115">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="38dbe-116">L'euristica determina i file da analizzare.</span><span class="sxs-lookup"><span data-stu-id="38dbe-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="38dbe-117">Quando viene rilevato che un file contiene un virus, il file viene contrassegnato in modo che non possa essere scaricato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="38dbe-117">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="38dbe-118">Ad aprile 2018 è stato rimosso il limite di 25 MB per i file analizzati.</span><span class="sxs-lookup"><span data-stu-id="38dbe-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="38dbe-119">Ecco cosa succede:</span><span class="sxs-lookup"><span data-stu-id="38dbe-119">Here's what happens:</span></span>

1. <span data-ttu-id="38dbe-120">Un utente carica un file in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="38dbe-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="38dbe-121">SharePoint Online determina se il file soddisfa i criteri per un'analisi.</span><span class="sxs-lookup"><span data-stu-id="38dbe-121">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="38dbe-122">Il motore di rilevamento virus analizza il file.</span><span class="sxs-lookup"><span data-stu-id="38dbe-122">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="38dbe-123">Se viene trovato un virus, il motore del virus imposta una proprietà sul file che indica che è stato infettato.</span><span class="sxs-lookup"><span data-stu-id="38dbe-123">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="38dbe-124">Cosa succede quando un utente tenta di scaricare un file infetto usando il browser?</span><span class="sxs-lookup"><span data-stu-id="38dbe-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="38dbe-125">Se un file è infetto, gli utenti non possono scaricarlo da SharePoint Online utilizzando un browser.</span><span class="sxs-lookup"><span data-stu-id="38dbe-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="38dbe-126">Ecco cosa succede:</span><span class="sxs-lookup"><span data-stu-id="38dbe-126">Here's what happens:</span></span>

1. <span data-ttu-id="38dbe-127">Un utente apre un Web browser e tenta di scaricare un file infetto da SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="38dbe-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="38dbe-128">All'utente viene visualizzato un avviso che indica che è stato rilevato un virus.</span><span class="sxs-lookup"><span data-stu-id="38dbe-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="38dbe-129">Per impostazione predefinita, all'utente viene data la possibilità di scaricare il file e tentare di pulirlo utilizzando il software antivirus nel proprio dispositivo.</span><span class="sxs-lookup"><span data-stu-id="38dbe-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="38dbe-130">Gli amministratori possono utilizzare il parametro *DisallowInfectedFileDownload* nel cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in PowerShell di SharePoint Online per impedire agli utenti di scaricare file infetti, anche nella finestra di avviso antivirus.</span><span class="sxs-lookup"><span data-stu-id="38dbe-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="38dbe-131">Per istruzioni, vedere [Usare PowerShell di SharePoint Online](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)per impedire agli utenti di scaricare file dannosi.</span><span class="sxs-lookup"><span data-stu-id="38dbe-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="38dbe-132">Non appena si abilita il parametro *DisallowInfectedFileDownload,* l'accesso ai file rilevati/bloccati viene completamente bloccato per utenti e amministratori.</span><span class="sxs-lookup"><span data-stu-id="38dbe-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="38dbe-133">Cosa succede quando il client di sincronizzazione di OneDrive tenta di sincronizzare un file infetto?</span><span class="sxs-lookup"><span data-stu-id="38dbe-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="38dbe-134">I client di sincronizzazione di OneDrive non scarieranno i file contenenti virus.</span><span class="sxs-lookup"><span data-stu-id="38dbe-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="38dbe-135">Il client di sincronizzazione visualizza una notifica che indica che il file non può essere sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="38dbe-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="38dbe-136">Funzionalità estese con Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="38dbe-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="38dbe-137">Le organizzazioni di Microsoft 365 con [Microsoft Defender per Office 365](office-365-atp.md) incluso nell'abbonamento o acquistate come componente aggiuntivo possono abilitare allegati sicuri per SharePoint, OneDrive e Microsoft Teams per la creazione di report e la protezione avanzata.</span><span class="sxs-lookup"><span data-stu-id="38dbe-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](office-365-atp.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="38dbe-138">Per ulteriori informazioni, vedere [Allegati sicuri per SharePoint, OneDrive e Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="38dbe-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="38dbe-139">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="38dbe-139">Related Articles</span></span>

[<span data-ttu-id="38dbe-140">Protezione da malware e ransomware in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="38dbe-140">Malware and ransomware protection in Microsoft 365</span></span>](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="38dbe-141">Per ulteriori informazioni sull'antivirus in SharePoint Online, OneDrive [](protect-against-threats.md) e Microsoft Teams, vedere Proteggere dalle minacce e attivare allegati sicuri per [SharePoint, OneDrive e Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="38dbe-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
