---
title: Creare SharePoint online e aggiungere utenti con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: 'Riepilogo: utilizzare PowerShell per creare nuovi siti SharePoint Online e quindi aggiungere utenti e gruppi a tali siti.'
ms.openlocfilehash: eb6c2817c8760ca222da8a7c2b14cbfcda4eb4b8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907619"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="cffed-103">Creare SharePoint online e aggiungere utenti con PowerShell</span><span class="sxs-lookup"><span data-stu-id="cffed-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="cffed-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="cffed-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cffed-105">Quando si utilizza PowerShell per Microsoft 365 per creare siti di SharePoint Online e aggiungere utenti, è possibile eseguire rapidamente e ripetutamente attività molto più velocemente di quanto sia possibile nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cffed-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cffed-106">È inoltre possibile eseguire attività che non è possibile eseguire nell'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="cffed-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="cffed-107">Connessione a SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cffed-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="cffed-108">Le procedure descritte in questo argomento richiedono la connessione a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cffed-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="cffed-109">Per istruzioni, vedere [Connessione to SharePoint PowerShell online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="cffed-109">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="cffed-110">Passaggio 1: Creare nuove raccolte siti tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="cffed-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="cffed-111">Creare più siti con PowerShell e un file .csv creato utilizzando il codice di esempio fornito e Blocco note.</span><span class="sxs-lookup"><span data-stu-id="cffed-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="cffed-112">Per questa procedura, l'utente dovrà sostituire le informazioni del segnaposto tra parentesi con quelle specifiche del proprio sito e tenant.</span><span class="sxs-lookup"><span data-stu-id="cffed-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="cffed-113">Questo processo consente di creare un singolo file ed eseguire un singolo comando di PowerShell che usa tale file.</span><span class="sxs-lookup"><span data-stu-id="cffed-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="cffed-114">Ciò rende le azioni intraprese ripetibili e portatili ed elimina molti, se non tutti, gli errori che possono provenire dal digitare lunghi comandi in SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cffed-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="cffed-115">La procedura è divisa in due parti.</span><span class="sxs-lookup"><span data-stu-id="cffed-115">There are two parts to this procedure.</span></span> <span data-ttu-id="cffed-116">Prima di tutto si creerà un file .csv e quindi si farà riferimento .csv file usando PowerShell, che utilizzerà il relativo contenuto per creare i siti.</span><span class="sxs-lookup"><span data-stu-id="cffed-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="cffed-117">Il cmdlet PowerShell importa il file .csv e lo esegue tramite pipe in un ciclo all'interno delle parentesi graffe che leggono la prima riga del file come intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="cffed-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="cffed-118">Il cmdlet PowerShell quindi scorre i record rimanenti, crea una nuova raccolta siti per ogni record e assegna le proprietà della raccolta siti in base alle intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="cffed-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="cffed-119">Creare un file .csv</span><span class="sxs-lookup"><span data-stu-id="cffed-119">Create a .csv file</span></span>

> [!NOTE]
> <span data-ttu-id="cffed-120">Il parametro quota delle risorse funziona solo nei siti classici.</span><span class="sxs-lookup"><span data-stu-id="cffed-120">The resource quota parameter works only on classic sites.</span></span> <span data-ttu-id="cffed-121">Se si utilizza questo parametro in un sito moderno, è possibile che venga visualizzato un messaggio di avviso che indica che è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="cffed-121">If you use this parameter on a modern site, you may receive a warning message that it has been deprecated.</span></span> 

1. <span data-ttu-id="cffed-122">Aprire Blocco note e incollare il seguente blocco di testo:</span><span class="sxs-lookup"><span data-stu-id="cffed-122">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="cffed-123">Dove *tenant* è il nome del tenant e *proprietario* è il nome utente dell'utente nel tenant a cui si desidera concedere il ruolo di amministratore principale della raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="cffed-123">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="cffed-124">È possibile premere CTRL+H quando si utilizza Blocco note sostituzione in blocco più velocemente.</span><span class="sxs-lookup"><span data-stu-id="cffed-124">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="cffed-125">Salvare il file sul desktop **comeSiteCollections.csv**.</span><span class="sxs-lookup"><span data-stu-id="cffed-125">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="cffed-126">Prima di utilizzare questo o qualsiasi altro file di script .csv o Windows PowerShell, è consigliabile verificare che non siano presenti caratteri estranei o non stampabili.</span><span class="sxs-lookup"><span data-stu-id="cffed-126">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="cffed-127">Aprire il file in Word e, nella barra multifunzione, fare clic sull'icona del paragrafo per mostrare i caratteri non stampabili.</span><span class="sxs-lookup"><span data-stu-id="cffed-127">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="cffed-128">Non dovrebbero esserci caratteri estranei non stampabili.</span><span class="sxs-lookup"><span data-stu-id="cffed-128">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="cffed-129">Ad esempio, non dovrebbe esserci alcun segno di paragrafo oltre quello finale alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="cffed-129">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="cffed-130">Eseguire il comando di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cffed-130">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="cffed-131">Al prompt Windows PowerShell digitare oppure copiare e incollare il comando seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="cffed-131">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="cffed-132">Dove *MyAlias* è uguale all'alias utente.</span><span class="sxs-lookup"><span data-stu-id="cffed-132">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="cffed-133">Attendere la Windows PowerShell di conferma.</span><span class="sxs-lookup"><span data-stu-id="cffed-133">Wait for the Windows PowerShell prompt to reappear.</span></span> <span data-ttu-id="cffed-134">Potrebbe richiedere uno o due minuti.</span><span class="sxs-lookup"><span data-stu-id="cffed-134">It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="cffed-135">Al prompt Windows PowerShell digitare oppure copiare e incollare il cmdlet seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="cffed-135">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="cffed-136">Notare la nuova raccolta di siti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="cffed-136">Note the new site collections in the list.</span></span> <span data-ttu-id="cffed-137">Utilizzando il file CSV di esempio, vengono mostrate le raccolte siti seguenti: **TeamSite01,** **Blog01,** **Project01** e **Community01**</span><span class="sxs-lookup"><span data-stu-id="cffed-137">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="cffed-138">Questo è tutto.</span><span class="sxs-lookup"><span data-stu-id="cffed-138">That’s it.</span></span> <span data-ttu-id="cffed-139">Sono state create più raccolte siti utilizzando il file .csv creato e un singolo Windows PowerShell comando.</span><span class="sxs-lookup"><span data-stu-id="cffed-139">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="cffed-140">L'utente è ora pronto a creare e assegnare utenti a questi siti.</span><span class="sxs-lookup"><span data-stu-id="cffed-140">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="cffed-141">Passaggio 2: aggiungere utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="cffed-141">Step 2: Add users and groups</span></span>

