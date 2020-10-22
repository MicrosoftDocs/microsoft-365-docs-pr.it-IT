---
title: Assegnare i ruoli agli account utente di Microsoft 365 con PowerShell
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
description: In questo articolo vengono fornite informazioni su come utilizzare PowerShell per Microsoft 365 in modo rapido e semplice per assegnare ruoli di amministratore agli account utente.
ms.openlocfilehash: 1486c86172cd34e6e88f8cd02d003967518bcdb7
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655948"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="1753a-103">Assegnare i ruoli di amministratore agli account utente di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1753a-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="1753a-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1753a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1753a-105">È possibile assegnare rapidamente e facilmente i ruoli di amministratore agli account utente tramite PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1753a-105">You can quickly and easily assign admin roles to user accounts using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="1753a-106">[Informazioni su come assegnare i ruoli di amministratore agli account utente](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) con l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1753a-106">[Learn how to assign admin roles to user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="1753a-107">Per un elenco di risorse aggiuntive, vedere [Manage Users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="1753a-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1753a-108">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="1753a-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1753a-109">Per prima cosa, [connettersi al tenant di Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) utilizzando un account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1753a-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) using a global administrator account.</span></span>
  
<span data-ttu-id="1753a-p102">Determinare quindi il nome di accesso dell'account utente da aggiungere a un ruolo (ad esempio mario@contoso.com). Questo nome di accesso è noto anche come nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="1753a-p102">Next, determine the sign-in name of the user account that you want to add to a role (example: fredsm@contoso.com). This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="1753a-112">Successivamente, determinare il nome del ruolo di amministratore.</span><span class="sxs-lookup"><span data-stu-id="1753a-112">Next, determine the name of the admin role.</span></span> <span data-ttu-id="1753a-113">Usare questo [elenco di autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="1753a-113">Use this [list of administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="1753a-114">Prestare attenzione alle note in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1753a-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="1753a-115">Alcuni nomi di ruoli sono diversi per Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1753a-115">Some role names are different for Azure AD PowerShell.</span></span> <span data-ttu-id="1753a-116">Ad esempio, il ruolo "Amministratore di SharePoint" nell'interfaccia di amministrazione di Microsoft 365 è denominato "Amministratore del servizio SharePoint" in Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1753a-116">For example, the "SharePoint Administrator" role in the Microsoft 365 admin center is named "SharePoint Service Administrator" for Azure AD PowerShell.</span></span>
>

<span data-ttu-id="1753a-117">Immettere quindi i nomi di accesso e di ruolo ed eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="1753a-117">Next, fill in the sign-in and role names and run these commands.</span></span>
  
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

<span data-ttu-id="1753a-118">Di seguito è riportato un esempio di un set di comandi completato che assegna il ruolo di amministratore del servizio di SharePoint all'account belindan@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="1753a-118">Here is an example of a completed command set that assigns the SharePoint Service Administrator admin role to the belindan@contoso.com account:</span></span>
  
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

<span data-ttu-id="1753a-119">Per visualizzare l'elenco dei nomi utente per uno specifico ruolo di amministratore, utilizzare questi comandi.</span><span class="sxs-lookup"><span data-stu-id="1753a-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1753a-120">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1753a-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1753a-121">Per prima cosa, [connettersi al tenant di Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) utilizzando un account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1753a-121">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) using a global administrator account.</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="1753a-122">Per una singola modifica del ruolo</span><span class="sxs-lookup"><span data-stu-id="1753a-122">For a single role change</span></span>

<span data-ttu-id="1753a-123">La modalità più comune di un account utente specifico è il nome visualizzato o il nome di posta elettronica, noto anche come nome di accesso o nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="1753a-123">The most common ways of specific user account is with its display name or its email name, also known its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="1753a-124">Visualizzazione dei nomi degli account utente</span><span class="sxs-lookup"><span data-stu-id="1753a-124">Display names of user accounts</span></span>

<span data-ttu-id="1753a-125">Se si è abituati a utilizzare i nomi visualizzati degli account utente, determinare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1753a-125">If you are used to working with the display names of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="1753a-126">L'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="1753a-126">The user account that you want to configure.</span></span>
    
    <span data-ttu-id="1753a-p105">Per specificare l'account utente, è necessario determinare il nome visualizzato. Per ottenere un elenco completo di account, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="1753a-p105">To specify the user account, you must determine its Display Name. To get a complete list accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="1753a-p106">Questo comando elenca il nome visualizzato degli account utente, ordinati per nome visualizzato, una schermata alla volta. È possibile filtrare l'elenco in un set più piccolo utilizzando il cmdlet **Where**. Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="1753a-p106">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time. You can filter the list to a smaller set by using the **Where** cmdlet. Here is an example:</span></span>

   >[!Note]
   ><span data-ttu-id="1753a-132">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="1753a-132">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="1753a-133">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1753a-133">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="1753a-134">Questo comando elenca solo gli account utente per cui il nome visualizzato inizia con "John".</span><span class="sxs-lookup"><span data-stu-id="1753a-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="1753a-135">Il ruolo da assegnare.</span><span class="sxs-lookup"><span data-stu-id="1753a-135">The role you want to assign.</span></span>
    
    <span data-ttu-id="1753a-136">Per visualizzare l'elenco dei ruoli di amministratore disponibili che è possibile assegnare agli account utente, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="1753a-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="1753a-137">Dopo aver determinato il nome visualizzato dell'account e il nome del ruolo di amministratore, utilizzare questi comandi per assegnare il ruolo all'account:</span><span class="sxs-lookup"><span data-stu-id="1753a-137">Once you have determined the Display Name of the account and the Name of the admin role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="1753a-138">Copiare i comandi e incollarli nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="1753a-138">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="1753a-139">Per le variabili **$dispName** e **$roleName** , sostituire il testo della descrizione con i relativi valori, rimuovere i \< and > caratteri e lasciare le virgolette.</span><span class="sxs-lookup"><span data-stu-id="1753a-139">For the **$dispName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="1753a-140">Copiare le righe modificate e incollarle nel modulo di Windows Azure Active Directory modulo affinché Windows PowerShell le esegua.</span><span class="sxs-lookup"><span data-stu-id="1753a-140">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="1753a-141">È anche possibile utilizzare Windows PowerShell Integrated Scripting Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="1753a-141">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="1753a-142">Segue un esempio di un set di comandi completati:</span><span class="sxs-lookup"><span data-stu-id="1753a-142">Here is an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="1753a-143">Nomi di accesso degli account utente</span><span class="sxs-lookup"><span data-stu-id="1753a-143">Sign-in names of user accounts</span></span>

