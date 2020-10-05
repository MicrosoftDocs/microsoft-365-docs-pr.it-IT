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
ms.openlocfilehash: 4dba05ce440ec0d395fda58a12df3e9f751bb469
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357899"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="56dd6-103">Visualizzare gli account utente di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="56dd6-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="56dd6-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="56dd6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="56dd6-105">Anche se è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per visualizzare gli account per il tenant di Microsoft 365, è anche possibile utilizzare PowerShell per Microsoft 365 e fare alcuni elementi che l'interfaccia di amministrazione non è in grado di eseguire.</span><span class="sxs-lookup"><span data-stu-id="56dd6-105">Although you can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant, you can also use PowerShell for Microsoft 365 and do some things that the admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="56dd6-106">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="56dd6-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="56dd6-107">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="56dd6-107">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="56dd6-108">Visualizzazione di tutti gli account</span><span class="sxs-lookup"><span data-stu-id="56dd6-108">View all accounts</span></span>

<span data-ttu-id="56dd6-109">Per visualizzare l'elenco completo degli account utente, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="56dd6-109">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="56dd6-110">Dovrebbero essere visualizzate informazioni analoghe alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="56dd6-110">You should see information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="56dd6-111">Visualizzazione di un account specifico</span><span class="sxs-lookup"><span data-stu-id="56dd6-111">View a specific account</span></span>

<span data-ttu-id="56dd6-112">Per visualizzare un account utente specifico, inserire il nome account di accesso dell'account utente, noto anche come nome dell'entità utente (UPN), rimuovere i caratteri "<" e ">" ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="56dd6-112">To display a specific user account, fill in the sign-in account name of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="56dd6-113">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="56dd6-113">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="56dd6-114">Visualizzare i valori di proprietà aggiuntivi per un account specifico</span><span class="sxs-lookup"><span data-stu-id="56dd6-114">View additional property values for a specific account</span></span>

<span data-ttu-id="56dd6-115">Per impostazione predefinita, il cmdlet **Get-AzureADUser** consente di visualizzare solo le proprietà ObjectID, DisplayName e userPrincipalName degli account.</span><span class="sxs-lookup"><span data-stu-id="56dd6-115">By default, the **Get-AzureADUser** cmdlet only displays the ObjectID, DisplayName, and UserPrincipalName properties of accounts.</span></span>

<span data-ttu-id="56dd6-116">Per essere più selettivi sull'elenco delle proprietà da visualizzare, è possibile utilizzare il cmdlet **Select** in combinazione con il cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="56dd6-116">To be more selective about the list of properties to display, you can use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="56dd6-117">Per combinare i due cmdlet, viene utilizzato il carattere "pipe" "|", che indica a Azure Active Directory PowerShell per Graph di prendere i risultati di un comando e inviarlo al comando successivo.</span><span class="sxs-lookup"><span data-stu-id="56dd6-117">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="56dd6-118">Di seguito è riportato un comando di esempio che consente di visualizzare il DisplayName, il reparto e UsageLocation per ogni account utente:</span><span class="sxs-lookup"><span data-stu-id="56dd6-118">Here is an example command that displays the DisplayName, Department, and UsageLocation for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="56dd6-119">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="56dd6-119">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="56dd6-120">Accedere a tutte le informazioni degli account utente ( **Get-AzureADUser** ) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-120">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="56dd6-121">Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo ( **selezionare DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-121">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
  
<span data-ttu-id="56dd6-122">Per visualizzare tutte le proprietà degli account utente, utilizzare il cmdlet **Select** e il carattere jolly (\*) per visualizzarli tutti per un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="56dd6-122">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="56dd6-123">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="56dd6-123">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="56dd6-124">Come un altro esempio, è possibile controllare lo stato abilitato di un account utente specifico con il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="56dd6-124">As another example, you can check the enabled status of a specific user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="56dd6-125">Visualizzare lo stato di sincronizzazione dell'account</span><span class="sxs-lookup"><span data-stu-id="56dd6-125">View account synchronization status</span></span>

<span data-ttu-id="56dd6-126">Gli account utente dispongono di due origini; Windows Server Active Directory (AD), ovvero account sincronizzati dall'annuncio locale al cloud e AD Azure AD, che sono account creati direttamente nel cloud.</span><span class="sxs-lookup"><span data-stu-id="56dd6-126">User accounts have two sources; Windows Server Active Directory (AD) which are accounts that sync from on-premises AD to the cloud and Azure AD which are accounts directly created in the cloud.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```
<span data-ttu-id="56dd6-127">Questo comando indica a PowerShell di ottenere tutti gli utenti che dispongono dell'attributo **DirSyncEnabled** impostato su true.</span><span class="sxs-lookup"><span data-stu-id="56dd6-127">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to True.</span></span> <span data-ttu-id="56dd6-128">Può essere utilizzato per recuperare gli account sincronizzati dall'annuncio locale.</span><span class="sxs-lookup"><span data-stu-id="56dd6-128">It can be used to pull up accounts synchronizing from on-premise AD.</span></span>


