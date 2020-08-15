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
description: Utilizzare i cmdlet di PowerShell per la distribuzione centralizzata per facilitare la distribuzione e la gestione dei componenti aggiuntivi di Office per l'organizzazione Microsoft 365.
ms.openlocfilehash: 659f12d2533601c4b2165a95ddbf59ea521945b8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691441"
---
# <a name="use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins"></a><span data-ttu-id="25bb4-103">Usare i cmdlet di PowerShell della distribuzione centralizzata per gestire i componenti aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="25bb4-103">Use the Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>

<span data-ttu-id="25bb4-104">In qualità di amministratore globale di Microsoft 365, è possibile distribuire i componenti aggiuntivi di Office agli utenti tramite la caratteristica di distribuzione centralizzata (vedere [Deploy Office Add-ins in the Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)).</span><span class="sxs-lookup"><span data-stu-id="25bb4-104">As a Microsoft 365 global admin, you can deploy Office add-ins to users via the Centralized Deployment feature (see [Deploy Office Add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)).</span></span> <span data-ttu-id="25bb4-105">Oltre a distribuire i componenti aggiuntivi di Office tramite l'interfaccia di amministrazione di Microsoft 365, è anche possibile utilizzare Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25bb4-105">In addition to deploying Office add-ins via the Microsoft 365 admin center, you can also use Microsoft PowerShell.</span></span> <span data-ttu-id="25bb4-106">Installare il [modulo di distribuzione del componente aggiuntivo centralizzato di O365 per Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span><span class="sxs-lookup"><span data-stu-id="25bb4-106">Install the [O365 Centralized Add-In Deployment Module for Windows PowerShell](https://www.powershellgallery.com/packages/O365CentralizedAddInDeployment).</span></span> 

<span data-ttu-id="25bb4-107">Dopo aver scaricato il modulo, aprire una normale finestra di Windows PowerShell ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="25bb4-107">After you download the module, open a regular Windows PowerShell window and run the following cmdlet:</span></span>

```powershell
 Import-Module -Name O365CentralizedAddInDeployment
```
    
## <a name="connect-using-your-admin-credentials"></a><span data-ttu-id="25bb4-108">Connettersi utilizzando le credenziali di amministratore</span><span class="sxs-lookup"><span data-stu-id="25bb4-108">Connect using your admin credentials</span></span>

<span data-ttu-id="25bb4-109">Prima di poter utilizzare i cmdlet di distribuzione centralizzata, è necessario eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="25bb4-109">Before you can use the Centralized Deployment cmdlets, you need to sign in.</span></span>
  
1. <span data-ttu-id="25bb4-110">Avviare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25bb4-110">Start PowerShell.</span></span>
    
2. <span data-ttu-id="25bb4-111">Connettersi a PowerShell mediante le credenziali di amministratore della società.</span><span class="sxs-lookup"><span data-stu-id="25bb4-111">Connect to PowerShell by using your company admin credentials.</span></span> <span data-ttu-id="25bb4-112">Eseguire il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="25bb4-112">Run the following cmdlet.</span></span>
    
  ```powershell
  Connect-OrganizationAddInService
  ```

3. <span data-ttu-id="25bb4-113">Nella pagina **Enter credentials** immettere le credenziali di amministratore globale di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="25bb4-113">In the **Enter Credentials** page, enter your Microsoft 365 global admin credentials.</span></span> <span data-ttu-id="25bb4-114">In alternativa, è possibile immettere le credenziali direttamente nel cmdlet.</span><span class="sxs-lookup"><span data-stu-id="25bb4-114">Alternately, you can enter your credentials directly into the cmdlet.</span></span> 
    
    <span data-ttu-id="25bb4-115">Eseguire il cmdlet seguente specificando le credenziali di amministratore dell'azienda come oggetto PSCredential.</span><span class="sxs-lookup"><span data-stu-id="25bb4-115">Run the following cmdlet specifying your company admin credentials as a PSCredential object.</span></span>
    
  ```powershell
  $secpasswd = ConvertTo-SecureString "MyPassword" -AsPlainText -Force
  $mycredentials = New-Object System.Management.Automation.PSCredential ("serviceaccount@contoso.com", $secpasswd)
  Connect-OrganizationAddInService -Credential $mycredentials
  ```

