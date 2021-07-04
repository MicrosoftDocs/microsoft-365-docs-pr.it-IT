---
title: Gestire SharePoint utenti e gruppi di SharePoint Online con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
description: In questo articolo viene illustrato come usare PowerShell per Microsoft 365 gestire SharePoint utenti, gruppi e siti di SharePoint Online.
ms.openlocfilehash: 823c5fdc9af178a2e8ea8f0ca4c63fbfa4673dd8
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289056"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a><span data-ttu-id="e8c3b-103">Gestire SharePoint utenti e gruppi di SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8c3b-103">Manage SharePoint Online users and groups with PowerShell</span></span>

<span data-ttu-id="e8c3b-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e8c3b-105">Se si è un amministratore di SharePoint Online che lavora con elenchi di grandi dimensioni di account utente o gruppi e desidera un modo più semplice per gestirli, è possibile utilizzare PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-105">If you are a SharePoint Online administrator who works with large lists of user accounts or groups and wants an easier way to manage them, you can use PowerShell for Microsoft 365.</span></span>

<span data-ttu-id="e8c3b-106">Prima di iniziare, le procedure descritte in questo argomento richiedono la connessione a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-106">Before you begin, the procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="e8c3b-107">Per istruzioni, vedere [Connessione to SharePoint PowerShell online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="e8c3b-107">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span></span>

## <a name="get-a-list-of-sites-groups-and-users"></a><span data-ttu-id="e8c3b-108">Ottenere un elenco di siti, gruppi e utenti</span><span class="sxs-lookup"><span data-stu-id="e8c3b-108">Get a list of sites, groups, and users</span></span>

<span data-ttu-id="e8c3b-109">Prima di iniziare a gestire utenti e gruppi, è necessario ottenere elenchi di siti, gruppi e utenti.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-109">Before we start to manage users and groups, you need to get lists of your sites, groups, and users.</span></span> <span data-ttu-id="e8c3b-110">È quindi possibile utilizzare queste informazioni per eseguire l'esempio in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-110">You can then use this information to work through the example in this article.</span></span>

<span data-ttu-id="e8c3b-111">Ottenere un elenco dei siti nel tenant con questo comando:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-111">Get a list of the sites in your tenant with this command:</span></span>

```powershell
Get-SPOSite
```

<span data-ttu-id="e8c3b-112">Ottieni un elenco dei gruppi nel tenant con questo comando:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-112">Get a list of the groups in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

<span data-ttu-id="e8c3b-113">Ottieni un elenco degli utenti nel tenant con questo comando:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-113">Get a list of the users in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a><span data-ttu-id="e8c3b-114">Aggiungere un utente al gruppo Amministratori raccolta siti</span><span class="sxs-lookup"><span data-stu-id="e8c3b-114">Add a user to the Site Collection Administrators group</span></span>

<span data-ttu-id="e8c3b-115">Utilizzare il `Set-SPOUser` cmdlet per aggiungere un utente all'elenco degli amministratori della raccolta siti in una raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-115">You use the `Set-SPOUser` cmdlet to add a user to the list of Site Collection Administrators on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

<span data-ttu-id="e8c3b-116">Per utilizzare questi comandi, sostituire tutti gli elementi racchiusi tra virgolette, inclusi i caratteri < e >, con i nomi corretti.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-116">To use these commands, replace everything within the quotes, including the < and > characters, with the correct names.</span></span>

<span data-ttu-id="e8c3b-117">Ad esempio, questo set di comandi aggiunge Opal Castillo (nome utente opalc) all'elenco degli amministratori della raccolta siti ContosoTest nella tenancy Contoso:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-117">For example, this set of commands adds Opal Castillo (user name opalc) to the list of Site Collection Administrators on the ContosoTest site collection in the Contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

<span data-ttu-id="e8c3b-118">È possibile copiare e incollare questi comandi in Blocco note, modificare i valori delle variabili per $tenant, $site e $user in valori effettivi dall'ambiente e quindi incollarli nella finestra di SharePoint Online Management Shell per eseguirli.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-118">You can copy and paste these commands into Notepad, change the variable values for $tenant, $site, and $user to actual values from your environment, and then paste this into your SharePoint Online Management Shell window to run them.</span></span>

## <a name="add-a-user-to-other-site-collection-groups"></a><span data-ttu-id="e8c3b-119">Aggiungere un utente ad altri gruppi di raccolte siti</span><span class="sxs-lookup"><span data-stu-id="e8c3b-119">Add a user to other site collection groups</span></span>

