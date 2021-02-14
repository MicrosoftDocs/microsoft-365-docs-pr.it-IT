---
title: Gestire i gruppi del sito di SharePoint Online con PowerShell
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
description: In questo articolo sono disponibili le procedure per l'uso di PowerShell per Microsoft 365 per gestire i gruppi di siti di SharePoint Online.
ms.openlocfilehash: fa9aff769ff84f8567c45b20c7b6c8a078b4a70c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691412"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="35cdd-103">Gestire i gruppi del sito di SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="35cdd-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="35cdd-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="35cdd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="35cdd-105">Anche se è possibile usare l'interfaccia di amministrazione di Microsoft 365, è anche possibile usare PowerShell per Microsoft 365 per gestire i gruppi di siti di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="35cdd-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="35cdd-106">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="35cdd-106">Before you begin</span></span>

<span data-ttu-id="35cdd-107">Le procedure descritte in questo articolo richiedono la connessione a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="35cdd-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="35cdd-108">Per istruzioni, vedere [Connettersi a PowerShell di SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="35cdd-108">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="35cdd-109">Visualizzare SharePoint Online con PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35cdd-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="35cdd-110">L'interfaccia di amministrazione di SharePoint Online include alcuni metodi di facile utilizzo per la gestione dei gruppi del sito.</span><span class="sxs-lookup"><span data-stu-id="35cdd-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="35cdd-111">Si supponga, ad esempio, di voler esaminare i gruppi e i membri del gruppo per il `https://litwareinc.sharepoint.com/sites/finance` sito.</span><span class="sxs-lookup"><span data-stu-id="35cdd-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="35cdd-112">Ecco cosa devi fare per:</span><span class="sxs-lookup"><span data-stu-id="35cdd-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="35cdd-113">Nell'interfaccia di amministrazione di SharePoint fare clic **su Siti attivi** e quindi sull'URL del sito.</span><span class="sxs-lookup"><span data-stu-id="35cdd-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="35cdd-114">Nella pagina del sito  fare clic sull'icona Impostazioni nell'angolo superiore destro della pagina e quindi fare clic su **Autorizzazioni sito.**</span><span class="sxs-lookup"><span data-stu-id="35cdd-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="35cdd-115">Ripetere quindi la procedura per il sito successivo.</span><span class="sxs-lookup"><span data-stu-id="35cdd-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="35cdd-116">Per ottenere un elenco dei gruppi con PowerShell per Microsoft 365, è possibile utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="35cdd-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

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

<span data-ttu-id="35cdd-117">Esistono due modi per eseguire questo set di comandi nel prompt dei comandi di SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="35cdd-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="35cdd-118">Copiare i comandi nel Blocco note (o in un altro editor di testo), modificare il valore della variabile **$siteURL,** selezionare i comandi e incollarli nel prompt dei comandi di SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="35cdd-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="35cdd-119">In questo caso, PowerShell verrà interrotta in un **>>** prompt.</span><span class="sxs-lookup"><span data-stu-id="35cdd-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="35cdd-120">Premere INVIO per eseguire il `foreach` comando.</span><span class="sxs-lookup"><span data-stu-id="35cdd-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="35cdd-121">Copiare i comandi nel Blocco note (o in un altro editor di testo), modificare il valore della variabile **$siteURL** e quindi salvare il file di testo con un nome e l'estensione ps1 in una cartella appropriata.</span><span class="sxs-lookup"><span data-stu-id="35cdd-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="35cdd-122">Successivamente, eseguire lo script dal prompt dei comandi di SharePoint Online Management Shell specificandone il percorso e il nome file.</span><span class="sxs-lookup"><span data-stu-id="35cdd-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="35cdd-123">Ecco un esempio di comando:</span><span class="sxs-lookup"><span data-stu-id="35cdd-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="35cdd-124">In entrambi i casi dovrebbe essere visualizzato un elemento simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="35cdd-124">In both cases, you should see something similar to this:</span></span>

![Gruppi del sito di SharePoint Online](../media/SPO-site-groups.png)

<span data-ttu-id="35cdd-126">Si tratta di tutti i gruppi creati per il sito e `https://litwareinc.sharepoint.com/sites/finance` di tutti gli utenti assegnati a tali gruppi.</span><span class="sxs-lookup"><span data-stu-id="35cdd-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="35cdd-127">I nomi dei gruppi sono in giallo per separare i nomi dei gruppi dai relativi membri.</span><span class="sxs-lookup"><span data-stu-id="35cdd-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="35cdd-128">Di seguito è riportato un set di comandi in cui sono elencati i gruppi e tutte le appartenenze ai gruppi per tutti i siti di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="35cdd-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

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
    
## <a name="see-also"></a><span data-ttu-id="35cdd-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35cdd-129">See also</span></span>

[<span data-ttu-id="35cdd-130">Connettersi a PowerShell per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="35cdd-130">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="35cdd-131">Creare siti di SharePoint Online e aggiungere utenti con PowerShell</span><span class="sxs-lookup"><span data-stu-id="35cdd-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="35cdd-132">Gestire utenti e gruppi di SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="35cdd-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="35cdd-133">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="35cdd-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="35cdd-134">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35cdd-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

