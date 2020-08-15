---
title: Gestire gli utenti e i gruppi di SharePoint Online con PowerShell
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
description: In questo articolo vengono fornite informazioni su come utilizzare PowerShell per Microsoft 365 per gestire gli utenti, i gruppi e i siti di SharePoint Online.
ms.openlocfilehash: 5252ecc950e5f26d6ad60cd871910a67bf50f187
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691409"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a><span data-ttu-id="5d963-103">Gestire gli utenti e i gruppi di SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d963-103">Manage SharePoint Online users and groups with PowerShell</span></span>

<span data-ttu-id="5d963-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5d963-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5d963-105">Se si è un amministratore di SharePoint Online che lavora con elenchi di grandi dimensioni degli account utente o dei gruppi e che si desidera gestire in modo più semplice, è possibile utilizzare PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5d963-105">If you are a SharePoint Online administrator who works with large lists of user accounts or groups and wants an easier way to manage them, you can use PowerShell for Microsoft 365.</span></span> 

<span data-ttu-id="5d963-106">Prima di iniziare, le procedure descritte in questo argomento richiedono la connessione a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5d963-106">Before you begin, the procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="5d963-107">Per istruzioni, vedere [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="5d963-107">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="get-a-list-of-sites-groups-and-users"></a><span data-ttu-id="5d963-108">Ottenere un elenco di siti, gruppi e utenti</span><span class="sxs-lookup"><span data-stu-id="5d963-108">Get a list of sites, groups, and users</span></span>

<span data-ttu-id="5d963-109">Prima di iniziare a gestire utenti e gruppi, è necessario ottenere elenchi di siti, gruppi e utenti.</span><span class="sxs-lookup"><span data-stu-id="5d963-109">Before we start to manage users and groups, you need to get lists of your sites, groups, and users.</span></span> <span data-ttu-id="5d963-110">È quindi possibile utilizzare queste informazioni per gestire l'esempio in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5d963-110">You can then use this information to work through the example in this article.</span></span>

<span data-ttu-id="5d963-111">Ottenere un elenco dei siti nel tenant con questo comando:</span><span class="sxs-lookup"><span data-stu-id="5d963-111">Get a list of the sites in your tenant with this command:</span></span>

```powershell
Get-SPOSite
```

<span data-ttu-id="5d963-112">Ottenere un elenco dei gruppi nel tenant con questo comando:</span><span class="sxs-lookup"><span data-stu-id="5d963-112">Get a list of the groups in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

<span data-ttu-id="5d963-113">Ottenere un elenco degli utenti nel tenant con questo comando:</span><span class="sxs-lookup"><span data-stu-id="5d963-113">Get a list of the users in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a><span data-ttu-id="5d963-114">Aggiungere un utente al gruppo Amministratori raccolta siti</span><span class="sxs-lookup"><span data-stu-id="5d963-114">Add a user to the Site Collection Administrators group</span></span>

<span data-ttu-id="5d963-115">È possibile utilizzare il `Set-SPOUser` cmdlet per aggiungere un utente all'elenco degli amministratori delle raccolte siti in una raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="5d963-115">You use the `Set-SPOUser` cmdlet to add a user to the list of Site Collection Administrators on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

<span data-ttu-id="5d963-116">Per utilizzare questi comandi, sostituire tutti gli elementi racchiusi tra virgolette, compresi i caratteri < e >, con i nomi corretti.</span><span class="sxs-lookup"><span data-stu-id="5d963-116">To use these commands, replace everything within the quotes, including the < and > characters, with the correct names.</span></span>

<span data-ttu-id="5d963-117">Ad esempio, questo set di comandi aggiunge Opal Castillo (nome utente opalc) all'elenco degli amministratori delle raccolte siti nella raccolta siti di ContosoTest nel contratto di locazione contoso:</span><span class="sxs-lookup"><span data-stu-id="5d963-117">For example, this set of commands adds Opal Castillo (user name opalc) to the list of Site Collection Administrators on the ContosoTest site collection in the Contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

