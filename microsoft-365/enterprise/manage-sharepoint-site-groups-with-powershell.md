---
title: Gestire i gruppi di siti di SharePoint Online con PowerShell
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
description: In questo articolo, trovare le procedure per l'utilizzo di PowerShell per Microsoft 365 per gestire i gruppi di siti di SharePoint Online.
ms.openlocfilehash: fa9aff769ff84f8567c45b20c7b6c8a078b4a70c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691412"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>Gestire i gruppi di siti di SharePoint Online con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Anche se è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365, è anche possibile utilizzare PowerShell per Microsoft 365 per gestire i gruppi di siti di SharePoint Online.

## <a name="before-you-begin"></a>Prima di iniziare

Le procedure descritte in questo articolo richiedono la connessione a SharePoint Online. Per istruzioni, vedere [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Visualizzazione di SharePoint Online con PowerShell per Microsoft 365

L'interfaccia di amministrazione di SharePoint Online offre alcuni metodi di facile utilizzo per la gestione dei gruppi di siti. Ad esempio, si supponga di voler esaminare i gruppi e i membri del gruppo per il `https://litwareinc.sharepoint.com/sites/finance` sito. Di seguito sono riportate le operazioni da eseguire per:

1. Dall'interfaccia di amministrazione di SharePoint, fare clic su **siti attivi**e quindi fare clic sull'URL del sito.
2. Nella pagina sito fare clic sull'icona **delle impostazioni** (nell'angolo in alto a destra della pagina) e quindi fare clic su **autorizzazioni sito**.

Ripetere quindi la procedura per il sito successivo.

Per ottenere un elenco dei gruppi con PowerShell per Microsoft 365, è possibile utilizzare i seguenti comandi:

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

Esistono due modi per eseguire questo set di comandi nel prompt dei comandi di SharePoint Online Management Shell:

- Copiare i comandi nel blocco note o in un altro editor di testo, modificare il valore della variabile **$SiteUrl** , selezionare i comandi e quindi incollarli nel prompt dei comandi di SharePoint Online Management Shell. Quando si esegue questa operazione, PowerShell si arresterà al **>>** prompt. Premere INVIO per eseguire il `foreach` comando.<br/>
- Copiare i comandi nel blocco note o in un altro editor di testo, modificare il valore della variabile **$SiteUrl** e quindi salvare il file di testo con un nome e l'estensione ps1 in una cartella adatta. Successivamente, eseguire lo script dal prompt dei comandi di SharePoint Online Management Shell specificando il percorso e il nome del file. Ecco un esempio di comando:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

In entrambi i casi, dovrebbe essere visualizzato qualcosa di simile al seguente:

![Gruppi di siti di SharePoint Online](../media/SPO-site-groups.png)

Questi sono tutti i gruppi che sono stati creati per il sito `https://litwareinc.sharepoint.com/sites/finance` e tutti gli utenti assegnati a tali gruppi. I nomi dei gruppi sono in giallo che consentono di separare i nomi dei gruppi dai rispettivi membri.

Un altro esempio è un set di comandi che elenca i gruppi e tutte le appartenenze a gruppi per tutti i siti di SharePoint Online.

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
    
## <a name="see-also"></a>Vedere anche

[Connettersi a PowerShell per SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Creare siti di SharePoint Online e aggiungere utenti con PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Gestire gli utenti e i gruppi di SharePoint Online con PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)

