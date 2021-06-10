---
title: Gestire SharePoint gruppi del sito di SharePoint Online con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: In questo articolo, trovare le procedure per l'utilizzo di PowerShell per Microsoft 365 gestire i gruppi del sito SharePoint Online.
ms.openlocfilehash: bcc7a00a6114a6fa2ba8aa02520267bd03a0abf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909539"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="7ef5c-103">Gestire SharePoint gruppi del sito di SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ef5c-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="7ef5c-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7ef5c-105">Sebbene sia possibile utilizzare l'interfaccia Microsoft 365 di amministrazione, è anche possibile usare PowerShell per Microsoft 365 per gestire i gruppi del sito SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7ef5c-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7ef5c-106">Before you begin</span></span>

<span data-ttu-id="7ef5c-107">Le procedure descritte in questo articolo richiedono la connessione a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="7ef5c-108">Per istruzioni, [vedere Connessione to SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="7ef5c-108">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="7ef5c-109">Visualizzare SharePoint Online con PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7ef5c-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="7ef5c-110">L'SharePoint di amministrazione di SharePoint Online include alcuni metodi di facile utilizzo per la gestione dei gruppi del sito.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="7ef5c-111">Si supponga, ad esempio, di voler esaminare i gruppi e i membri del gruppo per il `https://litwareinc.sharepoint.com/sites/finance` sito.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="7ef5c-112">Ecco cosa devi fare per:</span><span class="sxs-lookup"><span data-stu-id="7ef5c-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="7ef5c-113">Nell'SharePoint di amministrazione fare clic su **Siti attivi** e quindi sull'URL del sito.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="7ef5c-114">Nella pagina del sito fare clic **sull'icona Impostazioni** visualizzata nell'angolo superiore destro della pagina e quindi fare clic su **Autorizzazioni sito.**</span><span class="sxs-lookup"><span data-stu-id="7ef5c-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="7ef5c-115">Ripetere quindi la procedura per il sito successivo.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="7ef5c-116">Per ottenere un elenco dei gruppi con PowerShell per Microsoft 365, è possibile utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ef5c-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

<span data-ttu-id="7ef5c-117">Esistono due modi per eseguire questo set di comandi nel prompt dei comandi di SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="7ef5c-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="7ef5c-118">Copiare i comandi in Blocco note (o in un altro editor di testo), modificare il valore della variabile **$siteURL,** selezionare i comandi e quindi incollarli nel prompt dei comandi di SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="7ef5c-119">In questo caso, PowerShell verrà interrotta in un **>>** prompt.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="7ef5c-120">Premere INVIO per eseguire il `foreach` comando.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="7ef5c-121">Copiare i comandi in Blocco note (o in un altro editor di testo), modificare il valore della variabile **$siteURL** e quindi salvare il file di testo con un nome e l'estensione .ps1 in una cartella appropriata.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="7ef5c-122">Eseguire quindi lo script dal prompt dei comandi di SharePoint Online Management Shell specificandone il percorso e il nome file.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="7ef5c-123">Ecco un esempio di comando:</span><span class="sxs-lookup"><span data-stu-id="7ef5c-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="7ef5c-124">In entrambi i casi dovrebbe essere visualizzato un elemento simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7ef5c-124">In both cases, you should see something similar to this:</span></span>

![SharePoint Gruppi del sito online](../media/SPO-site-groups.png)

<span data-ttu-id="7ef5c-126">Si tratta di tutti i gruppi creati per il sito e `https://litwareinc.sharepoint.com/sites/finance` di tutti gli utenti assegnati a tali gruppi.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="7ef5c-127">I nomi dei gruppi sono in giallo per separare i nomi dei gruppi dai relativi membri.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="7ef5c-128">Come altro esempio, ecco un set di comandi che elenca i gruppi e tutte le appartenenze ai gruppi per tutti i siti SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7ef5c-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title 
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```
    
## <a name="see-also"></a><span data-ttu-id="7ef5c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ef5c-129">See also</span></span>

[<span data-ttu-id="7ef5c-130">Connettersi a PowerShell per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7ef5c-130">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="7ef5c-131">Creare SharePoint online e aggiungere utenti con PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ef5c-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="7ef5c-132">Gestire SharePoint utenti e gruppi di SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ef5c-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="7ef5c-133">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ef5c-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7ef5c-134">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7ef5c-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)