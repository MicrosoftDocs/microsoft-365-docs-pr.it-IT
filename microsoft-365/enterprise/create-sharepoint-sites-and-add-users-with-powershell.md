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
ms.openlocfilehash: 0c363df3edd40d810a0d8ca63090c0fec4c1c155
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288660"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Creare SharePoint online e aggiungere utenti con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Quando si utilizza PowerShell per Microsoft 365 per creare siti di SharePoint Online e aggiungere utenti, è possibile eseguire rapidamente e ripetutamente attività molto più velocemente di quanto sia possibile nella interfaccia di amministrazione di Microsoft 365. È inoltre possibile eseguire attività che non è possibile eseguire nella interfaccia di amministrazione di Microsoft 365.

## <a name="connect-to-sharepoint-online"></a>Connessione a SharePoint Online

Le procedure descritte in questo argomento richiedono la connessione a SharePoint Online. Per istruzioni, vedere [Connessione to SharePoint PowerShell online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="step-1-create-new-site-collections-using-powershell"></a>Passaggio 1: Creare nuove raccolte siti tramite PowerShell

Creare più siti con PowerShell e un file .csv creato utilizzando il codice di esempio fornito e Blocco note. Per questa procedura, l'utente dovrà sostituire le informazioni del segnaposto tra parentesi con quelle specifiche del proprio sito e tenant. Questo processo consente di creare un singolo file ed eseguire un singolo comando di PowerShell che usa tale file. Ciò rende le azioni intraprese ripetibili e portatili ed elimina molti, se non tutti, gli errori che possono provenire dal digitare lunghi comandi in SharePoint Online Management Shell. La procedura è divisa in due parti. Prima di tutto si creerà un file .csv e quindi si farà riferimento .csv file usando PowerShell, che utilizzerà il relativo contenuto per creare i siti.

Il cmdlet PowerShell importa il file .csv e lo esegue tramite pipe in un ciclo all'interno delle parentesi graffe che leggono la prima riga del file come intestazioni di colonna. Il cmdlet PowerShell quindi scorre i record rimanenti, crea una nuova raccolta siti per ogni record e assegna le proprietà della raccolta siti in base alle intestazioni di colonna.

### <a name="create-a-csv-file"></a>Creare un file .csv

> [!NOTE]
> Il parametro quota delle risorse funziona solo nei siti classici. Se si utilizza questo parametro in un sito moderno, è possibile che venga visualizzato un messaggio di avviso che indica che è stato deprecato.

1. Aprire Blocco note e incollare il seguente blocco di testo:

   ```powershell
   Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
   owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
   owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
   ```

   Dove *tenant* è il nome del tenant e *proprietario* è il nome utente dell'utente nel tenant a cui si desidera concedere il ruolo di amministratore principale della raccolta siti.

   È possibile premere CTRL+H quando si utilizza Blocco note sostituzione in blocco più velocemente.

2. Salvare il file sul desktop **comeSiteCollections.csv**.

> [!TIP]
> Prima di utilizzare questo o qualsiasi altro file di script .csv o Windows PowerShell, è consigliabile verificare che non siano presenti caratteri estranei o non stampabili. Aprire il file in Word e, nella barra multifunzione, fare clic sull'icona del paragrafo per mostrare i caratteri non stampabili. Non dovrebbero esserci caratteri estranei non stampabili. Ad esempio, non dovrebbe esserci alcun segno di paragrafo oltre quello finale alla fine del file.

### <a name="run-the-windows-powershell-command"></a>Eseguire il comando di Windows PowerShell:

1. Al prompt Windows PowerShell digitare oppure copiare e incollare il comando seguente e premere INVIO:

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
   ```

   Dove *MyAlias* è uguale all'alias utente.

2. Attendere la Windows PowerShell di conferma. Potrebbe richiedere uno o due minuti.

3. Al prompt Windows PowerShell digitare oppure copiare e incollare il cmdlet seguente e premere INVIO:

   ```powershell
   Get-SPOSite -Detailed | Format-Table -AutoSize
   ```

4. Notare la nuova raccolta di siti nell'elenco. Utilizzando il file CSV di esempio, vengono mostrate le raccolte siti seguenti: **TeamSite01,** **Blog01,** **Project01** e **Community01**

Questo è tutto. Sono state create più raccolte siti utilizzando il file .csv creato e un singolo Windows PowerShell comando. L'utente è ora pronto a creare e assegnare utenti a questi siti.

## <a name="step-2-add-users-and-groups"></a>Passaggio 2: aggiungere utenti e gruppi

A questo punto verranno creati gli utenti che verranno poi aggiunti a un gruppo di raccolte di sit. Si utilizzerà un file .csv per caricare in massa nuovi gruppi e utenti.

Le procedure seguenti continuano a utilizzare i siti di esempio TeamSite01, Blog01, Project01 e Community01.

### <a name="create-csv-and-ps1-files"></a>Creare file .csv e .ps1

1. Aprire Blocco note e incollare il seguente blocco di testo:

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

   Dove *tenant* è uguale al nome del tenant.

2. Salvare il file sul desktop **comeGroupsAndPermissions.csv**.

3. Aprire una nuova istanza del blocco note e incollare il seguente blocco di testo:

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

   Dove *tenant* è uguale al nome del tenant e *nomeutente* è uguale al nome utente di un utente esistente.

4. Salvare il file sul desktop **comeUsers.csv**.

5. Aprire una nuova istanza del blocco note e incollare il seguente blocco di testo:

   ```powershell
   Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
   Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
   ```

   Dove MyAlias è uguale al nome utente dell'utente attualmente connesso.

6. Salvare il file sul desktop **comeUsersAndGroups.ps1**. Si tratta di uno script Windows PowerShell semplice.

L'utente è ora pronto a eseguire lo script UsersAndGroup.ps1 per aggiungere utenti e gruppi a più raccolte di siti.

### <a name="run-usersandgroupsps1-script"></a>Eseguire lo script UsersAndGroups.ps1

1. Tornare a SharePoint Online Management Shell.

2. Al prompt Windows PowerShell digitare oppure copiare e incollare la riga seguente e premere INVIO:

   ```powershell
   Set-ExecutionPolicy Bypass
   ```

3. Al prompt di conferma, premere **Y**.

4. Al prompt Windows PowerShell digitare oppure copiare e incollare quanto segue e premere INVIO:

   ```powershell
   c:\users\MyAlias\desktop\UsersAndGroups.ps1
   ```

   Dove *MyAlias* è uguale al nome utente.

5. Attendere che il prompt risponda prima di andare avanti. Verranno innanzitutto visualizzati i gruppi man mano che vengono creati. Poi verrà visualizzato l'elenco dei gruppi ripetuto man mano che vengono aggiunti gli utenti.

## <a name="see-also"></a>Vedere anche

[Connettersi a PowerShell per SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[Gestire SharePoint gruppi del sito di SharePoint Online con PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