> [!NOTE]
> <span data-ttu-id="25bb4-116">Per ulteriori informazioni sull'utilizzo di PowerShell, vedere [Connect to Microsoft 365 with PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span><span class="sxs-lookup"><span data-stu-id="25bb4-116">For more information about using PowerShell, see [Connect to Microsoft 365 with PowerShell](https://go.microsoft.com/fwlink/p/?linkid=848585).</span></span> 
  
## <a name="upload-an-add-in-manifest"></a><span data-ttu-id="25bb4-117">Caricare un manifesto del componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="25bb4-117">Upload an add-in manifest</span></span>

<span data-ttu-id="25bb4-118">Eseguire il cmdlet **New-organizzazionecomponenti-in** per caricare un manifesto del componente aggiuntivo da un percorso, che può essere un percorso o un URL di file.</span><span class="sxs-lookup"><span data-stu-id="25bb4-118">Run the **New-OrganizationAdd-In** cmdlet to upload an add-in manifest from a path, which can be either a file location or URL.</span></span> <span data-ttu-id="25bb4-119">Nell'esempio seguente viene illustrato un percorso di file per il valore del parametro  _ManifestPath_ .</span><span class="sxs-lookup"><span data-stu-id="25bb4-119">The following example shows a file location for the value of the  _ManifestPath_ parameter.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

<span data-ttu-id="25bb4-120">È inoltre possibile eseguire il cmdlet **New-organizzazionecomponenti-in** per caricare un componente aggiuntivo e assegnarlo direttamente agli utenti o ai gruppi tramite il parametro  _Members_ , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="25bb4-120">You can also run the **New-OrganizationAdd-In** cmdlet to upload an add-in and assign it to users or groups directly by using the  _Members_ parameter, as shown in the following example.</span></span> <span data-ttu-id="25bb4-121">Separare gli indirizzi di posta elettronica dei membri con una virgola.</span><span class="sxs-lookup"><span data-stu-id="25bb4-121">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
New-OrganizationAddIn -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US' -Members  'KathyBonner@contoso.com', 'MaxHargrave@contoso.com'
```

## <a name="upload-an-add-in-from-the-office-store"></a><span data-ttu-id="25bb4-122">Caricare un componente aggiuntivo da Office Store</span><span class="sxs-lookup"><span data-stu-id="25bb4-122">Upload an add-in from the Office Store</span></span>

<span data-ttu-id="25bb4-123">Eseguire il cmdlet **New-OrganizationAddIn** per caricare un manifesto da Office Store.</span><span class="sxs-lookup"><span data-stu-id="25bb4-123">Run the **New-OrganizationAddIn** cmdlet to upload a manifest from the Office Store.</span></span>
  
<span data-ttu-id="25bb4-124">Nell'esempio seguente, il cmdlet **New-OrganizationAddIn** consente di specificare il AssetID per un componente aggiuntivo per un sito e un mercato del contenuto degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="25bb4-124">In the following example, the **New-OrganizationAddIn** cmdlet specifies the AssetId for an add-in for a United States location and content market.</span></span>
  
```powershell
New-OrganizationAddIn -AssetId 'WA104099688' -Locale 'en-US' -ContentMarket 'en-US'
```

<span data-ttu-id="25bb4-125">Per determinare il valore per il parametro  _AssetID_ , è possibile copiarlo dall'URL della pagina Web di Office Store per il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="25bb4-125">To determine the value for the  _AssetId_ parameter, you can copy it from the URL of the Office Store webpage for the add-in.</span></span> <span data-ttu-id="25bb4-126">AssetIds inizia sempre con "WA" seguito da un numero.</span><span class="sxs-lookup"><span data-stu-id="25bb4-126">AssetIds always begin with "WA" followed by a number.</span></span> <span data-ttu-id="25bb4-127">Nell'esempio precedente, ad esempio, l'origine per il valore AssetId di WA104099688 è l'URL della pagina Web di Office Store per il componente aggiuntivo: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688) .</span><span class="sxs-lookup"><span data-stu-id="25bb4-127">For example, in the previous example, the source for the AssetId value of WA104099688 is the Office Store webpage URL for the add-in: [https://store.office.com/en-001/app.aspx?assetid=WA104099688](https://store.office.com/en-001/app.aspx?assetid=WA104099688).</span></span>
  
<span data-ttu-id="25bb4-128">I valori per il parametro  _locale_ e per il parametro  _ContentMarket_ sono identici e indicano il paese o l'area geografica in cui si sta tentando di installare il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="25bb4-128">The values for the  _Locale_ parameter and the  _ContentMarket_ parameter are identical and indicate the country/region you're trying to install the add-in from.</span></span> <span data-ttu-id="25bb4-129">Il formato è en-US, fr-FR.</span><span class="sxs-lookup"><span data-stu-id="25bb4-129">The format is en-US, fr-FR.</span></span> <span data-ttu-id="25bb4-130">e così via.</span><span class="sxs-lookup"><span data-stu-id="25bb4-130">and so forth.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="25bb4-131">I componenti aggiuntivi caricati da Office Store vengono aggiornati automaticamente entro pochi giorni dall'ultimo aggiornamento disponibile in Office Store.</span><span class="sxs-lookup"><span data-stu-id="25bb4-131">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="get-details-of-an-add-in"></a><span data-ttu-id="25bb4-132">Ottenere informazioni dettagliate su un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="25bb4-132">Get details of an add-in</span></span>

<span data-ttu-id="25bb4-133">Eseguire il cmdlet **Get-OrganizationAddIn** come illustrato di seguito per ottenere informazioni dettagliate su tutti i componenti aggiuntivi caricati nel tenant, incluso un ID prodotto del componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="25bb4-133">Run the **Get-OrganizationAddIn** cmdlet as shown below to get details of all add-ins uploaded to the tenant, included an add-in's product ID.</span></span>
  
```powershell
Get-OrganizationAddIn
```

<span data-ttu-id="25bb4-134">Eseguire il cmdlet **Get-OrganizationAddIn** con un valore per il parametro  _ProductID_ per specificare il componente aggiuntivo di cui si desidera recuperare i dettagli.</span><span class="sxs-lookup"><span data-stu-id="25bb4-134">Run the **Get-OrganizationAddIn** cmdlet with a value for the  _ProductId_ parameter to specify which add-in you want to retrieve details for.</span></span> 
  
```powershell
Get-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122
```

<span data-ttu-id="25bb4-135">Per ottenere informazioni complete su tutti i componenti aggiuntivi più gli utenti e i gruppi assegnati, eseguire il piping dell'output del cmdlet **Get-OrganizationAddIn** al cmdlet Format-List, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="25bb4-135">To get full details of all the add-ins plus the assigned users and groups, pipe the output of the **Get-OrganizationAddIn** cmdlet to the Format-List cmdlet, as shown in the following example.</span></span>
  
```powershell
foreach($G in (Get-organizationAddIn)){Get-OrganizationAddIn -ProductId $G.ProductId | Format-List}
```

## <a name="turn-on-or-turn-off-an-add-in"></a><span data-ttu-id="25bb4-136">Attivazione o disattivazione di un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="25bb4-136">Turn on or turn off an add-in</span></span>

<span data-ttu-id="25bb4-137">Per disattivare un componente aggiuntivo in modo che gli utenti e i gruppi a esso assegnati non avranno più accesso, eseguire il cmdlet **set-OrganizationAddIn** con il parametro  _ProductID_ e il parametro  _Enabled_ impostato su  `$false` , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="25bb4-137">To turn off an add-in so users and groups that are assigned to it will no longer have access, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_ parameter and the  _Enabled_ parameter set to  `$false`, as shown in the following example.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $false
```

