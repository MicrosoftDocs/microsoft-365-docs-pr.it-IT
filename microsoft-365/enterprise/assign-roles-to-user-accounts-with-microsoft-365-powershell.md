---
title: Assegnare ruoli Microsoft 365 account utente con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: In questo articolo viene illustrato come usare PowerShell in modo rapido e semplice Microsoft 365 assegnare ruoli di amministratore agli account utente.
ms.openlocfilehash: 84e785052c970ca15487540c3904eacdd0e9ca28
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905381"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="c14d6-103">Assegnare ruoli di amministratore Microsoft 365 account utente con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c14d6-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="c14d6-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="c14d6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c14d6-105">È possibile assegnare facilmente ruoli agli account utente utilizzando PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c14d6-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="c14d6-106">Informazioni su come [assegnare ruoli di amministratore](../admin/add-users/assign-admin-roles.md) agli account utente con l'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="c14d6-106">Learn how to  [assign admin roles](../admin/add-users/assign-admin-roles.md) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="c14d6-107">Per un elenco delle risorse aggiuntive, vedere [Manage users and groups](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="c14d6-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c14d6-108">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="c14d6-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c14d6-109">Innanzitutto, utilizzare un account amministratore globale per [connettersi al tenant Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="c14d6-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="c14d6-110">Identificare quindi il nome di accesso dell'account utente che si desidera aggiungere a un ruolo (ad esempio: fredsm \@ contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c14d6-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="c14d6-111">Questo nome è noto anche come nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="c14d6-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="c14d6-112">Successivamente, determinare il nome del ruolo.</span><span class="sxs-lookup"><span data-stu-id="c14d6-112">Next, determine the name of the role.</span></span> <span data-ttu-id="c14d6-113">Vedere [autorizzazioni del ruolo di amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="c14d6-113">See [administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="c14d6-114">Prestare attenzione alle note in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c14d6-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="c14d6-115">Alcuni nomi di ruolo sono diversi per Azure Active Directory (Azure AD) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c14d6-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="c14d6-116">Ad esempio, il *ruolo SharePoint amministratore* nell'interfaccia di amministrazione Microsoft 365 è SharePoint *amministratore* del servizio in Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c14d6-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="c14d6-117">Quindi, inserire i nomi di accesso e di ruolo ed eseguire questi comandi:</span><span class="sxs-lookup"><span data-stu-id="c14d6-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="c14d6-118">Ecco un esempio di un set di comandi completato che assegna il ruolo SharePoint Service Administrator all'account *di contoso.com \@ belindan:*</span><span class="sxs-lookup"><span data-stu-id="c14d6-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="c14d6-119">Per visualizzare l'elenco dei nomi utente per uno specifico ruolo di amministratore, utilizzare questi comandi.</span><span class="sxs-lookup"><span data-stu-id="c14d6-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="c14d6-120">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c14d6-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="c14d6-121">Innanzitutto, utilizzare un account amministratore globale per [connettersi al tenant Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="c14d6-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="c14d6-122">Per una singola modifica del ruolo</span><span class="sxs-lookup"><span data-stu-id="c14d6-122">For a single role change</span></span>

<span data-ttu-id="c14d6-123">I modi più comuni per specificare l'account utente sono il nome visualizzato o il nome di posta elettronica, noto anche come nome di accesso o nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="c14d6-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="c14d6-124">Nomi visualizzati degli account utente</span><span class="sxs-lookup"><span data-stu-id="c14d6-124">Display names of user accounts</span></span>

<span data-ttu-id="c14d6-125">Se si è utilizzati per utilizzare i nomi visualizzati degli account utente, determinare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c14d6-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="c14d6-126">L'account utente che si desidera configurare</span><span class="sxs-lookup"><span data-stu-id="c14d6-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="c14d6-127">Per specificare l'account utente, è necessario determinare il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="c14d6-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="c14d6-128">Per ottenere un elenco completo degli account, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="c14d6-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="c14d6-129">Questo comando elenca il nome visualizzato degli account utente, ordinati per nome visualizzato, una schermata alla volta.</span><span class="sxs-lookup"><span data-stu-id="c14d6-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="c14d6-130">È possibile filtrare l'elenco in un set più piccolo utilizzando il cmdlet **Where**.</span><span class="sxs-lookup"><span data-stu-id="c14d6-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="c14d6-131">Vedere l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c14d6-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="c14d6-132">PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="c14d6-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="c14d6-133">Eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c14d6-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="c14d6-134">Questo comando elenca solo gli account utente per cui il nome visualizzato inizia con "John".</span><span class="sxs-lookup"><span data-stu-id="c14d6-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="c14d6-135">Ruolo che si desidera assegnare</span><span class="sxs-lookup"><span data-stu-id="c14d6-135">The role you want to assign</span></span>
    
    <span data-ttu-id="c14d6-136">Per visualizzare l'elenco dei ruoli di amministratore disponibili che è possibile assegnare agli account utente, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="c14d6-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="c14d6-137">Dopo aver determinato il nome visualizzato dell'account e il nome del ruolo, utilizzare questi comandi per assegnare il ruolo all'account:</span><span class="sxs-lookup"><span data-stu-id="c14d6-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="c14d6-138">Incollare i comandi in Blocco note.</span><span class="sxs-lookup"><span data-stu-id="c14d6-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="c14d6-139">Per le *variabili $dispName* *e $roleName,* sostituire il testo della descrizione con i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="c14d6-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="c14d6-140">Rimuovere i \< and > caratteri ma mantenere le virgolette.</span><span class="sxs-lookup"><span data-stu-id="c14d6-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="c14d6-141">Incollare le righe modificate nel modulo Microsoft Azure Active Directory per Windows PowerShell per eseguirle.</span><span class="sxs-lookup"><span data-stu-id="c14d6-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="c14d6-142">È anche possibile utilizzare Windows PowerShell Integrated Scripting Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="c14d6-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="c14d6-143">Ecco un esempio di un set di comandi completato:</span><span class="sxs-lookup"><span data-stu-id="c14d6-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="c14d6-144">Nomi di accesso degli account utente</span><span class="sxs-lookup"><span data-stu-id="c14d6-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="c14d6-145">Se si è abituati a utilizzare i nomi di accesso o gli UPN degli account utente, determinare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c14d6-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="c14d6-146">UPN dell'account utente</span><span class="sxs-lookup"><span data-stu-id="c14d6-146">The user account's UPN</span></span>
    
    <span data-ttu-id="c14d6-147">Se non si conosce l'UPN, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="c14d6-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="c14d6-148">Questo comando elenca l'UPN degli account utente, ordinati per UPN, una schermata alla volta.</span><span class="sxs-lookup"><span data-stu-id="c14d6-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="c14d6-149">È possibile utilizzare il cmdlet **Where** per filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="c14d6-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="c14d6-150">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="c14d6-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="c14d6-151">Questo comando elenca solo gli account utente per cui il nome visualizzato inizia con "John".</span><span class="sxs-lookup"><span data-stu-id="c14d6-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="c14d6-152">Ruolo che si desidera assegnare</span><span class="sxs-lookup"><span data-stu-id="c14d6-152">The role you want to assign</span></span>
    
    <span data-ttu-id="c14d6-153">Per visualizzare l'elenco dei ruoli disponibili che è possibile assegnare agli account utente, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="c14d6-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="c14d6-154">Dopo aver impostato l'UPN dell'account e il nome del ruolo, utilizzare questi comandi per assegnare il ruolo all'account:</span><span class="sxs-lookup"><span data-stu-id="c14d6-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="c14d6-155">Copiare i comandi e incollarli nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="c14d6-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="c14d6-156">Per le **$upnName** e **$roleName** variabili.</span><span class="sxs-lookup"><span data-stu-id="c14d6-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="c14d6-157">Sostituire il testo della descrizione con i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="c14d6-157">Replace the description text with their values.</span></span> <span data-ttu-id="c14d6-158">Rimuovere i \< and > caratteri ma mantenere le virgolette.</span><span class="sxs-lookup"><span data-stu-id="c14d6-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="c14d6-159">Incollare le righe modificate Microsoft Azure Active Directory modulo per Windows PowerShell finestra per eseguirle.</span><span class="sxs-lookup"><span data-stu-id="c14d6-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="c14d6-160">In alternativa, è possibile utilizzare il Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="c14d6-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="c14d6-161">Ecco un esempio di un set di comandi completato:</span><span class="sxs-lookup"><span data-stu-id="c14d6-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="c14d6-162">Modifiche a più ruoli</span><span class="sxs-lookup"><span data-stu-id="c14d6-162">Multiple role changes</span></span>

<span data-ttu-id="c14d6-163">Per le modifiche a più ruoli, determinare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c14d6-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="c14d6-164">Quali account utente si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="c14d6-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="c14d6-165">È possibile utilizzare i metodi descritti nella sezione precedente per raccogliere il set di nomi visualizzati o UPN.</span><span class="sxs-lookup"><span data-stu-id="c14d6-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="c14d6-166">Ruoli che si desidera assegnare a ogni account utente.</span><span class="sxs-lookup"><span data-stu-id="c14d6-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="c14d6-167">Per visualizzare l'elenco dei ruoli disponibili che è possibile assegnare agli account utente, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="c14d6-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="c14d6-168">Creare quindi un file di testo con valori delimitati da virgole (CSV) con il nome visualizzato o l'UPN e i campi del nome del ruolo.</span><span class="sxs-lookup"><span data-stu-id="c14d6-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="c14d6-169">Puoi farlo facilmente in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="c14d6-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="c14d6-170">Ecco un esempio per i nomi visualizzati:</span><span class="sxs-lookup"><span data-stu-id="c14d6-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="c14d6-171">Immettere infine il percorso del file CSV ed eseguire i comandi risultanti al prompt dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c14d6-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="c14d6-172">Ecco un esempio di UPN:</span><span class="sxs-lookup"><span data-stu-id="c14d6-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="c14d6-173">Immettere infine il percorso del file CSV ed eseguire i comandi risultanti al prompt dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c14d6-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="c14d6-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c14d6-174">See also</span></span>

- [<span data-ttu-id="c14d6-175">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c14d6-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c14d6-176">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c14d6-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c14d6-177">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c14d6-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)