<span data-ttu-id="e8c3b-120">In questa attività verrà utilizzato il cmdlet per aggiungere un utente a un gruppo SharePoint `Add-SPOUser` in una raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-120">In this task, we'll use the `Add-SPOUser` cmdlet to add a user to a SharePoint group on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

<span data-ttu-id="e8c3b-121">Ad esempio, aggiungere Glen Rife (nome utente glenr) al gruppo Auditors nella raccolta siti ContosoTest nella tenancy contoso:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-121">For example, let's add Glen Rife (user name glenr) to the Auditors group on the ContosoTest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a><span data-ttu-id="e8c3b-122">Creare un gruppo di raccolte siti</span><span class="sxs-lookup"><span data-stu-id="e8c3b-122">Create a site collection group</span></span>

<span data-ttu-id="e8c3b-123">Utilizzare il `New-SPOSiteGroup` cmdlet per creare un nuovo SharePoint e aggiungerlo a una raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-123">You use the `New-SPOSiteGroup` cmdlet to create a new SharePoint group and add it to a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

<span data-ttu-id="e8c3b-124">Le proprietà del gruppo, ad esempio i livelli di autorizzazione, possono essere aggiornate in un secondo momento utilizzando il `Set-SPOSiteGroup` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-124">Group properties, such as permission levels, can be updated later by using the `Set-SPOSiteGroup` cmdlet.</span></span>

<span data-ttu-id="e8c3b-125">Ad esempio, aggiungere il gruppo Auditors con autorizzazioni di sola visualizzazione alla raccolta siti contosotest nella tenancy contoso:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-125">For example, let's add the Auditors group with View Only permissions to the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a><span data-ttu-id="e8c3b-126">Rimuovere gli utenti da un gruppo</span><span class="sxs-lookup"><span data-stu-id="e8c3b-126">Remove users from a group</span></span>

<span data-ttu-id="e8c3b-127">A volte è necessario rimuovere un utente da un sito o anche da tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-127">Sometimes you have to remove a user from a site or even all sites.</span></span> <span data-ttu-id="e8c3b-128">Forse il dipendente si sposta da una divisione a un'altra o lascia l'azienda.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-128">Perhaps the employee moves from one division to another or leaves the company.</span></span> <span data-ttu-id="e8c3b-129">Puoi farlo facilmente per un dipendente nell'interfaccia utente, ma non è facile quando devi spostare una divisione completa da un sito a un altro.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-129">You can do this for one employee easily in the UI, but this is not easily done when you have to move a complete division from one site to another.</span></span>

<span data-ttu-id="e8c3b-130">Tuttavia, utilizzando SharePoint Online Management Shell e i file CSV, questo è facile e veloce.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-130">However by using the SharePoint Online Management Shell and CSV files, this is fast and easy.</span></span> <span data-ttu-id="e8c3b-131">In questa attività verrà utilizzato il Windows PowerShell per rimuovere un utente da un gruppo di sicurezza della raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-131">In this task, you'll use Windows PowerShell to remove a user from a site collection security group.</span></span> <span data-ttu-id="e8c3b-132">Si userà quindi un file CSV e si rimuoveranno molti utenti da siti diversi.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-132">Then you'll use a CSV file and remove lots of users from different sites.</span></span>

<span data-ttu-id="e8c3b-133">Verrà utilizzato il cmdlet 'Remove-SPOUser' per rimuovere un singolo utente Microsoft 365 da un gruppo di raccolte siti solo per visualizzare la sintassi dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-133">We'll be using the 'Remove-SPOUser' cmdlet to remove a single Microsoft 365 user from a site collection group just so we can see the command syntax.</span></span> <span data-ttu-id="e8c3b-134">Ecco l'aspetto della sintassi:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-134">Here is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="e8c3b-135">Ad esempio, rimuovere Davide Overby dal gruppo Auditors della raccolta siti contosotest nella tenancy contoso:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-135">For example, let's remove Bobby Overby from the site collection Auditors group in the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="e8c3b-136">Supponiamo di voler rimuovere Davide da tutti i gruppi in cui si trova attualmente.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-136">Suppose we wanted to remove Bobby from all the groups he is currently in.</span></span> <span data-ttu-id="e8c3b-137">Ecco come procedere:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-137">Here is how we would do that:</span></span>

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> <span data-ttu-id="e8c3b-138">Questo è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-138">This is just an example.</span></span> <span data-ttu-id="e8c3b-139">Non è consigliabile eseguire questo comando a meno che non sia effettivamente necessario rimuovere un utente da ogni gruppo, ad esempio se l'utente lascia la società.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-139">You should not run this command unless you really have to remove a user from every group, for example if the user leaves the company.</span></span>

