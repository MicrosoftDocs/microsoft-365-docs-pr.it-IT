---
title: Visualizzare gli account utente di Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Informazioni su come visualizzare, elencare o visualizzare gli account utente di Microsoft 365 in modi diversi con PowerShell.
ms.openlocfilehash: de91195afeb8480bf231d9536e4b3a94502a6da1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924649"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="d5318-103">Visualizzare gli account utente di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5318-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="d5318-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d5318-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d5318-105">È possibile usare l'interfaccia di amministrazione di Microsoft 365 per visualizzare gli account per il tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5318-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="d5318-106">PowerShell per Microsoft 365 abilita questa funzionalità, ma offre anche funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="d5318-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="d5318-107">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="d5318-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="d5318-108">Innanzitutto, [connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="d5318-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="d5318-109">Visualizzare tutti gli account</span><span class="sxs-lookup"><span data-stu-id="d5318-109">View all accounts</span></span>

<span data-ttu-id="d5318-110">Per visualizzare l'elenco completo degli account utente, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="d5318-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="d5318-111">È consigliabile ottenere informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5318-111">You should get information similar to this:</span></span>
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a><span data-ttu-id="d5318-112">Visualizzare un account specifico</span><span class="sxs-lookup"><span data-stu-id="d5318-112">View a specific account</span></span>

<span data-ttu-id="d5318-113">Per visualizzare un account utente specifico, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="d5318-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="d5318-114">Immettere il nome dell'account di accesso dell'account utente, noto anche come nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="d5318-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="d5318-115">Rimuovere i caratteri "<" e ">".</span><span class="sxs-lookup"><span data-stu-id="d5318-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="d5318-116">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="d5318-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="d5318-117">Visualizzare valori di proprietà aggiuntivi per un account specifico</span><span class="sxs-lookup"><span data-stu-id="d5318-117">View additional property values for a specific account</span></span>

<span data-ttu-id="d5318-118">Per impostazione predefinita, il cmdlet **Get-AzureADUser** visualizza solo le *proprietà ObjectID,* *DisplayName* e *UserPrincipalName* degli account.</span><span class="sxs-lookup"><span data-stu-id="d5318-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="d5318-119">Per essere più selettivi sulle proprietà da visualizzare, utilizzare il cmdlet **Select** in combinazione con il cmdlet **Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="d5318-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="d5318-120">Per combinare i due cmdlet, utilizzare il carattere "pipe" ("|"), che indica ad Azure Active Directory PowerShell per Graph di ottenere i risultati di un comando e inviarlo al comando successivo.</span><span class="sxs-lookup"><span data-stu-id="d5318-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="d5318-121">Ecco un comando di esempio che visualizza *DisplayName,* *Department* e *UsageLocation* per ogni account utente:</span><span class="sxs-lookup"><span data-stu-id="d5318-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="d5318-122">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="d5318-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="d5318-123">Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d5318-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="d5318-124">Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo (**Selezionare DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="d5318-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="d5318-125">Per visualizzare tutte le proprietà di un account utente specifico, utilizzare il cmdlet **Select** e il carattere jolly (\*).</span><span class="sxs-lookup"><span data-stu-id="d5318-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="d5318-126">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="d5318-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="d5318-127">Come altro esempio, eseguire il comando seguente per controllare lo stato abilitato di un account utente specifico:</span><span class="sxs-lookup"><span data-stu-id="d5318-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="d5318-128">Visualizzare lo stato di sincronizzazione degli account</span><span class="sxs-lookup"><span data-stu-id="d5318-128">View account synchronization status</span></span>

<span data-ttu-id="d5318-129">Gli account utente hanno due origini:</span><span class="sxs-lookup"><span data-stu-id="d5318-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="d5318-130">Windows Server Active Directory (AD), ovvero account sincronizzati da Active Directory locale al cloud.</span><span class="sxs-lookup"><span data-stu-id="d5318-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="d5318-131">Account Di Azure Active Directory (Azure AD), creati direttamente nel cloud.</span><span class="sxs-lookup"><span data-stu-id="d5318-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="d5318-132">Il comando seguente indica a PowerShell di ottenere tutti gli utenti con l'attributo *DirSyncEnabled* impostato su *True.*</span><span class="sxs-lookup"><span data-stu-id="d5318-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="d5318-133">Puoi usarlo per trovare gli account che si sincronizzano da Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="d5318-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="d5318-134">Il comando seguente indica a PowerShell di ottenere tutti gli utenti con l'attributo *DirSyncEnabled* impostato su *False.*</span><span class="sxs-lookup"><span data-stu-id="d5318-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="d5318-135">Puoi usarlo per trovare account solo cloud.</span><span class="sxs-lookup"><span data-stu-id="d5318-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="d5318-136">Visualizzare gli account in base a una proprietà comune</span><span class="sxs-lookup"><span data-stu-id="d5318-136">View accounts based on a common property</span></span>

