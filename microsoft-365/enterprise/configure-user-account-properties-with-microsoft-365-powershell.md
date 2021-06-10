---
title: Configurare Microsoft 365 account utente con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Usare PowerShell per Microsoft 365 per configurare le proprietà di singoli o più account utente nel tenant Microsoft 365 tenant.
ms.openlocfilehash: 6b674641842f89fd8c8e22dc26350cdd53734b9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911085"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="63131-103">Configurare Microsoft 365 account utente con PowerShell</span><span class="sxs-lookup"><span data-stu-id="63131-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="63131-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="63131-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="63131-105">È possibile utilizzare l'Microsoft 365 di amministrazione per configurare le proprietà per gli account utente del tenant Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="63131-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="63131-106">In PowerShell è anche possibile eseguire questa operazione, oltre ad altre operazioni che non è possibile eseguire nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="63131-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="63131-107">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="63131-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="63131-108">Per configurare le proprietà per gli account utente nel modulo Azure Active Directory PowerShell per Graph, utilizzare il cmdlet [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) e specificare le proprietà da impostare o modificare.</span><span class="sxs-lookup"><span data-stu-id="63131-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="63131-109">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="63131-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="63131-110">Modificare le proprietà per un account utente specifico</span><span class="sxs-lookup"><span data-stu-id="63131-110">Change properties for a specific user account</span></span>

<span data-ttu-id="63131-111">È possibile identificare l'account con *il parametro -ObjectID* e impostare o modificare proprietà specifiche utilizzando parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="63131-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="63131-112">Ecco un elenco dei parametri più comuni:</span><span class="sxs-lookup"><span data-stu-id="63131-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="63131-113">-Department "\<department name>"</span><span class="sxs-lookup"><span data-stu-id="63131-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="63131-114">-DisplayName "\<full user name>"</span><span class="sxs-lookup"><span data-stu-id="63131-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="63131-115">-FacsimilieTelephoneNumber "\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="63131-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="63131-116">-GivenName "\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="63131-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="63131-117">-Surname "\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="63131-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="63131-118">-Mobile "\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="63131-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="63131-119">-JobTitle "\<job title>"</span><span class="sxs-lookup"><span data-stu-id="63131-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="63131-120">-PreferredLanguage "\<language>"</span><span class="sxs-lookup"><span data-stu-id="63131-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="63131-121">-StreetAddress "\<street address>"</span><span class="sxs-lookup"><span data-stu-id="63131-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="63131-122">-City "<nome città>"</span><span class="sxs-lookup"><span data-stu-id="63131-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="63131-123">-State "\<state name>"</span><span class="sxs-lookup"><span data-stu-id="63131-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="63131-124">-PostalCode "\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="63131-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="63131-125">-Country "\<country name>"</span><span class="sxs-lookup"><span data-stu-id="63131-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="63131-126">-TelephoneNumber "\<office phone number>"</span><span class="sxs-lookup"><span data-stu-id="63131-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="63131-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="63131-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="63131-128">Si tratta del codice paese o area geografica a due lettere ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="63131-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="63131-129">Per ulteriori parametri, vedere [Set-AzureADUser](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="63131-129">For additional parameters, see [Set-AzureADUser](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="63131-130">Prima di poter assegnare licenze a un account utente, è necessario assegnare una posizione di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="63131-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="63131-131">Per visualizzare il nome principale degli utenti per gli account utente, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="63131-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="63131-132">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="63131-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="63131-133">Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="63131-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="63131-134">Ordinare in ordine alfabetico l'elenco dei nomi delle entità utente (**Sort UserPrincipalName**) e inviarlo al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="63131-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="63131-135">Visualizzare solo la proprietà User Principal Name per ogni account (**Select UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="63131-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="63131-136">Visualizzare gli elementi in una schermata alla volta (**More**).</span><span class="sxs-lookup"><span data-stu-id="63131-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="63131-137">Per visualizzare il nome dell'entità utente per un account in base al nome visualizzato (nome e cognome), eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="63131-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="63131-138">Compilare la *$userName* e rimuovere i \< and > caratteri:</span><span class="sxs-lookup"><span data-stu-id="63131-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="63131-139">In questo esempio viene visualizzato il nome dell'entità utente per l'account utente con il nome visualizzato *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="63131-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="63131-140">Utilizzando una variabile *$upn*, è possibile apportare modifiche ai singoli account in base al nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="63131-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="63131-141">Ecco un esempio che imposta la posizione di utilizzo di *Belinda Newman* sulla Francia.</span><span class="sxs-lookup"><span data-stu-id="63131-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="63131-142">Ma specifica il nome visualizzato anziché il nome dell'entità utente:</span><span class="sxs-lookup"><span data-stu-id="63131-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="63131-143">Modificare le proprietà per tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="63131-143">Change properties for all user accounts</span></span>