<span data-ttu-id="5d963-118">È possibile copiare e incollare questi comandi nel blocco note, modificare i valori delle variabili per $tenant, $site e $user ai valori effettivi dell'ambiente e quindi incollarli nella finestra di SharePoint Online Management Shell per eseguirli.</span><span class="sxs-lookup"><span data-stu-id="5d963-118">You can copy and paste these commands into Notepad, change the variable values for $tenant, $site, and $user to actual values from your environment, and then paste this into your SharePoint Online Management Shell window to run them.</span></span>

## <a name="add-a-user-to-other-site-collection-groups"></a><span data-ttu-id="5d963-119">Aggiungere un utente ad altri gruppi di raccolte siti</span><span class="sxs-lookup"><span data-stu-id="5d963-119">Add a user to other site collection groups</span></span>

<span data-ttu-id="5d963-120">In questa attività verrà utilizzato il `Add-SPOUser` cmdlet per aggiungere un utente a un gruppo di SharePoint in una raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="5d963-120">In this task, we'll use the `Add-SPOUser` cmdlet to add a user to a SharePoint group on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

<span data-ttu-id="5d963-121">Ad esempio, aggiungere Glen prevalente (nome utente Glenr) al gruppo revisori nella raccolta siti di ContosoTest nel contratto di locazione contoso:</span><span class="sxs-lookup"><span data-stu-id="5d963-121">For example, let's add Glen Rife (user name glenr) to the Auditors group on the ContosoTest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a><span data-ttu-id="5d963-122">Creare un gruppo di raccolte siti</span><span class="sxs-lookup"><span data-stu-id="5d963-122">Create a site collection group</span></span>

<span data-ttu-id="5d963-123">È possibile utilizzare il `New-SPOSiteGroup` cmdlet per creare un nuovo gruppo di SharePoint e aggiungerlo a una raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="5d963-123">You use the `New-SPOSiteGroup` cmdlet to create a new SharePoint group and add it to a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
<span data-ttu-id="5d963-124">Le proprietà del gruppo, ad esempio i livelli di autorizzazione, possono essere aggiornate in un secondo momento utilizzando il `Set-SPOSiteGroup` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5d963-124">Group properties, such as permission levels, can be updated later by using the `Set-SPOSiteGroup` cmdlet.</span></span>

<span data-ttu-id="5d963-125">Ad esempio, aggiungere il gruppo revisori con autorizzazioni di sola visualizzazione per la raccolta siti di ContosoTest nel contratto di locazione contoso:</span><span class="sxs-lookup"><span data-stu-id="5d963-125">For example, let's add the Auditors group with View Only permissions to the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a><span data-ttu-id="5d963-126">Rimuovere gli utenti da un gruppo</span><span class="sxs-lookup"><span data-stu-id="5d963-126">Remove users from a group</span></span>

<span data-ttu-id="5d963-127">A volte è necessario rimuovere un utente da un sito o anche da tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="5d963-127">Sometimes you have to remove a user from a site or even all sites.</span></span> <span data-ttu-id="5d963-128">Forse il dipendente si sposta da una divisione all'altra oppure lascia l'azienda.</span><span class="sxs-lookup"><span data-stu-id="5d963-128">Perhaps the employee moves from one division to another or leaves the company.</span></span> <span data-ttu-id="5d963-129">Questa operazione può essere eseguita facilmente per un dipendente nell'interfaccia utente, ma non è possibile farlo facilmente quando è necessario spostare una divisione completa da un sito a un altro.</span><span class="sxs-lookup"><span data-stu-id="5d963-129">You can do this for one employee easily in the UI, but this is not easily done when you have to move a complete division from one site to another.</span></span>

