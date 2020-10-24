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
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754199"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="cc00b-103">Assegnare i ruoli di amministratore agli account utente di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc00b-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="cc00b-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cc00b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cc00b-105">È possibile assegnare facilmente i ruoli agli account utente tramite PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc00b-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="cc00b-106">Informazioni su come  [assegnare i ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) agli account utente con l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cc00b-106">Learn how to  [assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="cc00b-107">Per un elenco di risorse aggiuntive, vedere [Manage Users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="cc00b-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="cc00b-108">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="cc00b-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="cc00b-109">Per prima cosa, utilizzare un account di amministratore globale per [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="cc00b-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="cc00b-110">Successivamente, identificare il nome di accesso dell'account utente che si desidera aggiungere a un ruolo (ad esempio: fredsm \@ contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cc00b-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="cc00b-111">Questo è conosciuto anche come nome dell'entità utente (UPN, User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="cc00b-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="cc00b-112">Successivamente, determinare il nome del ruolo.</span><span class="sxs-lookup"><span data-stu-id="cc00b-112">Next, determine the name of the role.</span></span> <span data-ttu-id="cc00b-113">Vedere [autorizzazioni per i ruoli di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="cc00b-113">See [administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="cc00b-114">Prestare attenzione alle note in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="cc00b-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="cc00b-115">Alcuni nomi di ruolo sono diversi per PowerShell di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="cc00b-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="cc00b-116">Ad esempio, il ruolo di *amministratore di SharePoint* nell'interfaccia di amministrazione di Microsoft 365 è amministratore del *servizio di SharePoint* in Azure ad PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc00b-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="cc00b-117">Successivamente, immettere i nomi di accesso e di ruolo ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc00b-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
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

<span data-ttu-id="cc00b-118">Di seguito è riportato un esempio di un set di comandi completato che assegna il ruolo di amministratore del servizio di SharePoint all'account \* \@ contoso.com di dilindan\* :</span><span class="sxs-lookup"><span data-stu-id="cc00b-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
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

<span data-ttu-id="cc00b-119">Per visualizzare l'elenco dei nomi utente per uno specifico ruolo di amministratore, utilizzare questi comandi.</span><span class="sxs-lookup"><span data-stu-id="cc00b-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="cc00b-120">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc00b-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="cc00b-121">Per prima cosa, utilizzare un account di amministratore globale per [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="cc00b-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="cc00b-122">Per una singola modifica del ruolo</span><span class="sxs-lookup"><span data-stu-id="cc00b-122">For a single role change</span></span>

<span data-ttu-id="cc00b-123">La modalità più comune per specificare l'account utente consiste nell'utilizzare il relativo nome visualizzato o il relativo nome di posta elettronica, noto anche come nome di accesso o nome dell'entità utente (UPN, User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="cc00b-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="cc00b-124">Visualizzazione dei nomi degli account utente</span><span class="sxs-lookup"><span data-stu-id="cc00b-124">Display names of user accounts</span></span>

<span data-ttu-id="cc00b-125">Se si è abituati a utilizzare i nomi visualizzati degli account utente, determinare le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="cc00b-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="cc00b-126">L'account utente che si desidera configurare</span><span class="sxs-lookup"><span data-stu-id="cc00b-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="cc00b-127">Per specificare l'account utente, è necessario determinare il nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="cc00b-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="cc00b-128">Per ottenere un elenco completo degli account, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="cc00b-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="cc00b-129">Questo comando elenca il nome visualizzato degli account utente, ordinati per nome visualizzato, una schermata alla volta.</span><span class="sxs-lookup"><span data-stu-id="cc00b-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="cc00b-130">È possibile filtrare l'elenco in un set più piccolo utilizzando il cmdlet **Where**.</span><span class="sxs-lookup"><span data-stu-id="cc00b-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="cc00b-131">Vedere l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="cc00b-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="cc00b-132">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per il modulo di Windows PowerShell e i cmdlet con *MSOL* nel proprio nome.</span><span class="sxs-lookup"><span data-stu-id="cc00b-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="cc00b-133">Eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc00b-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="cc00b-134">Questo comando elenca solo gli account utente per cui il nome visualizzato inizia con "John".</span><span class="sxs-lookup"><span data-stu-id="cc00b-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="cc00b-135">Il ruolo che si desidera assegnare</span><span class="sxs-lookup"><span data-stu-id="cc00b-135">The role you want to assign</span></span>
    
    <span data-ttu-id="cc00b-136">Per visualizzare l'elenco dei ruoli di amministratore disponibili che è possibile assegnare agli account utente, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="cc00b-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="cc00b-137">Dopo aver determinato il nome visualizzato dell'account e il nome del ruolo, utilizzare questi comandi per assegnare il ruolo all'account:</span><span class="sxs-lookup"><span data-stu-id="cc00b-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="cc00b-138">Incollare i comandi nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="cc00b-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="cc00b-139">Per le variabili *$dispName* e *$roleName* , sostituire il testo della descrizione con i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="cc00b-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="cc00b-140">Rimuovere i \< and > caratteri ma mantenere le virgolette.</span><span class="sxs-lookup"><span data-stu-id="cc00b-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="cc00b-141">Incollare le righe modificate nella finestra di Microsoft Azure Active Directory Module per Windows PowerShell per eseguirle.</span><span class="sxs-lookup"><span data-stu-id="cc00b-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="cc00b-142">È anche possibile utilizzare Windows PowerShell Integrated Scripting Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="cc00b-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="cc00b-143">Di seguito è riportato un esempio di un set di comandi completato:</span><span class="sxs-lookup"><span data-stu-id="cc00b-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="cc00b-144">Nomi di accesso degli account utente</span><span class="sxs-lookup"><span data-stu-id="cc00b-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="cc00b-145">Se si è abituati a utilizzare i nomi di accesso o gli account utente di UPN, determinare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc00b-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="cc00b-146">UPN dell'account utente</span><span class="sxs-lookup"><span data-stu-id="cc00b-146">The user account's UPN</span></span>
    
    <span data-ttu-id="cc00b-147">Se non si conosce l'UPN, utilizzare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="cc00b-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="cc00b-148">Questo comando elenca l'UPN degli account utente, ordinati in base all'UPN, una schermata alla volta.</span><span class="sxs-lookup"><span data-stu-id="cc00b-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="cc00b-149">È possibile utilizzare il cmdlet **where** per filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="cc00b-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="cc00b-150">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="cc00b-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="cc00b-151">Questo comando elenca solo gli account utente per cui il nome visualizzato inizia con "John".</span><span class="sxs-lookup"><span data-stu-id="cc00b-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="cc00b-152">Il ruolo che si desidera assegnare</span><span class="sxs-lookup"><span data-stu-id="cc00b-152">The role you want to assign</span></span>
    
    <span data-ttu-id="cc00b-153">Per visualizzare l'elenco dei ruoli disponibili che è possibile assegnare agli account utente, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="cc00b-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="cc00b-154">Dopo aver utilizzato l'UPN dell'account e il nome del ruolo, utilizzare questi comandi per assegnare il ruolo all'account:</span><span class="sxs-lookup"><span data-stu-id="cc00b-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="cc00b-155">Copiare i comandi e incollarli nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="cc00b-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="cc00b-156">Per le variabili **$upnName** e **$roleName** .</span><span class="sxs-lookup"><span data-stu-id="cc00b-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="cc00b-157">Sostituire il testo della descrizione con i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="cc00b-157">Replace the description text with their values.</span></span> <span data-ttu-id="cc00b-158">Rimuovere i \< and > caratteri ma mantenere le virgolette.</span><span class="sxs-lookup"><span data-stu-id="cc00b-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="cc00b-159">Incollare le righe modificate nella finestra di Microsoft Azure Active Directory Module per Windows PowerShell per eseguirle.</span><span class="sxs-lookup"><span data-stu-id="cc00b-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="cc00b-160">In alternativa, è possibile utilizzare Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="cc00b-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="cc00b-161">Di seguito è riportato un esempio di un set di comandi completato:</span><span class="sxs-lookup"><span data-stu-id="cc00b-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="cc00b-162">Modifiche a più ruoli</span><span class="sxs-lookup"><span data-stu-id="cc00b-162">Multiple role changes</span></span>

<span data-ttu-id="cc00b-163">Per le modifiche a più ruoli, determinare le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="cc00b-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="cc00b-164">Gli account utente che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="cc00b-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="cc00b-165">È possibile utilizzare i metodi descritti nella sezione precedente per raccogliere il set di nomi visualizzati o UPN.</span><span class="sxs-lookup"><span data-stu-id="cc00b-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="cc00b-166">Ruoli che si desidera assegnare a ogni account utente.</span><span class="sxs-lookup"><span data-stu-id="cc00b-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="cc00b-167">Per visualizzare l'elenco dei ruoli disponibili che è possibile assegnare agli account utente, usare questo comando:</span><span class="sxs-lookup"><span data-stu-id="cc00b-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="cc00b-168">Successivamente, creare un file di testo con valori delimitati da virgole (CSV) con il nome visualizzato o i campi UPN e nome ruolo.</span><span class="sxs-lookup"><span data-stu-id="cc00b-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="cc00b-169">È possibile eseguire questa operazione facilmente in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="cc00b-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="cc00b-170">Di seguito è riportato un esempio per i nomi visualizzati:</span><span class="sxs-lookup"><span data-stu-id="cc00b-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="cc00b-171">Immettere infine il percorso del file CSV ed eseguire i comandi risultanti al prompt dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc00b-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="cc00b-172">Di seguito è riportato un esempio di UPN:</span><span class="sxs-lookup"><span data-stu-id="cc00b-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="cc00b-173">Immettere infine il percorso del file CSV ed eseguire i comandi risultanti al prompt dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc00b-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="cc00b-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc00b-174">See also</span></span>

- [<span data-ttu-id="cc00b-175">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc00b-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cc00b-176">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc00b-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="cc00b-177">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc00b-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