<span data-ttu-id="1753a-144">Se si è abituati a utilizzare i nomi di accesso o gli account utente di UPN, determinare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1753a-144">If you are used to working with the sign-in names or UPNs of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="1753a-145">UPN dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="1753a-145">The user account's UPN.</span></span>
    
    <span data-ttu-id="1753a-146">Se non si conosce già l'UPN, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="1753a-146">If you don't already know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="1753a-147">Questo comando consente di elencare l'UPN degli account utente, ordinati in base all'UPN, una schermata alla volta.</span><span class="sxs-lookup"><span data-stu-id="1753a-147">This command lists the UPN of your user accounts, sorted by the UPN, one screen at a time.</span></span> <span data-ttu-id="1753a-148">È possibile filtrare l'elenco in un set più piccolo utilizzando il cmdlet **Where**.</span><span class="sxs-lookup"><span data-stu-id="1753a-148">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="1753a-149">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="1753a-149">Here is an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="1753a-150">Questo comando elenca solo gli account utente per cui il nome visualizzato inizia con "John".</span><span class="sxs-lookup"><span data-stu-id="1753a-150">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="1753a-151">Il ruolo da assegnare.</span><span class="sxs-lookup"><span data-stu-id="1753a-151">The role you want to assign.</span></span>
    
    <span data-ttu-id="1753a-152">Per visualizzare l'elenco dei ruoli disponibili che è possibile assegnare agli account utente, usare il comando:</span><span class="sxs-lookup"><span data-stu-id="1753a-152">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="1753a-153">Una volta che si dispone dell'UPN dell'account e del nome del ruolo, utilizzare questi comandi per assegnare il ruolo all'account:</span><span class="sxs-lookup"><span data-stu-id="1753a-153">Once you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="1753a-154">Copiare i comandi e incollarli nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="1753a-154">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="1753a-155">Per le variabili **$upnName** e **$roleName** , sostituire il testo della descrizione con i relativi valori, rimuovere i \< and > caratteri e lasciare le virgolette.</span><span class="sxs-lookup"><span data-stu-id="1753a-155">For the **$upnName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="1753a-156">Copiare le righe modificate e incollarle nel modulo di Windows Azure Active Directory modulo affinché Windows PowerShell le esegua.</span><span class="sxs-lookup"><span data-stu-id="1753a-156">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="1753a-157">In alternativa, è possibile utilizzare Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="1753a-157">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="1753a-158">Segue un esempio di un set di comandi completati:</span><span class="sxs-lookup"><span data-stu-id="1753a-158">Here is an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="1753a-159">Modifiche a più ruoli</span><span class="sxs-lookup"><span data-stu-id="1753a-159">Multiple role changes</span></span>

<span data-ttu-id="1753a-160">Per le modifiche a più ruoli, determinare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1753a-160">For multiple role changes, determine the following:</span></span>
  
- <span data-ttu-id="1753a-161">Quali account utente configurare.</span><span class="sxs-lookup"><span data-stu-id="1753a-161">Which user accounts that you want to configure.</span></span> <span data-ttu-id="1753a-162">È possibile utilizzare i metodi descritti nella sezione precedente per raccogliere il set di nomi visualizzati o UPN.</span><span class="sxs-lookup"><span data-stu-id="1753a-162">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="1753a-163">Ruoli che si desidera assegnare a ogni account utente.</span><span class="sxs-lookup"><span data-stu-id="1753a-163">Which roles you want to assign to each user account.</span></span>
    
    <span data-ttu-id="1753a-164">Per visualizzare l'elenco dei ruoli disponibili che è possibile assegnare agli account utente, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="1753a-164">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="1753a-165">Successivamente, creare un file di testo con valori delimitati da virgole (CSV) con il nome visualizzato o i campi UPN e nome ruolo.</span><span class="sxs-lookup"><span data-stu-id="1753a-165">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="1753a-166">È possibile eseguire questa operazione facilmente con Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="1753a-166">You can do this easily with Microsoft Excel.</span></span>

<span data-ttu-id="1753a-167">Di seguito è riportato un esempio per i nomi visualizzati:</span><span class="sxs-lookup"><span data-stu-id="1753a-167">Here is an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="1753a-168">Immettere infine il percorso del file CSV ed eseguire i comandi risultanti al prompt dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1753a-168">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="1753a-169">Di seguito è riportato un esempio per UPN:</span><span class="sxs-lookup"><span data-stu-id="1753a-169">Here is an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="1753a-170">Immettere infine il percorso del file CSV ed eseguire i comandi risultanti al prompt dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1753a-170">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="1753a-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1753a-171">See also</span></span>

- [<span data-ttu-id="1753a-172">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1753a-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1753a-173">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1753a-173">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1753a-174">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1753a-174">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