<span data-ttu-id="5d963-130">Tuttavia, grazie a SharePoint Online Management Shell e ai file CSV, è semplice e veloce.</span><span class="sxs-lookup"><span data-stu-id="5d963-130">However by using the SharePoint Online Management Shell and CSV files, this is fast and easy.</span></span> <span data-ttu-id="5d963-131">In questa attività, è possibile utilizzare Windows PowerShell per rimuovere un utente da un gruppo di sicurezza della raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="5d963-131">In this task, you'll use Windows PowerShell to remove a user from a site collection security group.</span></span> <span data-ttu-id="5d963-132">Verrà quindi utilizzato un file CSV e verranno rimossi numerosi utenti provenienti da siti diversi.</span><span class="sxs-lookup"><span data-stu-id="5d963-132">Then you'll use a CSV file and remove lots of users from different sites.</span></span> 

<span data-ttu-id="5d963-133">Verrà utilizzato il cmdlet Remove-consorter per rimuovere un singolo utente di Microsoft 365 da un gruppo di raccolte siti in modo che sia possibile visualizzare la sintassi dei comandi.</span><span class="sxs-lookup"><span data-stu-id="5d963-133">We'll be using the 'Remove-SPOUser' cmdlet to remove a single Microsoft 365 user from a site collection group just so we can see the command syntax.</span></span> <span data-ttu-id="5d963-134">Ecco come appare la sintassi:</span><span class="sxs-lookup"><span data-stu-id="5d963-134">Here is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
<span data-ttu-id="5d963-135">Si supponga, ad esempio, di rimuovere Bobby statastirata dal gruppo revisori raccolta siti nella raccolta siti di ContosoTest nel contratto di locazione contoso:</span><span class="sxs-lookup"><span data-stu-id="5d963-135">For example, let's remove Bobby Overby from the site collection Auditors group in the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="5d963-136">Si supponga di voler rimuovere Bobby da tutti i gruppi a cui è attualmente associato.</span><span class="sxs-lookup"><span data-stu-id="5d963-136">Suppose we wanted to remove Bobby from all the groups he is currently in.</span></span> <span data-ttu-id="5d963-137">Di seguito viene descritto come eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d963-137">Here is how we would do that:</span></span>

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> <span data-ttu-id="5d963-138">Questo è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="5d963-138">This is just an example.</span></span> <span data-ttu-id="5d963-139">Non è consigliabile eseguire questo comando, a meno che non sia necessario rimuovere un utente da tutti i gruppi, ad esempio se l'utente lascia la società.</span><span class="sxs-lookup"><span data-stu-id="5d963-139">You should not run this command unless you really have to remove a user from every group, for example if the user leaves the company.</span></span>

## <a name="automate-management-of-large-lists-of-users-and-groups"></a><span data-ttu-id="5d963-140">Automatizzare la gestione di elenchi di utenti e gruppi di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="5d963-140">Automate management of large lists of users and groups</span></span>

<span data-ttu-id="5d963-141">Per aggiungere un numero elevato di account a siti di SharePoint e concedere loro le autorizzazioni, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365, i singoli comandi di PowerShell o un file CSV di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d963-141">To add a large number of accounts to SharePoint sites and give them permissions, you can use the Microsoft 365 admin center, individual PowerShell commands, or PowerShell an a CSV file.</span></span> <span data-ttu-id="5d963-142">Di queste opzioni, il file CSV è il modo più rapido per automatizzare questa attività.</span><span class="sxs-lookup"><span data-stu-id="5d963-142">Of these choices, the CSV file is the fastest way to automate this task.</span></span>

<span data-ttu-id="5d963-143">Il processo di base consiste nel creare un file CSV con intestazioni (colonne) corrispondenti ai parametri necessari per lo script di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d963-143">The basic process is to create a CSV file that has headers (columns) that correspond to the parameters that the Windows PowerShell script needs.</span></span> <span data-ttu-id="5d963-144">È possibile creare facilmente un elenco di questo tipo in Excel e quindi esportarlo come file CSV.</span><span class="sxs-lookup"><span data-stu-id="5d963-144">You can easily create such a list in Excel and then export it as a CSV file.</span></span> <span data-ttu-id="5d963-145">Successivamente, si utilizza uno script di Windows PowerShell per eseguire un'iterazione nei record (righe) nel file CSV, aggiungendo gli utenti ai gruppi e ai gruppi ai siti.</span><span class="sxs-lookup"><span data-stu-id="5d963-145">Then, you use a Windows PowerShell script to iterate through records (rows) in the CSV file, adding the users to groups and the groups to sites.</span></span> 

