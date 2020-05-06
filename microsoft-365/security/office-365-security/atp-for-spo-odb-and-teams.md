---
title: ATP per SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: Informazioni su Office 365 Advanced Threat Protection per i file in SharePoint Online, OneDrive for business e Microsoft teams.
ms.openlocfilehash: 90e84f0a4393e5097fb59b93693862a21d6d9f2f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031449"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="df772-103">ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df772-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="df772-104">Panoramica di Office 365 ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df772-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="df772-105">Gli utenti condividono periodicamente file e collaborano con SharePoint, OneDrive e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="df772-105">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="df772-106">Con [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), l'organizzazione può collaborare in maniera più sicura.</span><span class="sxs-lookup"><span data-stu-id="df772-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner.</span></span> <span data-ttu-id="df772-107">ATP aiuta a rilevare e bloccare i file identificati come dannosi nei siti del team e nelle raccolte documenti.</span><span class="sxs-lookup"><span data-stu-id="df772-107">ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="df772-108">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="df772-108">How it works</span></span>

<span data-ttu-id="df772-109">Quando un file in SharePoint Online, OneDrive for business e Microsoft teams è stato identificato come dannoso, ATP si integra direttamente con gli archivi di file per bloccare il file.</span><span class="sxs-lookup"><span data-stu-id="df772-109">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file.</span></span> <span data-ttu-id="df772-110">Nell'immagine seguente viene mostrato un esempio di un file dannoso rilevato in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="df772-110">The following image shows an example of a malicious file detected in a library.</span></span>