## <a name="automate-management-of-large-lists-of-users-and-groups"></a><span data-ttu-id="e8c3b-140">Automatizzare la gestione di elenchi di utenti e gruppi di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="e8c3b-140">Automate management of large lists of users and groups</span></span>

<span data-ttu-id="e8c3b-141">Per aggiungere un numero elevato di account SharePoint siti e assegnare loro le autorizzazioni, è possibile utilizzare il interfaccia di amministrazione di Microsoft 365, i singoli comandi di PowerShell o PowerShell in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-141">To add a large number of accounts to SharePoint sites and give them permissions, you can use the Microsoft 365 admin center, individual PowerShell commands, or PowerShell an a CSV file.</span></span> <span data-ttu-id="e8c3b-142">Di queste scelte, il file CSV è il modo più rapido per automatizzare questa attività.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-142">Of these choices, the CSV file is the fastest way to automate this task.</span></span>

<span data-ttu-id="e8c3b-143">Il processo di base è la creazione di un file CSV con intestazioni (colonne) corrispondenti ai parametri necessari Windows PowerShell script.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-143">The basic process is to create a CSV file that has headers (columns) that correspond to the parameters that the Windows PowerShell script needs.</span></span> <span data-ttu-id="e8c3b-144">Puoi creare facilmente un elenco di questo tipo in Excel e quindi esportarlo come file CSV.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-144">You can easily create such a list in Excel and then export it as a CSV file.</span></span> <span data-ttu-id="e8c3b-145">Quindi, si utilizza uno script Windows PowerShell per scorrere i record (righe) nel file CSV, aggiungendo gli utenti ai gruppi e i gruppi ai siti.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-145">Then, you use a Windows PowerShell script to iterate through records (rows) in the CSV file, adding the users to groups and the groups to sites.</span></span>

<span data-ttu-id="e8c3b-146">Ad esempio, è possibile creare un file CSV per definire un gruppo di raccolte siti, gruppi e autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-146">For example, let's create a CSV file to define a group of site collections, groups, and permissions.</span></span> <span data-ttu-id="e8c3b-147">Successivamente, creeremo un file CSV per popolare i gruppi con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-147">Next, we will create a CSV file to populate the groups with users.</span></span> <span data-ttu-id="e8c3b-148">Infine, verrà creato ed eseguito un semplice script Windows PowerShell che crea e popola i gruppi.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-148">Finally, we will create and run a simple Windows PowerShell script that creates and populates the groups.</span></span>

<span data-ttu-id="e8c3b-149">Il primo file CSV aggiungerà uno o più gruppi a una o più raccolte siti e avrà questa struttura:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-149">The first CSV file will add one or more groups to one or more site collections and will have this structure:</span></span>

<span data-ttu-id="e8c3b-150">Intestazione:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-150">Header:</span></span>

```powershell
Site,Group,PermissionLevels
```

<span data-ttu-id="e8c3b-151">Elemento:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-151">Item:</span></span>

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

<span data-ttu-id="e8c3b-152">Ecco un file di esempio:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-152">Here is an example file:</span></span>

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

<span data-ttu-id="e8c3b-153">Il secondo file CSV aggiungerà uno o più utenti a uno o più gruppi e avrà questa struttura:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-153">The second CSV file will add one or more users to one or more groups and will have this structure:</span></span>

<span data-ttu-id="e8c3b-154">Intestazione:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-154">Header:</span></span>

```powershell
Group,LoginName,Site
```

<span data-ttu-id="e8c3b-155">Elemento:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-155">Item:</span></span>

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

<span data-ttu-id="e8c3b-156">Ecco un file di esempio:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-156">Here is an example file:</span></span>

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

<span data-ttu-id="e8c3b-157">Per il passaggio successivo, è necessario salvare i due file CSV nell'unità.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-157">For the next step, you must have the two CSV files saved to your drive.</span></span> <span data-ttu-id="e8c3b-158">Ecco alcuni comandi di esempio che usano entrambi i file CSV e per aggiungere autorizzazioni e appartenenza ai gruppi:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-158">Here are example commands that use both CSV files and to add permissions and group membership:</span></span>

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