<span data-ttu-id="5d963-146">Si supponga, ad esempio, di creare un file CSV per definire un gruppo di raccolte siti, gruppi e autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5d963-146">For example, let's create a CSV file to define a group of site collections, groups, and permissions.</span></span> <span data-ttu-id="5d963-147">Successivamente, verrà creato un file CSV per popolare i gruppi con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5d963-147">Next, we will create a CSV file to populate the groups with users.</span></span> <span data-ttu-id="5d963-148">Infine, verrà creato ed eseguito un semplice script di Windows PowerShell che consente di creare e popolare i gruppi.</span><span class="sxs-lookup"><span data-stu-id="5d963-148">Finally, we will create and run a simple Windows PowerShell script that creates and populates the groups.</span></span>

<span data-ttu-id="5d963-149">Il primo file CSV aggiunge uno o più gruppi a una o più raccolte siti e avrà la seguente struttura:</span><span class="sxs-lookup"><span data-stu-id="5d963-149">The first CSV file will add one or more groups to one or more site collections and will have this structure:</span></span>

<span data-ttu-id="5d963-150">Intestazione</span><span class="sxs-lookup"><span data-stu-id="5d963-150">Header:</span></span>

```powershell
Site,Group,PermissionLevels
```

<span data-ttu-id="5d963-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d963-151">Item:</span></span>

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

<span data-ttu-id="5d963-152">Di seguito è riportato un file di esempio:</span><span class="sxs-lookup"><span data-stu-id="5d963-152">Here is an example file:</span></span>

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

<span data-ttu-id="5d963-153">Il secondo file CSV aggiunge uno o più utenti a uno o più gruppi e avrà la seguente struttura:</span><span class="sxs-lookup"><span data-stu-id="5d963-153">The second CSV file will add one or more users to one or more groups and will have this structure:</span></span>

<span data-ttu-id="5d963-154">Intestazione</span><span class="sxs-lookup"><span data-stu-id="5d963-154">Header:</span></span>

```powershell
Group,LoginName,Site
```

<span data-ttu-id="5d963-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d963-155">Item:</span></span>

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

<span data-ttu-id="5d963-156">Di seguito è riportato un file di esempio:</span><span class="sxs-lookup"><span data-stu-id="5d963-156">Here is an example file:</span></span>

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

<span data-ttu-id="5d963-157">Per il passaggio successivo, è necessario che i due file CSV siano stati salvati nell'unità.</span><span class="sxs-lookup"><span data-stu-id="5d963-157">For the next step, you must have the two CSV files saved to your drive.</span></span> <span data-ttu-id="5d963-158">Di seguito sono riportati i comandi di esempio che consentono di utilizzare entrambi i file CSV e di aggiungere autorizzazioni e appartenenza ai gruppi:</span><span class="sxs-lookup"><span data-stu-id="5d963-158">Here are example commands that use both CSV files and to add permissions and group membership:</span></span>

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

<span data-ttu-id="5d963-159">Lo script importa il contenuto del file CSV e utilizza i valori nelle colonne per popolare i parametri dei comandi **New-SPOSiteGroup** e **Add-consorter** .</span><span class="sxs-lookup"><span data-stu-id="5d963-159">The script imports the CSV file contents and uses the values in the columns to populate the parameters of the **New-SPOSiteGroup** and **Add-SPOUser** commands.</span></span> <span data-ttu-id="5d963-160">In questo esempio, viene salvata la cartella theO365Admin nell'unità C, ma è possibile salvarla dove si vuole.</span><span class="sxs-lookup"><span data-stu-id="5d963-160">In our example, we are saving this to theO365Admin folder on drive C, but you can save it wherever you want.</span></span>