![File in OneDrive for business con uno rilevato come dannoso](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="df772-112">Anche se il file bloccato è ancora elencato nella raccolta documenti e nelle applicazioni Web, per dispositivi mobili o desktop, il file bloccato non può essere aperto, copiato, spostato o condiviso.</span><span class="sxs-lookup"><span data-stu-id="df772-112">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared.</span></span> <span data-ttu-id="df772-113">Tuttavia, gli utenti possono eliminare un file bloccato.</span><span class="sxs-lookup"><span data-stu-id="df772-113">People can, however, delete a blocked file.</span></span> <span data-ttu-id="df772-114">Di seguito è riportato un esempio di come si presenta sul dispositivo mobile di un utente:</span><span class="sxs-lookup"><span data-stu-id="df772-114">Here's an example of what that looks like on a user's mobile device:</span></span>

![Eliminazione di un file bloccato da OneDrive for business dall'app per dispositivi mobili di OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="df772-116">A seconda del modo in cui Microsoft 365 è configurato, la gente potrebbe o meno avere la possibilità di scaricare un file bloccato.</span><span class="sxs-lookup"><span data-stu-id="df772-116">Depending on how Microsoft 365 is configured, people might or might not have the ability to download a blocked file.</span></span> <span data-ttu-id="df772-117">Di seguito è riportato l'aspetto del download di un file bloccato nel dispositivo mobile di un utente:</span><span class="sxs-lookup"><span data-stu-id="df772-117">Here's what downloading a blocked file looks like on a user's mobile device:</span></span>

![Download di un file bloccato in OneDrive for business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="df772-119">Per altre informazioni, vedere [Office 365 ATP per SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="df772-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="df772-120">Tenere presente questi punti</span><span class="sxs-lookup"><span data-stu-id="df772-120">Keep these points in mind</span></span>

- <span data-ttu-id="df772-121">ATP non analizzerà tutti i singoli file in SharePoint Online, OneDrive for business o Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="df772-121">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="df772-122">Questo è il funzionamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="df772-122">This is by design.</span></span> <span data-ttu-id="df772-123">I file vengono analizzati in modo asincrono, tramite un processo che utilizza la condivisione e gli eventi di attività Guest insieme ai segnali euristici intelligenti e alle minacce per identificare i file dannosi.</span><span class="sxs-lookup"><span data-stu-id="df772-123">Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="df772-124">Verificare che i siti di SharePoint siano configurati per l'utilizzo dell' [esperienza moderna](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="df772-124">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="df772-125">Quando un file viene identificato come dannoso e bloccato, gli utenti possono vedere che si è verificato l'esperienza moderna, ma non la visualizzazione classica.</span><span class="sxs-lookup"><span data-stu-id="df772-125">When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view.</span></span> <span data-ttu-id="df772-126">La protezione del trifosfato di adenosina applica se viene utilizzata l'esperienza moderna o la visualizzazione classica. Tuttavia, gli indicatori visivi che un file è bloccato sono presenti solo nell'esperienza moderna.</span><span class="sxs-lookup"><span data-stu-id="df772-126">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>

- <span data-ttu-id="df772-127">I file identificati come dannosi in SharePoint Online, OneDrive for business o Microsoft teams verranno visualizzati nei [report di Office 365 Advanced Threat Protection](view-reports-for-atp.md) e in [Explorer (e in Real-Time detections)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="df772-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

- <span data-ttu-id="df772-128">ATP fa parte della strategia globale di protezione dalle minacce dell'organizzazione, che include protezione da posta indesiderata e antimalware, oltre a collegamenti sicuri e allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="df772-128">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments.</span></span> <span data-ttu-id="df772-129">Per ulteriori informazioni, vedere [protezione dalle minacce in Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="df772-129">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="df772-130">Un amministratore di SharePoint Online può decidere se consentire agli utenti di scaricare file che vengono rilevati come dannosi.</span><span class="sxs-lookup"><span data-stu-id="df772-130">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious.</span></span> <span data-ttu-id="df772-131">A tale scopo, è possibile eseguire il cmdlet Set-SPOTenant di PowerShell utilizzando un parametro DisallowInfectedFileDownload (vedere [accendere Office 365 ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md)).</span><span class="sxs-lookup"><span data-stu-id="df772-131">This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="df772-132">Quarantena in ATP per SharePoint Online, OneDrive for business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df772-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="df772-133">A partire dalla fine di maggio 2018, le funzionalità di [quarantena](quarantine-email-messages.md) nel centro sicurezza &amp; e conformità vengono estese a ATP per SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="df772-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="df772-134">Quando un file in SharePoint Online, OneDrive for business o Microsoft teams viene identificato come dannoso, oltre a ATP che blocca il file dall'apertura o dalla condivisione, tale file è incluso in un elenco di elementi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="df772-134">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items.</span></span> <span data-ttu-id="df772-135">Nel &amp; Centro sicurezza e conformità, passare alla **quarantena** e al filtro per la **gestione** \> **Review** \> delle minacce per **i file**.</span><span class="sxs-lookup"><span data-stu-id="df772-135">(In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Files**.)</span></span>

<span data-ttu-id="df772-136">Se si è parte del team di sicurezza Microsoft 365 for business dell'organizzazione e le autorizzazioni necessarie sono state [assegnate al centro &amp; sicurezza e conformità](permissions-in-the-security-and-compliance-center.md), è possibile scaricare, rilasciare, segnalare ed eliminare file che vengono rilevati come dannosi da ATP dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="df772-136">If you're part of your organization's Microsoft 365 for business security team and have the necessary [permissions assigned in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>

- <span data-ttu-id="df772-137">Il **rilascio e la segnalazione** di un file rimuove il blocco ATP nel file nel sito del team o nella raccolta documenti di SharePoint, OneDrive o Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="df772-137">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams.</span></span> <span data-ttu-id="df772-138">Gli utenti sono quindi in grado di aprire, condividere e scaricare il file.</span><span class="sxs-lookup"><span data-stu-id="df772-138">Users are then able to open, share, and download the file.</span></span> <span data-ttu-id="df772-139">Quando l'opzione **Invia rapporto a Microsoft** è selezionata, il file viene segnalato come falso positivo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df772-139">And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span>

- <span data-ttu-id="df772-140">L' **eliminazione di un file** consente di rimuovere il file dalla quarantena; Tuttavia, il file è ancora bloccato dall'apertura o dalla condivisione.</span><span class="sxs-lookup"><span data-stu-id="df772-140">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared.</span></span> <span data-ttu-id="df772-141">Il file deve essere eliminato anche nella rispettiva raccolta documenti o sito del team (SharePoint Online, OneDrive for business o Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="df772-141">The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span>

- <span data-ttu-id="df772-142">Il **download di un file** consente di scaricare e analizzare il file per eventuali falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="df772-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span>

## <a name="next-steps"></a><span data-ttu-id="df772-143">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="df772-143">Next steps</span></span>

 - [<span data-ttu-id="df772-144">Attivazione di Office 365 ATP per SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df772-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

 - [<span data-ttu-id="df772-145">Visualizzare informazioni sui file dannosi rilevati in SharePoint, OneDrive o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df772-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