<span data-ttu-id="e8c3b-159">Lo script importa il contenuto del file CSV e utilizza i valori nelle colonne per popolare i parametri dei **comandi New-SPOSiteGroup** e **Add-SPOUser.**</span><span class="sxs-lookup"><span data-stu-id="e8c3b-159">The script imports the CSV file contents and uses the values in the columns to populate the parameters of the **New-SPOSiteGroup** and **Add-SPOUser** commands.</span></span> <span data-ttu-id="e8c3b-160">In questo esempio questa cartella viene salvata nella cartella O365Admin nell'unità C, ma è possibile salvarla ovunque si desideri.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-160">In our example, we are saving this to theO365Admin folder on drive C, but you can save it wherever you want.</span></span>

<span data-ttu-id="e8c3b-161">A questo punto, rimuoviamo un gruppo di persone per diversi gruppi in siti diversi usando lo stesso file CSV.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-161">Now, let's remove a bunch of people for several groups in different sites using the same CSV file.</span></span> <span data-ttu-id="e8c3b-162">Ecco un esempio di comando:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-162">Here is an example command:</span></span>

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a><span data-ttu-id="e8c3b-163">Generare report utente</span><span class="sxs-lookup"><span data-stu-id="e8c3b-163">Generate user reports</span></span>

<span data-ttu-id="e8c3b-164">È consigliabile ottenere un report semplice per alcuni siti e visualizzare gli utenti per tali siti, il relativo livello di autorizzazione e altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-164">You might want to get a simple report for a few sites and display the users for those sites, their permission level, and other properties.</span></span> <span data-ttu-id="e8c3b-165">Ecco l'aspetto della sintassi:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-165">This is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="e8c3b-166">In questo modo verranno afferrati i dati per questi tre siti e verranno scriviti in un file di testo nell'unità locale.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-166">This will grab the data for these three sites and write them to a text file on your local drive.</span></span> <span data-ttu-id="e8c3b-167">Si noti che il parametro –Append aggiungerà nuovo contenuto a un file esistente.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-167">Note that the parameter –Append will add new content to an existing file.</span></span>

<span data-ttu-id="e8c3b-168">Ad esempio, eseguire un report nei siti ContosoTest, TeamSite01 e Project01 per il tenant Contoso1:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-168">For example, let's run a report on the ContosoTest, TeamSite01, and Project01 sites for the Contoso1 tenant:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="e8c3b-169">Si noti che è stato necessario modificare solo **la $site** variabile.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-169">Note that we had to change only the **$site** variable.</span></span> <span data-ttu-id="e8c3b-170">La **$tenant** mantiene il relativo valore in tutte e tre le esecuzioni del comando.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-170">The **$tenant** variable keeps its value through all three runs of the command.</span></span>

<span data-ttu-id="e8c3b-171">Tuttavia, cosa succede se si desidera eseguire questa operazione per ogni sito?</span><span class="sxs-lookup"><span data-stu-id="e8c3b-171">However, what if you wanted to do this for every site?</span></span> <span data-ttu-id="e8c3b-172">È possibile eseguire questa operazione senza dover digitare tutti i siti Web utilizzando questo comando:</span><span class="sxs-lookup"><span data-stu-id="e8c3b-172">You can do this without having to type all those websites by using this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="e8c3b-173">Questo report è piuttosto semplice ed è possibile aggiungere altro codice per creare report o report più specifici che includono informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-173">This report is fairly simple, and you can add more code to create more specific reports or reports that include more detailed information.</span></span> <span data-ttu-id="e8c3b-174">Ma questo dovrebbe fornire un'idea di come usare SharePoint Online Management Shell per gestire gli utenti nell'ambiente SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e8c3b-174">But this should give you an idea of how to use the SharePoint Online Management Shell to manage users in the SharePoint Online environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8c3b-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8c3b-175">See also</span></span>

[<span data-ttu-id="e8c3b-176">Connettersi a PowerShell per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8c3b-176">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[<span data-ttu-id="e8c3b-177">Gestire SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8c3b-177">Manage SharePoint Online with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="e8c3b-178">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8c3b-178">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="e8c3b-179">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8c3b-179">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
