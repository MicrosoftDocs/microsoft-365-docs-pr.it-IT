---
title: ATP per SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365-initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Informazioni su Office 365 Advanced Threat Protection per i file in SharePoint Online, OneDrive for business e Microsoft teams.
ms.openlocfilehash: e36efba37ae21ee1e2044d8b631cb14b17fcca55
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411759"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="786b0-103">ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="786b0-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="786b0-104">ATP per SharePoint, OneDrive e Microsoft teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) fornisce un ulteriore livello di protezione per i file che sono già stati analizzati al momento del caricamento da parte del [motore di rilevamento virus comune in Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="786b0-104">ATP for SharePoint, OneDrive, and Microsoft Teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="786b0-105">ATP per SharePoint, OneDrive e Microsoft teams consente di rilevare e bloccare i file esistenti identificati come dannosi nei siti del team e nelle raccolte documenti.</span><span class="sxs-lookup"><span data-stu-id="786b0-105">ATP for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="786b0-106">ATP per SharePoint, OneDrive e Microsoft teams non è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="786b0-106">ATP for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="786b0-107">Per attivarlo, vedere [accendere ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="786b0-107">To turn it on, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="786b0-108">Funzionamento di ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="786b0-108">How ATP for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="786b0-109">Quando ATP per SharePoint, OneDrive e Microsoft teams è abilitato e identifica un file come dannoso, il file viene bloccato utilizzando l'integrazione diretta con gli archivi di file.</span><span class="sxs-lookup"><span data-stu-id="786b0-109">When ATP for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="786b0-110">Nell'immagine seguente viene mostrato un esempio di un file dannoso rilevato in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="786b0-110">The following image shows an example of a malicious file detected in a library.</span></span>

![File in OneDrive for business con uno rilevato come dannoso](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="786b0-112">Anche se il file bloccato è ancora elencato nella raccolta documenti e nelle applicazioni Web, per dispositivi mobili o desktop, gli utenti non possono aprire, copiare, spostare o condividere il file.</span><span class="sxs-lookup"><span data-stu-id="786b0-112">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="786b0-113">Tuttavia, è possibile eliminare il file bloccato.</span><span class="sxs-lookup"><span data-stu-id="786b0-113">But they can delete the blocked file.</span></span>

<span data-ttu-id="786b0-114">Di seguito è riportato un esempio di come si presenta un file bloccato su un dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="786b0-114">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Eliminazione di un file bloccato da OneDrive for business dall'app per dispositivi mobili di OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="786b0-116">Per impostazione predefinita, gli utenti possono scaricare un file bloccato.</span><span class="sxs-lookup"><span data-stu-id="786b0-116">By default, people can download a blocked file.</span></span> <span data-ttu-id="786b0-117">Di seguito è riportato l'aspetto del download di un file bloccato su un dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="786b0-117">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Download di un file bloccato in OneDrive for business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="786b0-119">Gli amministratori di SharePoint Online possono impedire agli utenti di scaricare file dannosi.</span><span class="sxs-lookup"><span data-stu-id="786b0-119">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="786b0-120">Per istruzioni, vedere [utilizzare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="786b0-120">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="786b0-121">Per ulteriori informazioni sull'esperienza utente quando un file è stato rilevato come dannoso, vedere [cosa fare quando si trova un file dannoso in SharePoint Online, OneDrive o Microsoft teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="786b0-121">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="786b0-122">Visualizzare informazioni sui file dannosi rilevati da ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="786b0-122">View information about malicious files detected by ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="786b0-123">I file identificati come dannosi da ATP verranno visualizzati nei [report di Office 365 Advanced Threat Protection](view-reports-for-atp.md) e in [Explorer (e in Real-Time detections)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="786b0-123">Files that are identified as malicious by ATP will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="786b0-124">A maggio 2018, quando un file viene identificato come dannoso da ATP, il file è disponibile anche in quarantena.</span><span class="sxs-lookup"><span data-stu-id="786b0-124">As of May 2018, when a file is identified as malicious by ATP, the file is also available in quarantine.</span></span> <span data-ttu-id="786b0-125">Per ulteriori informazioni, vedere [use the Security & Compliance Center per gestire i file in quarantena](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="786b0-125">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="786b0-126">Tenere presente questi punti</span><span class="sxs-lookup"><span data-stu-id="786b0-126">Keep these points in mind</span></span>

- <span data-ttu-id="786b0-127">ATP non analizzerà tutti i singoli file in SharePoint Online, OneDrive for business o Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="786b0-127">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="786b0-128">Si tratta di un comportamento legato alla progettazione.</span><span class="sxs-lookup"><span data-stu-id="786b0-128">This is by design.</span></span> <span data-ttu-id="786b0-129">I file vengono analizzati in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="786b0-129">Files are scanned asynchronously.</span></span> <span data-ttu-id="786b0-130">Il processo utilizza gli eventi di condivisione e attività Guest insieme a sistemi euristici intelligenti e segnalazioni di minacce per identificare i file dannosi.</span><span class="sxs-lookup"><span data-stu-id="786b0-130">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="786b0-131">Verificare che i siti di SharePoint siano configurati per l'utilizzo dell' [esperienza moderna](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="786b0-131">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="786b0-132">La protezione del trifosfato di adenosina applica se viene utilizzata l'esperienza moderna o la visualizzazione classica. Tuttavia, gli indicatori visivi che un file è bloccato sono disponibili solo nell'esperienza moderna.</span><span class="sxs-lookup"><span data-stu-id="786b0-132">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="786b0-133">ATP per SharePoint, OneDrive e Microsoft teams è parte integrante della strategia globale di protezione dalle minacce dell'organizzazione, che include la protezione da posta indesiderata e antimalware in Exchange Online Protection (EOP), nonché collegamenti sicuri e allegati sicuri in Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="786b0-133">ATP for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Office 365 ATP.</span></span> <span data-ttu-id="786b0-134">Per ulteriori informazioni, vedere [protezione dalle minacce in Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="786b0-134">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