<span data-ttu-id="25bb4-138">Per attivare di nuovo un componente aggiuntivo, eseguire lo stesso cmdlet con il parametro  _Enabled_ impostato su  `$true` .</span><span class="sxs-lookup"><span data-stu-id="25bb4-138">To turn an add-in back on, run the same cmdlet with the  _Enabled_ parameter set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Enabled $true
```

## <a name="add-or-remove-users-from-an-add-in"></a><span data-ttu-id="25bb4-139">Aggiungere o rimuovere utenti da un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="25bb4-139">Add or remove users from an add-in</span></span>

<span data-ttu-id="25bb4-140">Per aggiungere utenti e gruppi a un componente aggiuntivo specifico, eseguire il cmdlet **set-OrganizationAddInAssignments** con i parametri  _ProductID_,  _Add_e  _Members_ .</span><span class="sxs-lookup"><span data-stu-id="25bb4-140">To add users and groups to a specific add-in, run the **Set-OrganizationAddInAssignments** cmdlet with the  _ProductId_,  _Add_, and  _Members_ parameters.</span></span> <span data-ttu-id="25bb4-141">Separare gli indirizzi di posta elettronica dei membri con una virgola.</span><span class="sxs-lookup"><span data-stu-id="25bb4-141">Separate the email addresses of members with a comma.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Add -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="25bb4-142">Per rimuovere utenti e gruppi, eseguire lo stesso cmdlet utilizzando il parametro  _Remove_ .</span><span class="sxs-lookup"><span data-stu-id="25bb4-142">To remove users and groups, run the same cmdlet using the  _Remove_ parameter.</span></span> 
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -Remove -Members 'KathyBonner@contoso.com','sales@contoso.com'
```

