---
title: Allegati sicuri per SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Informazioni su Microsoft Defender per Office 365 per i file in SharePoint Online, OneDrive for Business e Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7aa375020ce05ca1d484bb7ed18b8cf7a6e7d04e
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2021
ms.locfileid: "52932843"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7cbb9-103">Allegati sicuri per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7cbb9-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7cbb9-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="7cbb9-104">**Applies to**</span></span>
- [<span data-ttu-id="7cbb9-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="7cbb9-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7cbb9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7cbb9-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="7cbb9-107">Allegati sicuri per SharePoint, OneDrive e Microsoft Teams in Microsoft [Defender per Office 365](whats-new-in-defender-for-office-365.md) offre un ulteriore livello di protezione per i file che sono già stati analizzati in fase di caricamento dal motore di rilevamento virus comune [in Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="7cbb9-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="7cbb9-108">Allegati sicuri per SharePoint, OneDrive e Microsoft Teams consente di rilevare e bloccare i file esistenti identificati come dannosi nei siti del team e nelle raccolte documenti.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="7cbb9-109">Gli allegati sicuri per SharePoint, OneDrive e Microsoft Teams non sono abilitati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="7cbb9-110">Per attivarlo, vedere Attivare allegati sicuri per [SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7cbb9-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="7cbb9-111">Funzionamento degli allegati sicuri SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7cbb9-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="7cbb9-112">Quando allegati sicuri per SharePoint, OneDrive e Microsoft Teams è abilitato e identifica un file come dannoso, il file viene bloccato utilizzando l'integrazione diretta con gli archivi file.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="7cbb9-113">L'immagine di seguito mostra un esempio di file dannoso rilevato in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-113">The following image shows an example of a malicious file detected in a library.</span></span>

![File in OneDrive for Business con uno rilevato come dannoso](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="7cbb9-115">Anche se il file bloccato è ancora elencato nella raccolta documenti e nelle applicazioni Web, mobili o desktop, gli utenti non possono aprire, copiare, spostare o condividere il file.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="7cbb9-116">Ma possono eliminare il file bloccato.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="7cbb9-117">Ecco un esempio dell'aspetto di un file bloccato in un dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="7cbb9-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Eliminazione di un file bloccato OneDrive for Business dall'app OneDrive per dispositivi mobili](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="7cbb9-119">Per impostazione predefinita, gli utenti possono scaricare un file bloccato.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="7cbb9-120">Ecco l'aspetto del download di un file bloccato in un dispositivo mobile:</span><span class="sxs-lookup"><span data-stu-id="7cbb9-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Download di un file bloccato in OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="7cbb9-122">SharePoint Gli amministratori online possono impedire agli utenti di scaricare file dannosi.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="7cbb9-123">Per istruzioni, vedere [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="7cbb9-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="7cbb9-124">Per ulteriori informazioni sull'esperienza utente quando un file è stato rilevato come dannoso, vedere Cosa fare quando viene trovato un file dannoso [in SharePoint Online, OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)o Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="7cbb9-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7cbb9-125">Visualizzare informazioni sui file dannosi rilevati dagli allegati sicuri per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7cbb9-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="7cbb9-126">I file identificati come dannosi dagli allegati sicuri per SharePoint, OneDrive e Microsoft Teams verranno visualizzati nei report per [Microsoft Defender](view-reports-for-mdo.md) per Office 365 e in Esplora risorse (e rilevamenti in tempo [reale).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="7cbb9-126">Files that are identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="7cbb9-127">A maggio 2018, quando un file viene identificato come dannoso dagli allegati sicuri per SharePoint, OneDrive e Microsoft Teams, il file è disponibile anche in quarantena.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-127">As of May 2018, when a file is identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, the file is also available in quarantine.</span></span> <span data-ttu-id="7cbb9-128">Per altre informazioni, vedi [Gestire i file in quarantena in Defender per Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="7cbb9-128">For more information, see [Manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="7cbb9-129">Tenere presenti questi punti</span><span class="sxs-lookup"><span data-stu-id="7cbb9-129">Keep these points in mind</span></span>

- <span data-ttu-id="7cbb9-130">Defender per Office 365 non analizza ogni singolo file in SharePoint Online, OneDrive for Business o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="7cbb9-131">Si tratta di un comportamento legato alla progettazione.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-131">This is by design.</span></span> <span data-ttu-id="7cbb9-132">I file vengono analizzati in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="7cbb9-133">Il processo usa gli eventi di condivisione e attività guest insieme all'euristica intelligente e ai segnali di minaccia per identificare i file dannosi.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="7cbb9-134">Verificare che i siti SharePoint siano configurati per l'utilizzo [dell'esperienza moderna.](/sharepoint/guide-to-sharepoint-modern-experience)</span><span class="sxs-lookup"><span data-stu-id="7cbb9-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="7cbb9-135">Defender per Office 365 protezione si applica se viene usata l'esperienza moderna o la visualizzazione classica; Tuttavia, gli indicatori visivi che un file è bloccato sono disponibili solo nell'esperienza moderna.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="7cbb9-136">Allegati sicuri per SharePoint, OneDrive e Microsoft Teams fa parte della strategia generale di protezione dalle minacce dell'organizzazione, che include la protezione da posta indesiderata e antimalware in Exchange Online Protection (EOP), nonché collegamenti sicuri e allegati sicuri in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="7cbb9-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="7cbb9-137">Per ulteriori informazioni, vedere [Protezione dalle minacce in Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="7cbb9-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