<span data-ttu-id="5d963-161">A questo punto, è possibile rimuovere un gruppo di utenti per diversi gruppi in siti diversi utilizzando lo stesso file CSV.</span><span class="sxs-lookup"><span data-stu-id="5d963-161">Now, let's remove a bunch of people for several groups in different sites using the same CSV file.</span></span> <span data-ttu-id="5d963-162">Ecco un esempio di comando:</span><span class="sxs-lookup"><span data-stu-id="5d963-162">Here is an example command:</span></span>

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a><span data-ttu-id="5d963-163">Generare report utente</span><span class="sxs-lookup"><span data-stu-id="5d963-163">Generate user reports</span></span>

<span data-ttu-id="5d963-164">Potrebbe essere necessario ottenere un report semplice per alcuni siti e visualizzare gli utenti per tali siti, il livello di autorizzazione e altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="5d963-164">You might want to get a simple report for a few sites and display the users for those sites, their permission level, and other properties.</span></span> <span data-ttu-id="5d963-165">Ecco come appare la sintassi:</span><span class="sxs-lookup"><span data-stu-id="5d963-165">This is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="5d963-166">In questo modo i dati vengono afferrati per questi tre siti e vengono scritti in un file di testo nell'unità locale.</span><span class="sxs-lookup"><span data-stu-id="5d963-166">This will grab the data for these three sites and write them to a text file on your local drive.</span></span> <span data-ttu-id="5d963-167">Si noti che il parametro – Append aggiungerà nuovo contenuto a un file esistente.</span><span class="sxs-lookup"><span data-stu-id="5d963-167">Note that the parameter –Append will add new content to an existing file.</span></span>

<span data-ttu-id="5d963-168">Si supponga, ad esempio, di eseguire un report sui siti ContosoTest, TeamSite01 e Project01 per il tenant di Contoso1:</span><span class="sxs-lookup"><span data-stu-id="5d963-168">For example, let's run a report on the ContosoTest, TeamSite01, and Project01 sites for the Contoso1 tenant:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="5d963-169">Si noti che è stato necessario modificare solo la variabile **$site** .</span><span class="sxs-lookup"><span data-stu-id="5d963-169">Note that we had to change only the **$site** variable.</span></span> <span data-ttu-id="5d963-170">La variabile **$tenant** mantiene il suo valore tramite tutte e tre le esecuzioni del comando.</span><span class="sxs-lookup"><span data-stu-id="5d963-170">The **$tenant** variable keeps its value through all three runs of the command.</span></span>

<span data-ttu-id="5d963-171">Tuttavia, cosa succede se si desidera eseguire questa operazione per ogni sito?</span><span class="sxs-lookup"><span data-stu-id="5d963-171">However, what if you wanted to do this for every site?</span></span> <span data-ttu-id="5d963-172">È possibile eseguire questa operazione senza dover digitare tutti i siti Web utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5d963-172">You can do this without having to type all those websites by using this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="5d963-173">Questo report è piuttosto semplice ed è possibile aggiungere altro codice per creare report o report più specifici che includono informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="5d963-173">This report is fairly simple, and you can add more code to create more specific reports or reports that include more detailed information.</span></span> <span data-ttu-id="5d963-174">Tuttavia, questo dovrebbe fornire un'idea di come usare SharePoint Online Management Shell per gestire gli utenti nell'ambiente di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5d963-174">But this should give you an idea of how to use the SharePoint Online Management Shell to manage users in the SharePoint Online environment.</span></span>
   
## <a name="see-also"></a><span data-ttu-id="5d963-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d963-175">See also</span></span>

[<span data-ttu-id="5d963-176">Connettersi a PowerShell per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5d963-176">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="5d963-177">Gestire SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d963-177">Manage SharePoint Online with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="5d963-178">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d963-178">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5d963-179">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5d963-179">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
