---
title: Usare i cmdlet di PowerShell della distribuzione centralizzata per gestire i componenti aggiuntivi
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 94f4e86d-b8e5-42dd-b558-e6092f830ec9
ms.custom:
- seo-marvel-apr2020
description: Utilizzare i cmdlet di PowerShell per la distribuzione centralizzata per distribuire e gestire Office componenti aggiuntivi per l'Microsoft 365 organizzazione.
ms.openlocfilehash: 7872deedfcfe058f0a4ac63c489bbed139699d18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924673"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a>Usare i cmdlet di PowerShell della distribuzione centralizzata per gestire i componenti aggiuntivi

Come amministratore Microsoft 365 globale, è possibile distribuire Office componenti aggiuntivi agli utenti tramite la funzionalità distribuzione centralizzata (vedere Distribuire componenti aggiuntivi di Office nell'interfaccia di [amministrazione).](../admin/manage/manage-deployment-of-add-ins.md) Oltre a distribuire Office componenti aggiuntivi tramite l'Microsoft 365 di amministrazione, è anche possibile usare Microsoft PowerShell. Installare il modulo di distribuzione Add-In centralizzato [di O365 per Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment). 

Dopo aver scaricato il modulo, aprire una finestra Windows PowerShell ed eseguire il cmdlet seguente:

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a>Connessione le credenziali di amministratore

Prima di poter utilizzare i cmdlet per la distribuzione centralizzata, è necessario eseguire l'accesso.
  
1. Avviare PowerShell.
    
2. Connessione a PowerShell utilizzando le credenziali di amministratore dell'azienda. Eseguire il cmdlet seguente.
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. Nella pagina **Immetti credenziali** immettere le credenziali Microsoft 365 amministratore globale. In alternativa, è possibile immettere le credenziali direttamente nel cmdlet. 
    
    Eseguire il cmdlet seguente specificando le credenziali di amministratore aziendale come oggetto PSCredential.
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> Per ulteriori informazioni sull'uso di PowerShell, [vedere Connessione to Microsoft 365 with PowerShell](./connect-to-microsoft-365-powershell.md). 
  
## <a name="upload-an-add-in-manifest"></a>Upload manifesto di un componente aggiuntivo

Eseguire il cmdlet **New-OrganizationAdd-In** per caricare un manifesto del componente aggiuntivo da un percorso, che può essere un percorso di file o un URL. Nell'esempio seguente viene illustrato un percorso di file per il valore del _parametro ManifestPath._ 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

È inoltre possibile eseguire il cmdlet **New-OrganizationAdd-In** per caricare un componente aggiuntivo e assegnarlo direttamente a utenti o gruppi utilizzando il parametro  _Members,_ come illustrato nell'esempio seguente. Separare gli indirizzi di posta elettronica dei membri con una virgola. 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a>Upload un componente aggiuntivo da Office Store

Eseguire il cmdlet **New-OrganizationAddIn** per caricare un manifesto dall'Office Store.
  
Nell'esempio seguente, il cmdlet **New-OrganizationAddIn** specifica l'AssetId per un componente aggiuntivo per una posizione e un mercato del contenuto negli Stati Uniti.
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

Per determinare il valore del _parametro AssetId,_ puoi copiarlo dall'URL della pagina Web di Office Store per il componente aggiuntivo. AssetIds inizia sempre con "WA" seguito da un numero. Nell'esempio precedente, ad esempio, l'origine per il valore AssetId di WA104099688 è l'URL della pagina Web di Office Store per il componente aggiuntivo: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .
  
I valori per il  _parametro Locale_ e il parametro  _ContentMarket_ sono identici e indicano il paese/area geografica da cui si sta tentando di installare il componente aggiuntivo. Il formato è en-US, fr-FR. e così via. 
  
> [!NOTE]
> I componenti aggiuntivi caricati da Office Store verranno aggiornati automaticamente entro pochi giorni dalla disponibilità dell'aggiornamento più recente nel Office Store. 
  
## <a name="get-details-of-an-add-in"></a>Ottenere i dettagli di un componente aggiuntivo

Eseguire il cmdlet **Get-OrganizationAddIn** come illustrato di seguito per ottenere i dettagli di tutti i componenti aggiuntivi caricati nel tenant, incluso l'ID prodotto di un componente aggiuntivo.
  
```powershell
Get-OrganizationAddIn
```

Eseguire il cmdlet **Get-OrganizationAddIn** con un valore per il parametro  _ProductId_ per specificare il componente aggiuntivo per cui si desidera recuperare i dettagli. 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

Per ottenere tutti i dettagli di tutti i componenti aggiuntivi più gli utenti e i gruppi assegnati, eseguire il pipe dell'output del cmdlet **Get-OrganizationAddIn** al cmdlet Format-List, come illustrato nell'esempio seguente.
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a>Attivare o disattivare un componente aggiuntivo

Per disattivare un componente aggiuntivo in modo che gli utenti e i gruppi a esso assegnati non avranno più accesso, eseguire il cmdlet **Set-OrganizationAddIn** con il parametro  _ProductId_ e il parametro  _Enabled_ impostato su , come illustrato nell'esempio  `$false` seguente.
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

Per riattivare un componente aggiuntivo, eseguire lo stesso cmdlet con il  _parametro Enabled_ impostato su  `$true` .
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a>Aggiungere o rimuovere utenti da un componente aggiuntivo

Per aggiungere utenti e gruppi a un componente aggiuntivo specifico, eseguire il cmdlet **Set-OrganizationAddInAssignments** con i parametri _ProductId,_ _Add_ _e Members._ Separare gli indirizzi di posta elettronica dei membri con una virgola. 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Per rimuovere utenti e gruppi, eseguire lo stesso cmdlet utilizzando il _parametro Remove._ 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

Per assegnare un componente aggiuntivo a tutti gli utenti del tenant, eseguire lo stesso cmdlet utilizzando il  _parametro AssignToEveryone_ con il valore impostato su  `$true` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

Per non assegnare un componente aggiuntivo a tutti gli utenti e ripristinare gli utenti e i gruppi precedentemente assegnati, è possibile eseguire lo stesso cmdlet e disattivare il  _parametro AssignToEveryone_ impostandone il valore su  `$false` .
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a>Aggiornare un componente aggiuntivo

Per aggiornare un componente aggiuntivo da un manifesto, eseguire il cmdlet **Set-OrganizationAddIn** con i parametri  _ProductId,_  _ManifestPath_ e  _Locale,_ come illustrato nell'esempio seguente. 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> I componenti aggiuntivi caricati da Office Store verranno aggiornati automaticamente entro pochi giorni dalla disponibilità dell'aggiornamento più recente nel Office Store. 
  
## <a name="delete-an-add-in"></a>Eliminare un componente aggiuntivo

Per eliminare un componente aggiuntivo, eseguire il cmdlet **Remove-OrganizationAddIn** con il  _parametro ProductId,_ come illustrato nell'esempio seguente. 
  
```powershell
Remove-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<!--
## Customize Microsoft Store add-ins for your organization

You must customize the add-in before you deploy it to your organization. Add-ins older than version 1.1 are not supported by this feature. 

We recommend that you deploy a customized add-in  to yourself first to make sure it works as expected before you deploy it to your entire organization.

Note also the following restrictions:
- All URLs must be absolute (include http or https) and valid.
- *DisplayName* must not exceed 125 characters 
- *DisplayName*, *Resources* and *AppDomains* must not include the following characters: 
 
    - \<
    -  \>
    -  ;
    -  =   

If you want to customize an add-in that has been deployed, you have to uninstall it in the admin center, and see [remove an add-in from local cache](#remove-an-add-in-from-local-cache) for steps to remove it from each computer it has been deployed to.

To customize an add-in, run the **Set –OrganizationAddInOverrides** cmdlet with the *ProductId* as a parameter, followed by the tag you want to overwrite and the new value. To find out how to get the *ProductId* see [get details of an add-in](#get-details-of-an-add-in) in this article. For example:

```powershell
 Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -IconUrl "https://site.com/img.jpg" 
```
To customize multiple tags for an add-in, add those tags to the commandline:

```powershell
Set-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 -Hosts h1, 2 -DisplayName "New DocuSign W" -IconUrl "https://site.com/img.jpg" 
```

> [!IMPORTANT]
> You must apply multiple customized tags to one add-in as one command. If you customize tags one by one, only the last customization will be applied. Additionally, if you customize a tag by mistake, you must remove all customizations and start over.

### Tags you can customize

| Tag                  | Description          |
| :------------------- | :------------------- |
| \<IconURL>   </br>| The URL of the image used as the add-in’s icon (in admin center). </br> |
| \<DisplayName>| The title of the add-in  (in admin center).|
| \<Hosts>| List of apps that will support the add-in.|
| \<SourceLocation> | The source URL that the add-in will connect to.| 
| \<AppDomains> | A list of domains that the add-in can connect with. | 
| \<SupportURL>| The URL users can use to access help and support. | 
| \<Resources>  | This tag contains a number of elements including titles, tooltips, and icons of different sizes.| 
|
### Customize Resources tag

Any element in the <Resources> tag of the manifest can be customized dynamically. You first need to check the manifest to find the element id to which you want to assign a new value. The <Resources> tag looks like this:

```
<Resources>  
    <bt:Images> 
          <bt:Image id=”img16icon” DefaultValue=”https://site.com/img.jpg” 
    </bt:Images> 
</Resources> 
``` 
In this case, the element id for the image is “img16icon” and the value associated with it is “http:<i></i>//site.<i></i>com/img.jpg.”

Once you have identified the elements you want to customize, use the following command in Powershell to assign new values to the elements:

```powershell
Set-OrganizationAddInOverrides -Resources @{“ElementID” = “New Value”; “NextElementID” = “Next New Value”} 
```

You can customize as many elements with the command as you need to.

### Remove customization from an add-in

The only option currently available for deleting customizations is to delete all of them at once:

```powershell
Remove-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### View add-in customizations

To view a list of applied customizations, run the **Get-OrganizationAddInOverrides** cmdlet. If **Get-OrganizationAddInOverrides** is run without a *ProductId* then a list of all add-ins with applied overrides are returned.  

```powershell
Get-OrganizationAddInOverrides 
```
If ProductId is specified, then a list of overrides applied to that add-in is returned. 

```powershell
Get-OrganizationAddInOverrides -ProductId 5b31b349-2c41-4f94-b720-6ee40349d391 
```

### Remove an add-in from local cache

If an add-in has been deployed, it has to be removed from the cache in each computer before it can be customized. To remive an add-in from cache:

1. Navigate to the “Users” folder in C:\ 
1. Go to your user folder
1. Navigate to AppData\Local\Microsoft\Office and select the folder associated with your version of Office
1. In the *Wef* folder delete the *Manifests* folder.

-->

## <a name="get-detailed-help-for-each-cmdlet"></a>Ottenere informazioni dettagliate per ogni cmdlet

È possibile esaminare la Guida dettagliata per ogni cmdlet utilizzando il cmdlet Get-help. Ad esempio, il cmdlet seguente fornisce informazioni dettagliate sul cmdlet Remove-OrganizationAddIn.
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```