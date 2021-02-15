---
title: Configurare le proprietà dell'account utente di Microsoft 365 con PowerShell
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
description: Usare PowerShell per Microsoft 365 per configurare le proprietà di uno o più account utente nel tenant di Microsoft 365.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754329"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="14a6c-103">Configurare le proprietà dell'account utente di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="14a6c-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="14a6c-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="14a6c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="14a6c-105">È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per configurare le proprietà per gli account utente del tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14a6c-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="14a6c-106">In PowerShell, è anche possibile eseguire questa operazione, oltre ad altre operazioni che non è possibile eseguire nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="14a6c-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="14a6c-107">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="14a6c-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="14a6c-108">Per configurare le proprietà per gli account utente nel modulo Azure Active Directory PowerShell per Graph, utilizzare il cmdlet [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) e specificare le proprietà da impostare o modificare.</span><span class="sxs-lookup"><span data-stu-id="14a6c-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="14a6c-109">Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="14a6c-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="14a6c-110">Modificare le proprietà per un account utente specifico</span><span class="sxs-lookup"><span data-stu-id="14a6c-110">Change properties for a specific user account</span></span>

<span data-ttu-id="14a6c-111">È possibile identificare l'account con *il parametro -ObjectID* e impostare o modificare proprietà specifiche utilizzando parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="14a6c-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="14a6c-112">Ecco un elenco dei parametri più comuni:</span><span class="sxs-lookup"><span data-stu-id="14a6c-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="14a6c-113">-Department "\<department name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="14a6c-114">-DisplayName "\<full user name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="14a6c-115">-FacsimilieTelephoneNumber "\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="14a6c-116">-GivenName "\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="14a6c-117">-Surname "\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="14a6c-118">-Mobile "\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="14a6c-119">-JobTitle "\<job title>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="14a6c-120">-PreferredLanguage "\<language>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="14a6c-121">-StreetAddress "\<street address>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="14a6c-122">-City "<nome città>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="14a6c-123">-State "\<state name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="14a6c-124">-PostalCode "\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="14a6c-125">-Country "\<country name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="14a6c-126">-TelephoneNumber "\<office phone number>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="14a6c-127">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="14a6c-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="14a6c-128">Si tratta del codice paese o area geografica a due lettere ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="14a6c-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="14a6c-129">Per ulteriori parametri, vedere [Set-AzureADUser.](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="14a6c-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="14a6c-130">Prima di poter assegnare licenze a un account utente, è necessario assegnare una posizione di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="14a6c-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="14a6c-131">Per visualizzare il nome principale degli utenti per gli account utente, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="14a6c-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="14a6c-132">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="14a6c-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="14a6c-133">Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="14a6c-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="14a6c-134">Ordinare l'elenco dei nomi dell'entità utente in ordine alfabetico (**Sort UserPrincipalName**) e inviarlo al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="14a6c-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="14a6c-135">Visualizzare solo la proprietà User Principal Name per ogni account (**Select UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="14a6c-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="14a6c-136">Visualizzare gli elementi in una schermata alla volta (**More**).</span><span class="sxs-lookup"><span data-stu-id="14a6c-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="14a6c-137">Per visualizzare il nome dell'entità utente per un account in base al nome visualizzato (nome e cognome), eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="14a6c-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="14a6c-138">Compilare la *$userName* e rimuovere i \< and > caratteri:</span><span class="sxs-lookup"><span data-stu-id="14a6c-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="14a6c-139">In questo esempio viene visualizzato il nome dell'entità utente per l'account utente con nome visualizzato *Caleb Sills.*</span><span class="sxs-lookup"><span data-stu-id="14a6c-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="14a6c-140">Utilizzando una variabile *$upn*, è possibile apportare modifiche ai singoli account in base al nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="14a6c-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="14a6c-141">Ecco un esempio che imposta la posizione di utilizzo di *Belinda Newman* sulla Francia.</span><span class="sxs-lookup"><span data-stu-id="14a6c-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="14a6c-142">Tuttavia, specifica il nome visualizzato anziché il nome dell'entità utente:</span><span class="sxs-lookup"><span data-stu-id="14a6c-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="14a6c-143">Modificare le proprietà per tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="14a6c-143">Change properties for all user accounts</span></span>

<span data-ttu-id="14a6c-144">Per modificare le proprietà di tutti gli utenti, è possibile utilizzare una combinazione dei cmdlet **Get-AzureADUser** e **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="14a6c-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="14a6c-145">Nell'esempio seguente la posizione di utilizzo di tutti gli utenti viene modificata in *Francia:*</span><span class="sxs-lookup"><span data-stu-id="14a6c-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="14a6c-146">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="14a6c-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="14a6c-147">Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="14a6c-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="14a6c-148">Impostare la posizione dell'utente su Francia (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="14a6c-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="14a6c-149">Modificare le proprietà per un set specifico di account utente</span><span class="sxs-lookup"><span data-stu-id="14a6c-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="14a6c-150">Per modificare le proprietà di un set specifico di account utente, è possibile utilizzare una combinazione dei cmdlet **Get-AzureADUser**, **Where** e **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="14a6c-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="14a6c-151">Nell'esempio seguente la posizione di utilizzo di tutti gli utenti del reparto Contabilità viene modificata in *Francia:*</span><span class="sxs-lookup"><span data-stu-id="14a6c-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="14a6c-152">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="14a6c-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="14a6c-153">Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="14a6c-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="14a6c-154">Trovare tutti gli account utente la cui proprietà *Department* è impostata su "Accounting" (**Where {$_. Department -eq "Accounting"}**) e inviare le informazioni risultanti al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="14a6c-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="14a6c-155">Impostare la posizione dell'utente su Francia (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="14a6c-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="14a6c-156">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14a6c-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="14a6c-157">Per configurare le proprietà per gli account utente con il modulo di Microsoft Azure Active Directory per Windows PowerShell, utilizzare il cmdlet **Set-MsolUser** e specificare le proprietà da impostare o modificare.</span><span class="sxs-lookup"><span data-stu-id="14a6c-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="14a6c-158">Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="14a6c-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="14a6c-159">PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="14a6c-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="14a6c-160">Eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14a6c-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="14a6c-161">Modificare le proprietà per un account utente specifico</span><span class="sxs-lookup"><span data-stu-id="14a6c-161">Change properties for a specific user account</span></span>