<span data-ttu-id="63131-144">Per modificare le proprietà di tutti gli utenti, è possibile utilizzare una combinazione dei cmdlet **Get-AzureADUser** e **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="63131-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="63131-145">Nell'esempio seguente la posizione di utilizzo per tutti gli utenti viene modificata in *Francia:*</span><span class="sxs-lookup"><span data-stu-id="63131-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="63131-146">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="63131-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="63131-147">Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="63131-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="63131-148">Impostare la posizione utente su Francia (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="63131-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="63131-149">Modificare le proprietà per un set specifico di account utente</span><span class="sxs-lookup"><span data-stu-id="63131-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="63131-150">Per modificare le proprietà di un set specifico di account utente, è possibile utilizzare una combinazione dei cmdlet **Get-AzureADUser**, **Where** e **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="63131-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="63131-151">Nell'esempio seguente la posizione di utilizzo di tutti gli utenti del reparto Contabilità viene modificata in *Francia*:</span><span class="sxs-lookup"><span data-stu-id="63131-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="63131-152">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="63131-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="63131-153">Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="63131-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="63131-154">Trovare tutti gli account utente la cui *proprietà Department* è impostata su "Accounting" (**Where {$_. Department -eq "Accounting"}**) e inviare le informazioni risultanti al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="63131-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="63131-155">Impostare la posizione utente su Francia (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="63131-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="63131-156">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="63131-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="63131-157">Per configurare le proprietà per gli account utente con il modulo Microsoft Azure Active Directory per Windows PowerShell, utilizzare il cmdlet **Set-MsolUser** e specificare le proprietà da impostare o modificare.</span><span class="sxs-lookup"><span data-stu-id="63131-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="63131-158">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="63131-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="63131-159">PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="63131-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="63131-160">Eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="63131-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="63131-161">Modificare le proprietà per un account utente specifico</span><span class="sxs-lookup"><span data-stu-id="63131-161">Change properties for a specific user account</span></span>

<span data-ttu-id="63131-162">Per configurare le proprietà per un account utente specifico, utilizzare il cmdlet [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) e specificare le proprietà da impostare o modificare.</span><span class="sxs-lookup"><span data-stu-id="63131-162">To configure properties for a specific user account, use the [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="63131-163">È possibile identificare l'account con *il parametro -UserPrincipalName* e impostare o modificare proprietà specifiche utilizzando parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="63131-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="63131-164">Ecco un elenco dei parametri più comuni.</span><span class="sxs-lookup"><span data-stu-id="63131-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="63131-165">-City "<nome città>"</span><span class="sxs-lookup"><span data-stu-id="63131-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="63131-166">-Country "\<country name>"</span><span class="sxs-lookup"><span data-stu-id="63131-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="63131-167">-Department "\<department name>"</span><span class="sxs-lookup"><span data-stu-id="63131-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="63131-168">-DisplayName "\<full user name>"</span><span class="sxs-lookup"><span data-stu-id="63131-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="63131-169">-Fax "\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="63131-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="63131-170">-FirstName "\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="63131-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="63131-171">-LastName "\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="63131-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="63131-172">-MobilePhone "\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="63131-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="63131-173">-Office "\<office location>"</span><span class="sxs-lookup"><span data-stu-id="63131-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="63131-174">-PhoneNumber "\<office phone number>"</span><span class="sxs-lookup"><span data-stu-id="63131-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="63131-175">-PostalCode "\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="63131-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="63131-176">-PreferredLanguage "\<language>"</span><span class="sxs-lookup"><span data-stu-id="63131-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="63131-177">-State "\<state name>"</span><span class="sxs-lookup"><span data-stu-id="63131-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="63131-178">-StreetAddress "\<street address>"</span><span class="sxs-lookup"><span data-stu-id="63131-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="63131-179">-Title "\<title name>"</span><span class="sxs-lookup"><span data-stu-id="63131-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="63131-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="63131-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="63131-181">Si tratta del codice paese o area geografica a due lettere ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="63131-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="63131-182">Per ulteriori parametri, vedere [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="63131-182">For additional parameters, see [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="63131-183">Per visualizzare i nomi dell'entità utente di tutti gli utenti, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="63131-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="63131-184">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="63131-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="63131-185">Ottenere tutte le informazioni per gli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="63131-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="63131-186">Ordinare in ordine alfabetico l'elenco dei nomi delle entità utente (**Sort UserPrincipalName**) e inviarlo al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="63131-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="63131-187">Visualizzare solo la proprietà User Principal Name per ogni account (**Select UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="63131-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="63131-188">Visualizzare gli elementi in una schermata alla volta (**More**).</span><span class="sxs-lookup"><span data-stu-id="63131-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="63131-189">Per visualizzare il nome dell'entità utente per un account in base al nome visualizzato (nome e cognome), eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="63131-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="63131-190">Compilare la *$userName* e rimuovere i \< and > caratteri.</span><span class="sxs-lookup"><span data-stu-id="63131-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="63131-191">In questo esempio viene visualizzato il nome dell'entità utente per l'utente caleb sills:</span><span class="sxs-lookup"><span data-stu-id="63131-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="63131-192">Utilizzando una variabile *$upn*, è possibile apportare modifiche ai singoli account in base al nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="63131-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="63131-193">Ecco un esempio che imposta la posizione di utilizzo di *Belinda Newman* su *Francia,* ma specifica il nome visualizzato anziché il nome dell'entità utente:</span><span class="sxs-lookup"><span data-stu-id="63131-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="63131-194">Modificare le proprietà per tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="63131-194">Change properties for all user accounts</span></span>

<span data-ttu-id="63131-195">Per modificare le proprietà di tutti gli utenti, utilizzare una combinazione dei cmdlet **Get-MsolUser** **e Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="63131-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="63131-196">Nell'esempio seguente la posizione di utilizzo per tutti gli utenti viene modificata in *Francia:*</span><span class="sxs-lookup"><span data-stu-id="63131-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="63131-197">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="63131-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="63131-198">Ottenere tutte le informazioni per gli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="63131-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="63131-199">Impostare la posizione utente su Francia (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="63131-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="63131-200">Modificare le proprietà per un set specifico di account utente</span><span class="sxs-lookup"><span data-stu-id="63131-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="63131-201">Per modificare le proprietà di un set specifico di account utente, è possibile utilizzare una combinazione dei cmdlet **Get-MsolUser**, **Where** e **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="63131-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="63131-202">Nell'esempio seguente la posizione di utilizzo di tutti gli utenti del reparto Contabilità viene modificata in *Francia*:</span><span class="sxs-lookup"><span data-stu-id="63131-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="63131-203">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="63131-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="63131-204">Ottenere tutte le informazioni per gli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="63131-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="63131-205">Trovare tutti gli account utente la cui *proprietà Department* è impostata su "Accounting" (**Where {$_. Department -eq "Accounting"}**) e inviare le informazioni risultanti al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="63131-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="63131-206">Impostare la posizione utente su Francia (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="63131-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="63131-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63131-207">See also</span></span>

[<span data-ttu-id="63131-208">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="63131-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="63131-209">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="63131-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="63131-210">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="63131-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)