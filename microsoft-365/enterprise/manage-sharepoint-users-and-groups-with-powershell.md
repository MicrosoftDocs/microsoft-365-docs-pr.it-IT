---
title: Gestire utenti e gruppi di SharePoint Online con PowerShell
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
description: In questo articolo viene illustrato come usare PowerShell per Microsoft 365 per gestire utenti, gruppi e siti di SharePoint Online.
ms.openlocfilehash: 5252ecc950e5f26d6ad60cd871910a67bf50f187
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691409"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>Gestire utenti e gruppi di SharePoint Online con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Gli amministratori di SharePoint Online che lavorano con elenchi di grandi dimensioni di account utente o gruppi e desiderano un modo più semplice per gestirli, possono usare PowerShell per Microsoft 365. 

Prima di iniziare, le procedure descritte in questo argomento richiedono la connessione a SharePoint Online. Per istruzioni, vedere [Connettersi a PowerShell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="get-a-list-of-sites-groups-and-users"></a>Ottenere un elenco di siti, gruppi e utenti

Prima di iniziare a gestire utenti e gruppi, è necessario ottenere elenchi di siti, gruppi e utenti. È quindi possibile utilizzare queste informazioni per eseguire l'esempio in questo articolo.

Ottenere un elenco dei siti nel tenant con questo comando:

```powershell
Get-SPOSite
```

Ottenere un elenco dei gruppi nel tenant con questo comando:

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

Ottenere un elenco degli utenti nel tenant con questo comando:

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>Aggiungere un utente al gruppo Amministratori raccolta siti

Utilizzare il `Set-SPOUser` cmdlet per aggiungere un utente all'elenco degli amministratori della raccolta siti in una raccolta siti.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Per utilizzare questi comandi, sostituire tutti gli elementi racchiusi tra virgolette, inclusi i caratteri < e >, con i nomi corretti.

Ad esempio, questo set di comandi aggiunge Opal Castillo (nome utente opalc) all'elenco degli amministratori della raccolta siti ContosoTest nel tenancy Contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

È possibile copiare e incollare questi comandi nel Blocco note, modificare i valori delle variabili per $tenant, $site e $user in valori effettivi dell'ambiente e quindi incollarli nella finestra di SharePoint Online Management Shell per eseguirli.

## <a name="add-a-user-to-other-site-collection-groups"></a>Aggiungere un utente ad altri gruppi di raccolte siti

In questa attività verrà utilizzato il cmdlet per aggiungere un utente `Add-SPOUser` a un gruppo di SharePoint in una raccolta siti.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Ad esempio, è possibile aggiungere Unifio Rife (nome utente tuttora esistente) al gruppo Auditors della raccolta siti ContosoTest nella tenancy contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Creare un gruppo di raccolte siti

Utilizzare il `New-SPOSiteGroup` cmdlet per creare un nuovo gruppo di SharePoint e aggiungerlo a una raccolta siti.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
Le proprietà del gruppo, ad esempio i livelli di autorizzazione, possono essere aggiornate in un secondo momento utilizzando il `Set-SPOSiteGroup` cmdlet.

Ad esempio, aggiungere il gruppo Auditors con autorizzazioni di sola visualizzazione alla raccolta siti contosotest nella tenancy contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Rimuovere gli utenti da un gruppo

A volte è necessario rimuovere un utente da un sito o anche da tutti i siti. Forse il dipendente passa da una divisione a un'altra o lascia l'azienda. Puoi farlo facilmente per un dipendente nell'interfaccia utente, ma questa operazione non è facile quando devi spostare una divisione completa da un sito a un altro.

Tuttavia, utilizzando SharePoint Online Management Shell e i file CSV, questa operazione è semplice e veloce. In questa attività verrà utilizzato il Windows PowerShell per rimuovere un utente da un gruppo di sicurezza della raccolta siti. Si userà quindi un file CSV e si rimuoveranno molti utenti da siti diversi. 

Il cmdlet "Remove-SPOUser" verrà utilizzato per rimuovere un singolo utente di Microsoft 365 da un gruppo di raccolte siti solo per visualizzare la sintassi dei comandi. Ecco l'aspetto della sintassi:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
Ad esempio, rimuovere Boby Overby dal gruppo Auditors della raccolta siti contosotest nella tenancy contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Supponiamo di voler rimuovere Boby da tutti i gruppi in cui si trova attualmente. Ecco come eseguire questa operazione:

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> Questo è solo un esempio. Non eseguire questo comando a meno che non sia effettivamente necessario rimuovere un utente da ogni gruppo, ad esempio se l'utente lascia la società.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Automatizzare la gestione di elenchi di utenti e gruppi di grandi dimensioni

Per aggiungere un numero elevato di account ai siti di SharePoint e assegnare loro le autorizzazioni, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365, i singoli comandi di PowerShell o PowerShell in un file CSV. Tra queste scelte, il file CSV è il modo più rapido per automatizzare questa attività.

Il processo di base è la creazione di un file CSV con intestazioni (colonne) corrispondenti ai parametri necessari per Windows PowerShell script. È possibile creare facilmente un elenco di questo tipo in Excel e quindi esportarlo come file CSV. Si utilizza quindi uno script Windows PowerShell per scorrere i record (righe) nel file CSV, aggiungendo gli utenti ai gruppi e i gruppi ai siti. 

Ad esempio, è possibile creare un file CSV per definire un gruppo di raccolte siti, gruppi e autorizzazioni. Successivamente, verrà creato un file CSV per popolare i gruppi con gli utenti. Infine, verrà creato ed eseguito un semplice script di Windows PowerShell che crea e popola i gruppi.

Il primo file CSV aggiungerà uno o più gruppi a una o più raccolte siti e avrà questa struttura:

Intestazione:

```powershell
Site,Group,PermissionLevels
```

Elemento:

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

Ecco un file di esempio:

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

Il secondo file CSV aggiungerà uno o più utenti a uno o più gruppi e avrà questa struttura:

Intestazione:

```powershell
Group,LoginName,Site
```

Elemento:

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

Ecco un file di esempio:

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

Per il passaggio successivo, è necessario salvare i due file CSV nell'unità. Ecco alcuni comandi di esempio che usano sia i file CSV che per aggiungere autorizzazioni e appartenenza ai gruppi:

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

Lo script importa il contenuto del file CSV e utilizza i valori nelle colonne per popolare i parametri dei **comandi New-SPOSiteGroup** e **Add-SPOUser.** In questo esempio, questa cartella viene salvata nella cartella O365Admin nell'unità C, ma è possibile salvarla ovunque si desideri.

A questo punto, rimuovere un gruppo di persone per diversi gruppi in siti diversi usando lo stesso file CSV. Ecco un esempio di comando:

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>Generare report utente

È possibile ottenere un semplice report per alcuni siti e visualizzare gli utenti per tali siti, il relativo livello di autorizzazione e altre proprietà. Ecco l'aspetto della sintassi:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

In questo modo, i dati per questi tre siti verranno catturati e scritto in un file di testo nell'unità locale. Si noti che il parametro –Append aggiungerà nuovo contenuto a un file esistente.

Ad esempio, è possibile eseguire un report sui siti ContosoTest, TeamSite01 e Project01 per il tenant Contoso1:

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Si noti che è stato necessario modificare solo **la $site** variabile. La **$tenant** mantiene il valore in tutte e tre le esecuzioni del comando.

Tuttavia, cosa succede se si desidera eseguire questa operazione per ogni sito? Puoi eseguire questa operazione senza dover digitare tutti i siti Web usando questo comando:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Questo report è piuttosto semplice ed è possibile aggiungere altro codice per creare report o report più specifici che includono informazioni più dettagliate. Tuttavia, questo dovrebbe fornire un'idea di come utilizzare SharePoint Online Management Shell per gestire gli utenti nell'ambiente SharePoint Online.
   
## <a name="see-also"></a>Vedere anche

[Connettersi a PowerShell per SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Gestire SharePoint Online con PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