<span data-ttu-id="cffed-p110">A questo punto verranno creati gli utenti che verranno poi aggiunti a un gruppo di raccolte di sit. Si utilizzerà un file .csv per caricare in massa nuovi gruppi e utenti.</span><span class="sxs-lookup"><span data-stu-id="cffed-p110">Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="cffed-144">Le procedure seguenti continuano a utilizzare i siti di esempio TeamSite01, Blog01, Project01 e Community01.</span><span class="sxs-lookup"><span data-stu-id="cffed-144">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="cffed-145">Creare file .csv e .ps1</span><span class="sxs-lookup"><span data-stu-id="cffed-145">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="cffed-146">Aprire Blocco note e incollare il seguente blocco di testo:</span><span class="sxs-lookup"><span data-stu-id="cffed-146">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Site,Group,PermissionLevels
https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```
<br/><span data-ttu-id="cffed-147">Dove *tenant* è uguale al nome del tenant.</span><span class="sxs-lookup"><span data-stu-id="cffed-147">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="cffed-148">Salvare il file sul desktop **comeGroupsAndPermissions.csv**.</span><span class="sxs-lookup"><span data-stu-id="cffed-148">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="cffed-149">Aprire una nuova istanza del blocco note e incollare il seguente blocco di testo:</span><span class="sxs-lookup"><span data-stu-id="cffed-149">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Group,LoginName,Site
Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
```
<br/><span data-ttu-id="cffed-150">Dove *tenant* è uguale al nome del tenant e *nomeutente* è uguale al nome utente di un utente esistente.</span><span class="sxs-lookup"><span data-stu-id="cffed-150">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="cffed-151">Salvare il file sul desktop **comeUsers.csv**.</span><span class="sxs-lookup"><span data-stu-id="cffed-151">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="cffed-152">Aprire una nuova istanza del blocco note e incollare il seguente blocco di testo:</span><span class="sxs-lookup"><span data-stu-id="cffed-152">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="cffed-153">Dove MyAlias è uguale al nome utente dell'utente attualmente connesso.</span><span class="sxs-lookup"><span data-stu-id="cffed-153">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="cffed-154">Salvare il file sul desktop **comeUsersAndGroups.ps1**.</span><span class="sxs-lookup"><span data-stu-id="cffed-154">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="cffed-155">Si tratta di uno script Windows PowerShell semplice.</span><span class="sxs-lookup"><span data-stu-id="cffed-155">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="cffed-156">L'utente è ora pronto a eseguire lo script UsersAndGroup.ps1 per aggiungere utenti e gruppi a più raccolte di siti.</span><span class="sxs-lookup"><span data-stu-id="cffed-156">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="cffed-157">Eseguire lo script UsersAndGroups.ps1</span><span class="sxs-lookup"><span data-stu-id="cffed-157">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="cffed-158">Tornare a SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cffed-158">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="cffed-159">Al prompt Windows PowerShell digitare oppure copiare e incollare la riga seguente e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="cffed-159">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="cffed-160">Al prompt di conferma, premere **Y**.</span><span class="sxs-lookup"><span data-stu-id="cffed-160">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="cffed-161">Al prompt Windows PowerShell digitare oppure copiare e incollare quanto segue e premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="cffed-161">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="cffed-162">Dove *MyAlias* è uguale al nome utente.</span><span class="sxs-lookup"><span data-stu-id="cffed-162">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="cffed-p112">Attendere che il prompt risponda prima di andare avanti. Verranno innanzitutto visualizzati i gruppi man mano che vengono creati. Poi verrà visualizzato l'elenco dei gruppi ripetuto man mano che vengono aggiunti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="cffed-p112">Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="cffed-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cffed-166">See also</span></span>

[<span data-ttu-id="cffed-167">Connettersi a PowerShell per SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cffed-167">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="cffed-168">Gestire SharePoint gruppi del sito di SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="cffed-168">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="cffed-169">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="cffed-169">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="cffed-170">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cffed-170">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)