<span data-ttu-id="14a6c-162">Per configurare le proprietà per un account utente specifico, utilizzare il cmdlet [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) e specificare le proprietà da impostare o modificare.</span><span class="sxs-lookup"><span data-stu-id="14a6c-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="14a6c-163">È possibile identificare l'account con *il parametro -UserPrincipalName* e impostare o modificare proprietà specifiche utilizzando parametri aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="14a6c-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="14a6c-164">Ecco un elenco dei parametri più comuni.</span><span class="sxs-lookup"><span data-stu-id="14a6c-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="14a6c-165">-City "<nome città>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="14a6c-166">-Country "\<country name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="14a6c-167">-Department "\<department name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="14a6c-168">-DisplayName "\<full user name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="14a6c-169">-Fax "\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="14a6c-170">-FirstName "\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="14a6c-171">-LastName "\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="14a6c-172">-MobilePhone "\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="14a6c-173">-Office "\<office location>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="14a6c-174">-PhoneNumber "\<office phone number>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="14a6c-175">-PostalCode "\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="14a6c-176">-PreferredLanguage "\<language>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="14a6c-177">-State "\<state name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="14a6c-178">-StreetAddress "\<street address>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="14a6c-179">-Title "\<title name>"</span><span class="sxs-lookup"><span data-stu-id="14a6c-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="14a6c-180">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="14a6c-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="14a6c-181">Si tratta del codice paese o area geografica a due lettere ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="14a6c-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="14a6c-182">Per ulteriori parametri, vedere [Set-MsolUser.](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="14a6c-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="14a6c-183">Per visualizzare i nomi dell'entità utente di tutti gli utenti, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="14a6c-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="14a6c-184">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="14a6c-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="14a6c-185">Ottenere tutte le informazioni per gli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="14a6c-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="14a6c-186">Ordinare l'elenco dei nomi dell'entità utente in ordine alfabetico (**Sort UserPrincipalName**) e inviarlo al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="14a6c-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="14a6c-187">Visualizzare solo la proprietà User Principal Name per ogni account (**Select UserPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="14a6c-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="14a6c-188">Visualizzare gli elementi in una schermata alla volta (**More**).</span><span class="sxs-lookup"><span data-stu-id="14a6c-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="14a6c-189">Per visualizzare il nome dell'entità utente per un account in base al nome visualizzato (nome e cognome), eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="14a6c-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="14a6c-190">Compilare la *$userName* e rimuovere i \< and > caratteri.</span><span class="sxs-lookup"><span data-stu-id="14a6c-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="14a6c-191">In questo esempio viene visualizzato il nome dell'entità utente per l'utente Caleb Sills:</span><span class="sxs-lookup"><span data-stu-id="14a6c-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="14a6c-192">Utilizzando una variabile *$upn*, è possibile apportare modifiche ai singoli account in base al nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="14a6c-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="14a6c-193">Ecco un esempio che imposta la posizione di utilizzo di *Belinda Newman* sulla *Francia,* ma specifica il nome visualizzato anziché il nome dell'entità utente:</span><span class="sxs-lookup"><span data-stu-id="14a6c-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="14a6c-194">Modificare le proprietà per tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="14a6c-194">Change properties for all user accounts</span></span>

<span data-ttu-id="14a6c-195">Per modificare le proprietà di tutti gli utenti, utilizzare una combinazione dei cmdlet **Get-MsolUser** e **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="14a6c-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="14a6c-196">Nell'esempio seguente la posizione di utilizzo di tutti gli utenti viene modificata in *Francia:*</span><span class="sxs-lookup"><span data-stu-id="14a6c-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="14a6c-197">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="14a6c-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="14a6c-198">Ottenere tutte le informazioni per gli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="14a6c-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="14a6c-199">Impostare la posizione dell'utente su Francia (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="14a6c-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="14a6c-200">Modificare le proprietà per un set specifico di account utente</span><span class="sxs-lookup"><span data-stu-id="14a6c-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="14a6c-201">Per modificare le proprietà di un set specifico di account utente, è possibile utilizzare una combinazione dei cmdlet **Get-MsolUser**, **Where** e **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="14a6c-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="14a6c-202">Nell'esempio seguente la posizione di utilizzo di tutti gli utenti del reparto Contabilità viene modificata in *Francia:*</span><span class="sxs-lookup"><span data-stu-id="14a6c-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="14a6c-203">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="14a6c-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="14a6c-204">Ottenere tutte le informazioni per gli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="14a6c-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="14a6c-205">Trovare tutti gli account utente la cui proprietà *Department* è impostata su "Accounting" (**Where {$_. Department -eq "Accounting"}**) e inviare le informazioni risultanti al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="14a6c-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="14a6c-206">Impostare la posizione dell'utente su Francia (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="14a6c-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="14a6c-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14a6c-207">See also</span></span>

[<span data-ttu-id="14a6c-208">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="14a6c-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="14a6c-209">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="14a6c-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="14a6c-210">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14a6c-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