<span data-ttu-id="d5318-137">Per essere più selettivi sull'elenco di account da visualizzare, è possibile utilizzare il cmdlet **Where** in combinazione con il cmdlet **Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="d5318-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="d5318-138">Per combinare i due cmdlet, utilizzare il carattere "pipe" ("|"), che indica ad Azure Active Directory PowerShell per Graph di ottenere i risultati di un comando e inviarlo al comando successivo.</span><span class="sxs-lookup"><span data-stu-id="d5318-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="d5318-139">Ecco un comando di esempio che visualizza solo gli account utente con un percorso di utilizzo non specificato:</span><span class="sxs-lookup"><span data-stu-id="d5318-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="d5318-140">Questo comando indica ad Azure Active Directory PowerShell per Graph di:</span><span class="sxs-lookup"><span data-stu-id="d5318-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="d5318-141">Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d5318-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d5318-142">Trovare tutti gli account utente con un percorso di utilizzo non specificato (**Where {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="d5318-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="d5318-143">All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account per cui la proprietà dell'account utente UsageLocation (**$ \_ . UsageLocation**) non è specificato (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="d5318-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="d5318-144">La proprietà **UsageLocation** è solo una delle tante associate a un account utente.</span><span class="sxs-lookup"><span data-stu-id="d5318-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="d5318-145">Per visualizzare tutte le proprietà di un account utente specifico, utilizzare il cmdlet **Select** e il carattere jolly (\*).</span><span class="sxs-lookup"><span data-stu-id="d5318-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="d5318-146">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="d5318-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="d5318-147">**City** è il nome di una proprietà dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="d5318-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="d5318-148">È possibile utilizzare il comando seguente per elencare tutti gli account degli utenti che vivono a Londra:</span><span class="sxs-lookup"><span data-stu-id="d5318-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="d5318-149">La sintassi del cmdlet **Where** in questi esempi è **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="d5318-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="d5318-150">[nome proprietà account utente] [operatore di confronto] [valore] **}**.> [operatore di confronto] è **-eq** per uguale a, **-ne** per diverso da, **-lt** per minore di, **-gt** per maggiore di e altri.</span><span class="sxs-lookup"><span data-stu-id="d5318-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="d5318-151">[valore] è in genere una stringa (una sequenza di lettere, numeri e altri caratteri), un valore numerico **o** $Null per non specificato.</span><span class="sxs-lookup"><span data-stu-id="d5318-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="d5318-152">Per ulteriori informazioni, vedere [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="d5318-152">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="d5318-153">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5318-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="d5318-154">Innanzitutto, [connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="d5318-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="d5318-155">Visualizzare tutti gli account</span><span class="sxs-lookup"><span data-stu-id="d5318-155">View all accounts</span></span>

<span data-ttu-id="d5318-156">Per visualizzare l'elenco completo degli account utente, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="d5318-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="d5318-157">PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="d5318-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="d5318-158">Eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5318-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="d5318-159">È consigliabile ottenere informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5318-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="d5318-160">Il cmdlet **Get-MsolUser** dispone inoltre di un set di parametri per filtrare il gruppo di account utente visualizzato.</span><span class="sxs-lookup"><span data-stu-id="d5318-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="d5318-161">Ad esempio, per l'elenco degli utenti senza licenza (utenti aggiunti a Microsoft 365 ma non ancora concessi in licenza per l'utilizzo di uno dei servizi), eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="d5318-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="d5318-162">È consigliabile ottenere informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5318-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="d5318-163">Per informazioni sui parametri aggiuntivi per filtrare il set di account utente visualizzati, vedere [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="d5318-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="d5318-164">Visualizzare un account specifico</span><span class="sxs-lookup"><span data-stu-id="d5318-164">View a specific account</span></span>

<span data-ttu-id="d5318-165">Per visualizzare un account utente specifico, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="d5318-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="d5318-166">Compilare il nome di accesso dell'account utente, noto anche come nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="d5318-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="d5318-167">Rimuovere i caratteri "<" e ">".</span><span class="sxs-lookup"><span data-stu-id="d5318-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="d5318-168">Visualizzare gli account in base a una proprietà comune</span><span class="sxs-lookup"><span data-stu-id="d5318-168">View accounts based on a common property</span></span>

<span data-ttu-id="d5318-169">Per essere più selettivi sull'elenco di account da visualizzare, è possibile utilizzare il cmdlet **Where** in combinazione con il cmdlet **Get-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="d5318-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="d5318-170">Per combinare i due cmdlet, utilizzare il carattere "pipe" ("|"), che indica a PowerShell di ottenere i risultati di un comando e inviarlo al comando successivo.</span><span class="sxs-lookup"><span data-stu-id="d5318-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="d5318-171">Ecco un esempio in cui vengono visualizzati solo gli account utente con un percorso di utilizzo non specificato:</span><span class="sxs-lookup"><span data-stu-id="d5318-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="d5318-172">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="d5318-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="d5318-173">Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d5318-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d5318-174">Trovare tutti gli account utente con un percorso di utilizzo non specificato (**Where {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="d5318-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="d5318-175">All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account per cui la proprietà dell'account utente UsageLocation (**$ \_ . UsageLocation**) non è specificato (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="d5318-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="d5318-176">È consigliabile ottenere informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5318-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="d5318-177">La proprietà *UsageLocation* è solo una delle tante associate a un account utente.</span><span class="sxs-lookup"><span data-stu-id="d5318-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="d5318-178">Per visualizzare tutte le proprietà per gli account utente, utilizzare il cmdlet **Select** e il carattere jolly (\*) per visualizzarle tutte per un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="d5318-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="d5318-179">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="d5318-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="d5318-180">*City* è il nome di una proprietà dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="d5318-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="d5318-181">È possibile utilizzare il comando seguente per elencare tutti gli account utente per gli utenti che vivono a Londra:</span><span class="sxs-lookup"><span data-stu-id="d5318-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="d5318-182">La sintassi del cmdlet **Where** in questi esempi è **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="d5318-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="d5318-183">[nome proprietà account utente] [operatore di confronto] [valore] **}**.</span><span class="sxs-lookup"><span data-stu-id="d5318-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="d5318-184">[operatore di confronto] è **-eq** per uguale a, **-ne** per diverso da, **-lt** per minore di, **-gt** per maggiore di e altri.</span><span class="sxs-lookup"><span data-stu-id="d5318-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="d5318-185">[valore] è in genere una stringa (una sequenza di lettere, numeri e altri caratteri), un valore numerico **o** $Null per non specificato.</span><span class="sxs-lookup"><span data-stu-id="d5318-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="d5318-186">Per ulteriori informazioni, vedere [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="d5318-186">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="d5318-187">Per verificare lo stato bloccato di un account utente, utilizzare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d5318-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="d5318-188">Visualizzare valori di proprietà aggiuntivi per gli account</span><span class="sxs-lookup"><span data-stu-id="d5318-188">View additional property values for accounts</span></span>

<span data-ttu-id="d5318-189">Per impostazione predefinita, il cmdlet **Get-MsolUser** visualizza queste tre proprietà degli account utente:</span><span class="sxs-lookup"><span data-stu-id="d5318-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="d5318-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="d5318-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="d5318-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d5318-191">DisplayName</span></span>
    
- <span data-ttu-id="d5318-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="d5318-192">isLicensed</span></span>
    
<span data-ttu-id="d5318-193">Se sono necessarie proprietà aggiuntive, ad esempio il reparto in cui lavora l'utente e il paese/area geografica in cui utilizzano i servizi di Microsoft 365, è possibile eseguire **Get-MsolUser** in combinazione con il cmdlet **Select** per specificare l'elenco delle proprietà dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="d5318-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="d5318-194">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="d5318-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="d5318-195">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="d5318-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="d5318-196">Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d5318-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d5318-197">Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo (**Selezionare DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="d5318-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="d5318-198">È consigliabile ottenere informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5318-198">You should get information similar to this:</span></span>
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

<span data-ttu-id="d5318-199">Il cmdlet **Select** consente di scegliere le proprietà da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="d5318-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="d5318-200">Per visualizzare tutte le proprietà di un account utente specifico, utilizzare il carattere jolly (\*).</span><span class="sxs-lookup"><span data-stu-id="d5318-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="d5318-201">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="d5318-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="d5318-202">Per essere più selettivi sull'elenco di account da visualizzare, è inoltre possibile utilizzare il cmdlet **Where.**</span><span class="sxs-lookup"><span data-stu-id="d5318-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="d5318-203">Ecco un comando di esempio che visualizza solo gli account utente con un percorso di utilizzo non specificato:</span><span class="sxs-lookup"><span data-stu-id="d5318-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="d5318-204">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="d5318-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="d5318-205">Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d5318-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d5318-206">Trovare tutti gli account utente con un percorso di utilizzo non specificato (**Where {$ \_ . UsageLocation -eq $Null}**) e inviare le informazioni risultanti al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d5318-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="d5318-207">All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account per cui la proprietà dell'account utente UsageLocation (**$ \_ . UsageLocation**) non è specificato (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="d5318-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="d5318-208">Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo (**Selezionare DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="d5318-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="d5318-209">È consigliabile ottenere informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5318-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="d5318-210">Se si utilizza la sincronizzazione della directory per creare e gestire gli utenti di Microsoft 365, è possibile visualizzare l'account locale da cui è stato proiettato un utente di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5318-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="d5318-211">Nell'esempio seguente si presuppone che:</span><span class="sxs-lookup"><span data-stu-id="d5318-211">The following example assumes that:</span></span>

- <span data-ttu-id="d5318-212">Azure AD Connect è configurato per usare l'ancoraggio di origine predefinito di ObjectGUID.</span><span class="sxs-lookup"><span data-stu-id="d5318-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="d5318-213">Per ulteriori informazioni sulla configurazione di un ancoraggio di origine, vedere [Azure AD Connect: Concetti di progettazione.](/azure/active-directory/hybrid/plan-connect-design-concepts)</span><span class="sxs-lookup"><span data-stu-id="d5318-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="d5318-214">Il modulo Servizi di dominio Active Directory per PowerShell è stato installato (vedere [Strumenti RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span><span class="sxs-lookup"><span data-stu-id="d5318-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="d5318-215">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5318-215">See also</span></span>

[<span data-ttu-id="d5318-216">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5318-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d5318-217">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5318-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d5318-218">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d5318-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)