```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $true}
```
<span data-ttu-id="56dd6-129">Questo comando indica a PowerShell di ottenere tutti gli utenti il cui attributo **DirSyncEnabled** è impostato su false.</span><span class="sxs-lookup"><span data-stu-id="56dd6-129">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to False.</span></span> <span data-ttu-id="56dd6-130">Può essere utilizzato per recuperare gli account solo cloud.</span><span class="sxs-lookup"><span data-stu-id="56dd6-130">It can be used to pull up cloud-only accounts.</span></span>

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="56dd6-131">Visualizzare alcuni account basati su una proprietà comune</span><span class="sxs-lookup"><span data-stu-id="56dd6-131">View some accounts based on a common property</span></span>

<span data-ttu-id="56dd6-132">Per essere più selettivi sull'elenco degli account da visualizzare, è possibile utilizzare il cmdlet **where** in combinazione con il cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="56dd6-132">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="56dd6-133">Per combinare i due cmdlet, viene utilizzato il carattere "pipe" "|", che indica a Azure Active Directory PowerShell per Graph di prendere i risultati di un comando e inviarlo al comando successivo.</span><span class="sxs-lookup"><span data-stu-id="56dd6-133">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="56dd6-134">Ecco un comando di esempio che visualizza soltanto gli account utente con un percorso di utilizzo non specificato:</span><span class="sxs-lookup"><span data-stu-id="56dd6-134">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="56dd6-135">Questo comando indica a Azure Active Directory PowerShell per Graph di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="56dd6-135">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
- <span data-ttu-id="56dd6-136">Accedere a tutte le informazioni degli account utente ( **Get-AzureADUser** ) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-136">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="56dd6-137">Individuare tutti gli account utente che dispongono di una posizione di utilizzo non specificata ( **dove {$ \_ . UsageLocation-eq $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-137">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="56dd6-138">All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account in cui la proprietà dell'account utente di UsageLocation ( \*\* $ \_ . UsageLocation\*\* ) non è specificato ( **-eq $null** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-138">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="56dd6-139">La proprietà **UsageLocation** è solo una delle tante associate a un account utente.</span><span class="sxs-lookup"><span data-stu-id="56dd6-139">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="56dd6-140">Per visualizzare tutte le proprietà degli account utente, utilizzare il cmdlet **Select** e il carattere jolly (\*) per visualizzarli tutti per un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="56dd6-140">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="56dd6-141">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="56dd6-141">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="56dd6-p108">In questo elenco, **City** è il nome di una proprietà dell'account utente. Questo significa che è possibile usare il comando seguente per elencare tutti gli account degli utenti che vivono a Londra:</span><span class="sxs-lookup"><span data-stu-id="56dd6-p108">For example, from this list, **City** is the name of a user account property. This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="56dd6-144">La sintassi del cmdlet **where** mostrato in questi esempi è **dove {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="56dd6-144">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="56dd6-145">[nome della proprietà dell'account utente] [operatore di confronto] valore **}**. > [operatore di confronto] è **-EQ** per Equals, **-ne** per non uguale a, **-lt** per meno di, **-gt** per maggiore di e altri.</span><span class="sxs-lookup"><span data-stu-id="56dd6-145">[user account property name] [comparison operator] [value] **}**.>  [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="56dd6-146">[valore] è in genere una stringa (una sequenza di lettere, numeri e altri caratteri), un valore numerico o **$null** per> non specificati vedere [dove](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="56dd6-146">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified>  See [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) for more information.</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="56dd6-147">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56dd6-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="56dd6-148">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="56dd6-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="56dd6-149">Visualizzazione di tutti gli account</span><span class="sxs-lookup"><span data-stu-id="56dd6-149">View all accounts</span></span>

<span data-ttu-id="56dd6-150">Per visualizzare l'elenco completo degli account utente, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="56dd6-150">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="56dd6-151">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="56dd6-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="56dd6-152">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56dd6-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="56dd6-153">Dovrebbero essere visualizzate informazioni analoghe alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="56dd6-153">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="56dd6-154">Il cmdlet **Get-MsolUser** dispone inoltre di un set di parametri per filtrare il gruppo di account utente visualizzato.</span><span class="sxs-lookup"><span data-stu-id="56dd6-154">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="56dd6-155">Ad esempio, per l'elenco degli utenti senza licenza (gli utenti che sono stati aggiunti a Microsoft 365 ma non sono stati ancora autorizzati a utilizzare uno qualsiasi dei servizi), eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="56dd6-155">For example, for the list of unlicensed users (users who've been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command.</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="56dd6-156">Dovrebbero essere visualizzate informazioni analoghe alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="56dd6-156">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="56dd6-157">Per ulteriori informazioni sui parametri aggiuntivi per filtrare la visualizzazione del set di account utente visualizzato, vedere [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="56dd6-157">For more information about additional parameters to filter the display the set of user accounts displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="56dd6-158">Visualizzazione di un account specifico</span><span class="sxs-lookup"><span data-stu-id="56dd6-158">View a specific account</span></span>

<span data-ttu-id="56dd6-159">Per visualizzare un account utente specifico, inserire il nome di accesso dell'account utente dell'account utente, noto anche come nome dell'entità utente (UPN), rimuovere i caratteri "<" e ">" ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="56dd6-159">To display a specific user account, fill in the sign-in name of the user account of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="56dd6-160">Visualizzare alcuni account basati su una proprietà comune</span><span class="sxs-lookup"><span data-stu-id="56dd6-160">View some accounts based on a common property</span></span>

<span data-ttu-id="56dd6-161">Per essere più selettivi sull'elenco degli account da visualizzare, è possibile utilizzare il cmdlet **where** in combinazione con il cmdlet **Get-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="56dd6-161">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="56dd6-162">Per combinare i due cmdlet, viene utilizzato il carattere "pipe" "|", che indica a PowerShell di prendere i risultati di un comando e inviarlo al comando successivo.</span><span class="sxs-lookup"><span data-stu-id="56dd6-162">To combine the two cmdlets, we use the "pipe" character "|", which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="56dd6-163">Ecco un comando di esempio che visualizza soltanto gli account utente con un percorso di utilizzo non specificato:</span><span class="sxs-lookup"><span data-stu-id="56dd6-163">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="56dd6-164">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="56dd6-164">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="56dd6-165">Accedere a tutte le informazioni degli account utente ( **Get-MsolUser** ) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-165">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="56dd6-166">Individuare tutti gli account utente che dispongono di una posizione di utilizzo non specificata ( **dove {$ \_ . UsageLocation-eq $Null}** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-166">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="56dd6-167">All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account in cui la proprietà dell'account utente di UsageLocation ( \*\* $ \_ . UsageLocation\*\* ) non è specificato ( **-eq $null** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-167">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="56dd6-168">Dovrebbero essere visualizzate informazioni analoghe alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="56dd6-168">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="56dd6-169">La proprietà **UsageLocation** è solo una delle tante associate a un account utente.</span><span class="sxs-lookup"><span data-stu-id="56dd6-169">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="56dd6-170">Per visualizzare tutte le proprietà degli account utente, utilizzare il cmdlet **Select** e il carattere jolly (\*) per visualizzarli tutti per un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="56dd6-170">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="56dd6-171">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="56dd6-171">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="56dd6-p115">In questo elenco, **City** è il nome di una proprietà dell'account utente. Questo significa che è possibile usare il comando seguente per elencare tutti gli account degli utenti che vivono a Londra:</span><span class="sxs-lookup"><span data-stu-id="56dd6-p115">For example, from this list, **City** is the name of a user account property. This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="56dd6-174">La sintassi del cmdlet **where** mostrato in questi esempi è **dove {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="56dd6-174">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="56dd6-175">[nome della proprietà dell'account utente] [operatore di confronto] valore **}**.</span><span class="sxs-lookup"><span data-stu-id="56dd6-175">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="56dd6-176">[operatore di confronto] è **-EQ** per Equals, **-ne** per non uguale a, **-lt** per meno di, **-gt** per maggiore di e altri.</span><span class="sxs-lookup"><span data-stu-id="56dd6-176">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="56dd6-177">[valore] è in genere una stringa, ovvero una sequenza di lettere, numeri e altri caratteri, un valore numerico o **$null** per Unspecified.</span><span class="sxs-lookup"><span data-stu-id="56dd6-177">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="56dd6-178">Vedere [dove](https://technet.microsoft.com/library/hh849715.aspx) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="56dd6-178">See [Where](https://technet.microsoft.com/library/hh849715.aspx) for more information.</span></span>
  
<span data-ttu-id="56dd6-179">È possibile controllare lo stato bloccato di un account utente con il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="56dd6-179">You can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="56dd6-180">Visualizzare i valori di proprietà aggiuntivi per gli account</span><span class="sxs-lookup"><span data-stu-id="56dd6-180">View additional property values for accounts</span></span>

<span data-ttu-id="56dd6-181">Il cmdlet **Get-MsolUser** per impostazione predefinita visualizza tre proprietà degli account utente:</span><span class="sxs-lookup"><span data-stu-id="56dd6-181">The **Get-MsolUser** cmdlet by default displays three properties of user accounts:</span></span>
  
- <span data-ttu-id="56dd6-182">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="56dd6-182">UserPrincipalName</span></span>
    
- <span data-ttu-id="56dd6-183">DisplayName</span><span class="sxs-lookup"><span data-stu-id="56dd6-183">DisplayName</span></span>
    
- <span data-ttu-id="56dd6-184">isLicensed</span><span class="sxs-lookup"><span data-stu-id="56dd6-184">isLicensed</span></span>
    
<span data-ttu-id="56dd6-185">Se sono necessarie ulteriori proprietà, ad esempio il reparto utilizzato dall'utente e il paese/area geografica in cui l'utente utilizza i servizi Microsoft 365, è possibile eseguire **Get-MsolUser** in combinazione con il cmdlet **SELECT** per specificare l'elenco delle proprietà degli account utente.</span><span class="sxs-lookup"><span data-stu-id="56dd6-185">If you need additional properties, such as the department the user works for and the country/region where the user uses Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="56dd6-186">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="56dd6-186">Here is an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="56dd6-187">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="56dd6-187">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="56dd6-188">Accedere a tutte le informazioni degli account utente ( **Get-MsolUser** ) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-188">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="56dd6-189">Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo ( **selezionare DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-189">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="56dd6-190">Dovrebbero essere visualizzate informazioni analoghe alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="56dd6-190">You should see information similar to this:</span></span>
  
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

<span data-ttu-id="56dd6-191">Il cmdlet **Select** consente di scegliere le proprietà che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="56dd6-191">The **Select** cmdlet lets you pick and choose the properties you want a command to display.</span></span> <span data-ttu-id="56dd6-192">Per visualizzare tutte le proprietà degli account utente, utilizzare il carattere jolly (\*) per visualizzarle tutte per un account utente specifico.</span><span class="sxs-lookup"><span data-stu-id="56dd6-192">To see all of the properties for user accounts, use the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="56dd6-193">Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="56dd6-193">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="56dd6-194">Per essere più selettivi sull'elenco degli account da visualizzare, è anche possibile utilizzare il cmdlet **where** .</span><span class="sxs-lookup"><span data-stu-id="56dd6-194">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="56dd6-195">Ecco un comando di esempio che visualizza soltanto gli account utente con un percorso di utilizzo non specificato:</span><span class="sxs-lookup"><span data-stu-id="56dd6-195">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="56dd6-196">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="56dd6-196">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="56dd6-197">Accedere a tutte le informazioni degli account utente ( **Get-MsolUser** ) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-197">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="56dd6-198">Individuare tutti gli account utente che dispongono di una posizione di utilizzo non specificata ( **dove {$ \_ . UsageLocation-eq $Null}** ) e inviare le informazioni risultanti al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-198">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ) and send the resulting information to the next command ( **|** ).</span></span> <span data-ttu-id="56dd6-199">All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account in cui la proprietà dell'account utente di UsageLocation ( \*\* $ \_ . UsageLocation\*\* ) non è specificato ( **-eq $null** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-199">Inside the braces, the command is instructing PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
- <span data-ttu-id="56dd6-200">Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo ( **selezionare DisplayName, Department, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="56dd6-200">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="56dd6-201">Dovrebbero essere visualizzate informazioni analoghe alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="56dd6-201">You should see information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="56dd6-202">Se si utilizza la sincronizzazione della directory per creare e gestire gli utenti di Microsoft 365, è possibile visualizzare l'account locale da cui è stato progettato un utente di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56dd6-202">If you are using directory synchronization to create and manage your Microsoft 365 users, you can display which local account a Microsoft 365 user has been projected from.</span></span> <span data-ttu-id="56dd6-203">Di seguito si presuppone che Azure AD Connect sia stato configurato per l'utilizzo dell'ancoraggio di origine predefinito di ObjectGUID (per ulteriori informazioni sulla configurazione di un ancoraggio di origine, vedere [Azure ad Connect: Design Concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) e presuppone che sia stato installato il modulo servizi di dominio Active Directory per PowerShell (vedere [strumenti di amministrazione remota](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span><span class="sxs-lookup"><span data-stu-id="56dd6-203">The following assumes that Azure AD Connect has been configured to use the default source anchor of ObjectGUID (for more on configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) and assumes that the Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="56dd6-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56dd6-204">See also</span></span>

[<span data-ttu-id="56dd6-205">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="56dd6-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="56dd6-206">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="56dd6-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="56dd6-207">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56dd6-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
