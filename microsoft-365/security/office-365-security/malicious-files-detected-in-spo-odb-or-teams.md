---
title: Visualizzare informazioni sui file dannosi rilevati da Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
ms.collection:
- M365-security-compliance
description: Per informazioni su come eseguire le operazioni su tali file, vedere l'articolo relativo alla visualizzazione dei file dannosi rilevati in SharePoint, OneDrive o teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47b1fea4b3b5713a8f69e8f4b2c0e2ad0f6dd6b8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036645"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="34fa6-103">Visualizzare informazioni sui file dannosi rilevati in SharePoint, OneDrive o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34fa6-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="34fa6-104">[Office 365 ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) protegge l'organizzazione da file dannosi nelle raccolte documenti e nei siti del team.</span><span class="sxs-lookup"><span data-stu-id="34fa6-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites.</span></span> <span data-ttu-id="34fa6-105">Quando viene rilevato un file dannoso, il file viene bloccato in modo che nessuno possa aprirlo, copiarlo, spostarlo o condividerlo fino a quando non vengono intraprese altre azioni da parte del team di sicurezza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="34fa6-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="34fa6-106">Leggere questo articolo per scoprire come visualizzare le informazioni sui file rilevati e le azioni da intraprendere.</span><span class="sxs-lookup"><span data-stu-id="34fa6-106">Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="34fa6-107">Per eseguire le attività descritte in questo articolo, è necessario disporre delle [autorizzazioni necessarie per il &amp; Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="34fa6-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="34fa6-108">Visualizzare i report con informazioni sui file rilevati</span><span class="sxs-lookup"><span data-stu-id="34fa6-108">View reports with information about detected files</span></span>

<span data-ttu-id="34fa6-109">Per visualizzare lo stato e informazioni dettagliate sui file che sono stati rilevati da Office 365 ATP, è possibile utilizzare il rapporto sullo stato di protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="34fa6-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="34fa6-110">Nel [Centro sicurezza &amp; e conformità](https://protection.office.com), scegliere **segnala** \> **Dashboard** \> **lo stato di protezione delle minacce**del dashboard.</span><span class="sxs-lookup"><span data-stu-id="34fa6-110">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="34fa6-111">Nell'angolo in alto a destra del report, scegliere **Visualizza dettagli tabella**.</span><span class="sxs-lookup"><span data-stu-id="34fa6-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="34fa6-112">Visualizzare l'elenco dei file che sono stati rilevati nel report.</span><span class="sxs-lookup"><span data-stu-id="34fa6-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="34fa6-113">Selezionare un elemento nell'elenco per visualizzare informazioni dettagliate, incluse le azioni eseguite, il nome del file, il percorso del file e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="34fa6-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="34fa6-114">Scegliere la scheda **analisi avanzata** per visualizzare le informazioni, ad esempio il comportamento osservato e i dettagli dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="34fa6-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="34fa6-115">Visualizzare ed eseguire azioni sui file in quarantena</span><span class="sxs-lookup"><span data-stu-id="34fa6-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="34fa6-116">Nel centro sicurezza &amp; e conformità, scegliere **quarantena** **Revisione** \> di **Threat Management** \> .</span><span class="sxs-lookup"><span data-stu-id="34fa6-116">In the Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span> <span data-ttu-id="34fa6-117">È anche possibile passare direttamente a [https://protection.office.com/quarantine](https://protection.office.com/quarantine).</span><span class="sxs-lookup"><span data-stu-id="34fa6-117">(You can also go directly to [https://protection.office.com/quarantine](https://protection.office.com/quarantine).)</span></span>
    
2. <span data-ttu-id="34fa6-118">Nell'angolo in alto a sinistra, cambiare il menu a discesa dai **messaggi di posta elettronica** ai **file**.</span><span class="sxs-lookup"><span data-stu-id="34fa6-118">In the upper left corner, change the drop-down menu from **Emails** to **Files**.</span></span> <span data-ttu-id="34fa6-119">Se l'elenco dei risultati include troppi elementi, utilizzare la funzionalità di **filtro** per restringere la selezione.</span><span class="sxs-lookup"><span data-stu-id="34fa6-119">If the list of results includes too many items, use the **Filter** functionality to narrow down the selection.</span></span>
    
3. <span data-ttu-id="34fa6-120">Selezionare un elemento nell'elenco per visualizzare informazioni dettagliate, incluso l'URL del file.</span><span class="sxs-lookup"><span data-stu-id="34fa6-120">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="34fa6-121">Scegliere un'azione disponibile.</span><span class="sxs-lookup"><span data-stu-id="34fa6-121">Choose an available action.</span></span>
    
    - <span data-ttu-id="34fa6-122">Scegliere **Release file** per sbloccare il file.</span><span class="sxs-lookup"><span data-stu-id="34fa6-122">Choose **Release file** to unblock the file.</span></span> 

      <span data-ttu-id="34fa6-123">Selezionare **Invia rapporto a Microsoft** per segnalare il file come falso positivo a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34fa6-123">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 

    - <span data-ttu-id="34fa6-124">Scegliere **Download file** per analizzare ulteriormente il file.</span><span class="sxs-lookup"><span data-stu-id="34fa6-124">Choose **Download file** to investigate the file further.</span></span> 

    - <span data-ttu-id="34fa6-125">Scegliere **Rimuovi dalla quarantena** per rimuovere il file dall'elenco degli elementi in quarantena.</span><span class="sxs-lookup"><span data-stu-id="34fa6-125">Choose **Remove from quarantine** to remove the file from the list of quarantined items.</span></span> <span data-ttu-id="34fa6-126">Se si sceglie questa opzione, è necessario eliminare anche il file dalla rispettiva raccolta in SharePoint Online, OneDrive for business o Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="34fa6-126">If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="34fa6-127">Questa opzione non sblocca un file dall'apertura o dalla condivisione.</span><span class="sxs-lookup"><span data-stu-id="34fa6-127">This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="34fa6-128">Fare clic su **Chiudi** per chiudere i dettagli per un elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="34fa6-128">Choose **Close** to close the details for a selected item.</span></span> 
  
  