<span data-ttu-id="25bb4-143">Per assegnare un componente aggiuntivo a tutti gli utenti nel tenant, eseguire lo stesso cmdlet utilizzando il parametro  _AssignToEveryone_ con il valore impostato su  `$true` .</span><span class="sxs-lookup"><span data-stu-id="25bb4-143">To assign an add-in to all users on the tenant, run the same cmdlet using the  _AssignToEveryone_ parameter with the value set to  `$true`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $true
```

<span data-ttu-id="25bb4-144">Per non assegnare un componente aggiuntivo a tutti e ripristinare gli utenti e i gruppi precedentemente assegnati, è possibile eseguire lo stesso cmdlet e disattivare il parametro  _AssignToEveryone_ impostando il relativo valore su  `$false` .</span><span class="sxs-lookup"><span data-stu-id="25bb4-144">To not assign an add-in to everyone and revert to the previously assigned users and groups, you can run the same cmdlet and turn off the  _AssignToEveryone_ parameter by setting its value to  `$false`.</span></span>
  
```powershell
Set-OrganizationAddInAssignments -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -AssignToEveryone $false
```

## <a name="update-an-add-in"></a><span data-ttu-id="25bb4-145">Aggiornare un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="25bb4-145">Update an add-in</span></span>

<span data-ttu-id="25bb4-146">Per aggiornare un componente aggiuntivo da un manifesto, eseguire il cmdlet **set-OrganizationAddIn** con i parametri  _ProductID_,  _ManifestPath_e  _locale_ , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="25bb4-146">To update an add-in from a manifest, run the **Set-OrganizationAddIn** cmdlet with the  _ProductId_,  _ManifestPath_, and  _Locale_ parameters, as shown in the following example.</span></span> 
  
```powershell
Set-OrganizationAddIn -ProductId 6a75788e-1c6b-4e9b-b5db-5975a2072122 -ManifestPath 'C:\Users\Me\Desktop\taskpane.xml' -Locale 'en-US'
```

> [!NOTE]
> <span data-ttu-id="25bb4-147">I componenti aggiuntivi caricati da Office Store vengono aggiornati automaticamente entro pochi giorni dall'ultimo aggiornamento disponibile in Office Store.</span><span class="sxs-lookup"><span data-stu-id="25bb4-147">Add-ins uploaded from the Office Store will update automatically within a few days of the latest update being available on the Office Store.</span></span> 
  
## <a name="delete-an-add-in"></a><span data-ttu-id="25bb4-148">Eliminare un componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="25bb4-148">Delete an add-in</span></span>

<span data-ttu-id="25bb4-149">Per eliminare un componente aggiuntivo, eseguire il cmdlet **Remove-OrganizationAddIn** con il parametro  _ProductID_ , come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="25bb4-149">To delete an add-in, run the **Remove-OrganizationAddIn** cmdlet with the  _ProductId_ parameter, as shown in the following example.</span></span> 
  
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

## <a name="get-detailed-help-for-each-cmdlet"></a><span data-ttu-id="25bb4-150">Ottenere informazioni dettagliate su ogni cmdlet</span><span class="sxs-lookup"><span data-stu-id="25bb4-150">Get detailed help for each cmdlet</span></span>

<span data-ttu-id="25bb4-151">È possibile esaminare la guida dettagliata per ogni cmdlet utilizzando il cmdlet Get-Help.</span><span class="sxs-lookup"><span data-stu-id="25bb4-151">You can look at detailed help for each cmdlet by using the Get-help cmdlet.</span></span> <span data-ttu-id="25bb4-152">Ad esempio, il cmdlet seguente fornisce informazioni dettagliate sul cmdlet Remove-OrganizationAddIn.</span><span class="sxs-lookup"><span data-stu-id="25bb4-152">For example, the following cmdlet provides detailed information about the Remove-OrganizationAddIn cmdlet.</span></span>
  
```powershell
Get-help Remove-OrganizationAddIn -Full
```


