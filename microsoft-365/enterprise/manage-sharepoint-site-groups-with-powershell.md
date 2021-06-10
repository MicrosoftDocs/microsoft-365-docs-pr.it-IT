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
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>Gestire SharePoint gruppi del sito di SharePoint Online con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Sebbene sia possibile utilizzare l'interfaccia Microsoft 365 di amministrazione, è anche possibile usare PowerShell per Microsoft 365 per gestire i gruppi del sito SharePoint Online.

## <a name="before-you-begin"></a>Prima di iniziare

Le procedure descritte in questo articolo richiedono la connessione a SharePoint Online. Per istruzioni, [vedere Connessione to SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Visualizzare SharePoint Online con PowerShell per Microsoft 365

L'SharePoint di amministrazione di SharePoint Online include alcuni metodi di facile utilizzo per la gestione dei gruppi del sito. Si supponga, ad esempio, di voler esaminare i gruppi e i membri del gruppo per il `https://litwareinc.sharepoint.com/sites/finance` sito. Ecco cosa devi fare per:

1. Nell'SharePoint di amministrazione fare clic su **Siti attivi** e quindi sull'URL del sito.
2. Nella pagina del sito fare clic **sull'icona Impostazioni** visualizzata nell'angolo superiore destro della pagina e quindi fare clic su **Autorizzazioni sito.**

Ripetere quindi la procedura per il sito successivo.

Per ottenere un elenco dei gruppi con PowerShell per Microsoft 365, è possibile utilizzare i comandi seguenti:

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

- Copiare i comandi in Blocco note (o in un altro editor di testo), modificare il valore della variabile **$siteURL,** selezionare i comandi e quindi incollarli nel prompt dei comandi di SharePoint Online Management Shell. In questo caso, PowerShell verrà interrotta in un **>>** prompt. Premere INVIO per eseguire il `foreach` comando.<br/>
- Copiare i comandi in Blocco note (o in un altro editor di testo), modificare il valore della variabile **$siteURL** e quindi salvare il file di testo con un nome e l'estensione .ps1 in una cartella appropriata. Eseguire quindi lo script dal prompt dei comandi di SharePoint Online Management Shell specificandone il percorso e il nome file. Ecco un esempio di comando:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

In entrambi i casi dovrebbe essere visualizzato un elemento simile al seguente:

![SharePoint Gruppi del sito online](../media/SPO-site-groups.png)

Si tratta di tutti i gruppi creati per il sito e `https://litwareinc.sharepoint.com/sites/finance` di tutti gli utenti assegnati a tali gruppi. I nomi dei gruppi sono in giallo per separare i nomi dei gruppi dai relativi membri.

Come altro esempio, ecco un set di comandi che elenca i gruppi e tutte le appartenenze ai gruppi per tutti i siti SharePoint Online.

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

[Connettersi a PowerShell per SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Creare SharePoint online e aggiungere utenti con PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Gestire SharePoint utenti e gruppi di SharePoint Online con PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)