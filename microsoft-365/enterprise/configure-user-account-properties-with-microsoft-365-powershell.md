---
title: Configurare le proprietà degli account utente di Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
description: 'Riepilogo: utilizzare PowerShell per Microsoft 365 per configurare le proprietà di singoli o più account utente nel tenant di Microsoft 365.'
ms.openlocfilehash: 6a435b3981efa8d8c2be7f6d983a1d062237f0db
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690916"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="bd717-103">Configurare le proprietà degli account utente di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd717-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="bd717-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="bd717-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bd717-105">Anche se è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per configurare le proprietà per gli account utente del tenant di Microsoft 365, è anche possibile utilizzare PowerShell e fare alcuni elementi che possono essere configurati dal centro di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd717-105">Although you can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant, you can also use PowerShell and do some things that the Microsoft 365 admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="bd717-106">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="bd717-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="bd717-107">Per configurare le proprietà degli account utente con il modulo Azure Active Directory PowerShell per Graph, utilizzare il cmdlet [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) e specificare le proprietà da impostare o modificare.</span><span class="sxs-lookup"><span data-stu-id="bd717-107">To configure properties for user accounts with the Azure Active Directory PowerShell for Graph module, you use the [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="bd717-108">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="bd717-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="bd717-109">Modificare le proprietà per un account utente specifico</span><span class="sxs-lookup"><span data-stu-id="bd717-109">Change properties for a specific user account</span></span>

<span data-ttu-id="bd717-p101">Identificare l'account con il parametro **-ObjectID** e impostare o modificare proprietà specifiche con ulteriori parametri. Ecco un elenco dei parametri più comuni.</span><span class="sxs-lookup"><span data-stu-id="bd717-p101">You identify the account with the **-ObjectID** parameter and set or change specific properties with additional parameters. Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="bd717-112">-Department "\<department name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-112">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="bd717-113">-DisplayName "\<full user name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-113">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="bd717-114">-FacsimilieTelephoneNumber "\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="bd717-114">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="bd717-115">-GivenName "\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-115">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="bd717-116">-Surname "\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-116">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="bd717-117">-Mobile "\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="bd717-117">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="bd717-118">-JobTitle "\<job title>"</span><span class="sxs-lookup"><span data-stu-id="bd717-118">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="bd717-119">-PreferredLanguage "\<language>"</span><span class="sxs-lookup"><span data-stu-id="bd717-119">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="bd717-120">-StreetAddress "\<street address>"</span><span class="sxs-lookup"><span data-stu-id="bd717-120">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="bd717-121">-City "<nome città>"</span><span class="sxs-lookup"><span data-stu-id="bd717-121">-City "\<city name>"</span></span>
    
- <span data-ttu-id="bd717-122">-State "\<state name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-122">-State "\<state name>"</span></span>
    
- <span data-ttu-id="bd717-123">-PostalCode "\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="bd717-123">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="bd717-124">-Country "\<country name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-124">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="bd717-125">-TelephoneNumber "\<office phone number>"</span><span class="sxs-lookup"><span data-stu-id="bd717-125">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="bd717-126">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="bd717-126">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="bd717-127">Si tratta del codice paese o area geografica a due lettere ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="bd717-127">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="bd717-128">Per ulteriori parametri, vedere [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="bd717-128">See [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) for additional parameters.</span></span>


<span data-ttu-id="bd717-129">Per visualizzare il nome principale degli utenti per gli account utente, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="bd717-129">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="bd717-130">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="bd717-130">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bd717-131">Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bd717-131">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bd717-132">Ordinare l'elenco dei nomi delle entità utente in ordine alfabetico (**Sort userPrincipalName**) e inviarlo al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bd717-132">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bd717-133">Visualizzare solo la proprietà del nome dell'entità utente per ogni account (**selezionare userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="bd717-133">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

- <span data-ttu-id="bd717-134">Visualizzare gli elementi in una schermata alla volta (**More**).</span><span class="sxs-lookup"><span data-stu-id="bd717-134">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="bd717-135">Con questo comando vengono elencati tutti gli account.</span><span class="sxs-lookup"><span data-stu-id="bd717-135">This command will list all of your accounts.</span></span> <span data-ttu-id="bd717-136">Se si desidera visualizzare il nome dell'entità utente per un account in base al nome visualizzato (nome e cognome), inserire la variabile **$username** in basso (rimozione dei \< and > caratteri), quindi eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd717-136">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bd717-137">Questo esempio permette di visualizzare il nome dell’entità utente per l’account utente con nome visualizzato Caleb Sillis.</span><span class="sxs-lookup"><span data-stu-id="bd717-137">This example displays the User Principal Name for the user account with the display name of Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bd717-p103">Utilizzando una variabile **$upn**, è possibile apportare modifiche ai singoli account in base al nome visualizzato. Ecco un esempio di impostazione della posizione di utilizzo di Belinda Newman in Francia, specificando il nome visualizzato anziché il nome principale dell'utente:</span><span class="sxs-lookup"><span data-stu-id="bd717-p103">By using a **$upn** variable, you can make changes to individual accounts based on their display name. Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="bd717-140">Modificare le proprietà per tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="bd717-140">Change properties for all user accounts</span></span>

<span data-ttu-id="bd717-p104">Per modificare le proprietà per tutti gli utenti, è possibile utilizzare la combinazione di cmdlet **Get-AzureADUser** e **Set-AzureADUser**. Nell'esempio seguente viene modificata la posizione di utilizzo per tutti gli utenti in Francia:</span><span class="sxs-lookup"><span data-stu-id="bd717-p104">To change properties for all users, you can use the combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets. The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="bd717-143">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="bd717-143">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bd717-144">Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bd717-144">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bd717-145">Impostare la posizione dell'utente in Francia (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="bd717-145">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="bd717-146">Modificare le proprietà per un set specifico di account utente</span><span class="sxs-lookup"><span data-stu-id="bd717-146">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="bd717-p105">Per modificare le proprietà per un set specifico di account utente, è possibile utilizzare la combinazione di cmdlet **Get-AzureADUser**, **Where** e **Set-AzureADUser**. Nell'esempio seguente viene modificata la posizione di utilizzo per tutti gli utenti del reparto Contabilità in Francia:</span><span class="sxs-lookup"><span data-stu-id="bd717-p105">To change properties for a specific set of user account, you can use the combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets. The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="bd717-149">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="bd717-149">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bd717-150">Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bd717-150">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bd717-151">Individuare tutti gli account utente con la proprietà Department impostata su "Accounting" (**dove {$ _. Department-EQ "Accounting"}**) e inviare le informazioni risultanti al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bd717-151">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="bd717-152">Impostare la posizione dell'utente in Francia (**set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="bd717-152">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="bd717-153">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd717-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="bd717-154">Per configurare le proprietà degli account utente con il modulo di Microsoft Azure Active Directory per Windows PowerShell, utilizzare il cmdlet **set-MsolUser** e specificare le proprietà da impostare o modificare.</span><span class="sxs-lookup"><span data-stu-id="bd717-154">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, you use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="bd717-155">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="bd717-155">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="bd717-156">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="bd717-156">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="bd717-157">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd717-157">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="bd717-158">Modificare le proprietà per un account utente specifico</span><span class="sxs-lookup"><span data-stu-id="bd717-158">Change properties for a specific user account</span></span>

<span data-ttu-id="bd717-159">Per configurare le proprietà per un account utente specifico, utilizzare il cmdlet [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) e specificare le proprietà da impostare o modificare.</span><span class="sxs-lookup"><span data-stu-id="bd717-159">To configure properties for a specific user account, you use the [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="bd717-p107">Identificare l'account con il parametro **-UserPrincipalName** e impostare o modificare proprietà specifiche con ulteriori parametri. Ecco un elenco dei parametri più comuni.</span><span class="sxs-lookup"><span data-stu-id="bd717-p107">You identify the account with the **-UserPrincipalName** parameter and set or change specific properties with additional parameters. Here is a list of the most common parameters.</span></span>
  
- <span data-ttu-id="bd717-162">-City "<nome città>"</span><span class="sxs-lookup"><span data-stu-id="bd717-162">-City "\<city name>"</span></span>
    
- <span data-ttu-id="bd717-163">-Country "\<country name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-163">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="bd717-164">-Department "\<department name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-164">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="bd717-165">-DisplayName "\<full user name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-165">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="bd717-166">-Fax "\<fax number>"</span><span class="sxs-lookup"><span data-stu-id="bd717-166">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="bd717-167">-FirstName "\<user first name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-167">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="bd717-168">-LastName "\<user last name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-168">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="bd717-169">-MobilePhone "\<mobile phone number>"</span><span class="sxs-lookup"><span data-stu-id="bd717-169">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="bd717-170">-Office "\<office location>"</span><span class="sxs-lookup"><span data-stu-id="bd717-170">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="bd717-171">-PhoneNumber "\<office phone number>"</span><span class="sxs-lookup"><span data-stu-id="bd717-171">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="bd717-172">-PostalCode "\<postal code>"</span><span class="sxs-lookup"><span data-stu-id="bd717-172">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="bd717-173">-PreferredLanguage "\<language>"</span><span class="sxs-lookup"><span data-stu-id="bd717-173">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="bd717-174">-State "\<state name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-174">-State "\<state name>"</span></span>
    
- <span data-ttu-id="bd717-175">-StreetAddress "\<street address>"</span><span class="sxs-lookup"><span data-stu-id="bd717-175">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="bd717-176">-Title "\<title name>"</span><span class="sxs-lookup"><span data-stu-id="bd717-176">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="bd717-177">-UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="bd717-177">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="bd717-178">Si tratta del codice paese o area geografica a due lettere ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="bd717-178">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="bd717-179">Per ulteriori parametri, vedere [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="bd717-179">See [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) for additional parameters.</span></span>

<span data-ttu-id="bd717-180">Per visualizzare i nomi principali di tutti gli utenti, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="bd717-180">To see the User Principal Names of all your users, run the following command.</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="bd717-181">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="bd717-181">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bd717-182">Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bd717-182">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bd717-183">Ordinare l'elenco dei nomi delle entità utente in ordine alfabetico (**Sort userPrincipalName**) e inviarlo al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bd717-183">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bd717-184">Visualizzare solo la proprietà del nome dell'entità utente per ogni account (**selezionare userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="bd717-184">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
- <span data-ttu-id="bd717-185">Visualizzare gli elementi in una schermata alla volta (**More**).</span><span class="sxs-lookup"><span data-stu-id="bd717-185">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="bd717-186">Con questo comando vengono elencati tutti gli account.</span><span class="sxs-lookup"><span data-stu-id="bd717-186">This command will list all of your accounts.</span></span> <span data-ttu-id="bd717-187">Se si desidera visualizzare il nome dell'entità utente per un account in base al nome visualizzato (nome e cognome), inserire la variabile **$username** in basso (rimozione dei \< and > caratteri), quindi eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd717-187">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bd717-188">Questo esempio permette di visualizzare il nome principale dell'utente denominato Caleb Sillis.</span><span class="sxs-lookup"><span data-stu-id="bd717-188">This example displays the User Principal Name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="bd717-p109">Utilizzando una variabile **$upn**, è possibile apportare modifiche ai singoli account in base al nome visualizzato. Ecco un esempio di impostazione della posizione di utilizzo di Belinda Newman in Francia, specificando il nome visualizzato anziché il nome principale dell'utente:</span><span class="sxs-lookup"><span data-stu-id="bd717-p109">By using a **$upn** variable, you can make changes to individual accounts based on their display name. Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="bd717-191">Modificare le proprietà per tutti gli account utente</span><span class="sxs-lookup"><span data-stu-id="bd717-191">Change properties for all user accounts</span></span>

<span data-ttu-id="bd717-p110">Per modificare le proprietà per tutti gli utenti, è possibile utilizzare la combinazione di cmdlet **Get-MsolUser** e **Set-MsolUser**. Nell'esempio seguente viene modificata la posizione di utilizzo per tutti gli utenti in Francia:</span><span class="sxs-lookup"><span data-stu-id="bd717-p110">To change properties for all users, you can use the combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets. The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="bd717-194">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="bd717-194">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bd717-195">Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bd717-195">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bd717-196">Impostare la posizione dell'utente in Francia (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="bd717-196">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="bd717-197">Modificare le proprietà per un set specifico di account utente</span><span class="sxs-lookup"><span data-stu-id="bd717-197">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="bd717-198">Per modificare le proprietà di un determinato set di account utente, è possibile utilizzare la combinazione dei cmdlet **Get-MsolUser**, **where**e **set-MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="bd717-198">To change properties for a specific set of user account, you can use the combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="bd717-199">Nell'esempio seguente viene modificata la posizione di utilizzo per tutti gli utenti del reparto Contabilità in Francia:</span><span class="sxs-lookup"><span data-stu-id="bd717-199">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="bd717-200">Questo comando indica a PowerShell di:</span><span class="sxs-lookup"><span data-stu-id="bd717-200">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="bd717-201">Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bd717-201">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="bd717-202">Individuare tutti gli account utente con la proprietà Department impostata su "Accounting" (**dove {$ _. Department-EQ "Accounting"}**) e inviare le informazioni risultanti al comando successivo ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="bd717-202">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="bd717-203">Impostare la posizione dell'utente in Francia (**set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="bd717-203">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    

## <a name="see-also"></a><span data-ttu-id="bd717-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd717-204">See also</span></span>

[<span data-ttu-id="bd717-205">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd717-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="bd717-206">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd717-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="bd717-207">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bd717-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
