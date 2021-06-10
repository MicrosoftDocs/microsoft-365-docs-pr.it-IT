---
title: Visualizzare Microsoft 365 licenze e servizi con PowerShell
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
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: Spiega come usare PowerShell per visualizzare informazioni sui piani di licenza, i servizi e le licenze disponibili nell'organizzazione Microsoft 365 locale.
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924637"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="c6585-103">Visualizzare Microsoft 365 licenze e servizi con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6585-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="c6585-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="c6585-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c6585-105">Ogni Microsoft 365 è costituito dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="c6585-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="c6585-106">**Piani di licenza** Questi sono noti anche come piani di licenza o Microsoft 365 licenza.</span><span class="sxs-lookup"><span data-stu-id="c6585-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="c6585-107">I piani di gestione delle Microsoft 365 definiscono i servizi di licenza disponibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c6585-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="c6585-108">La Microsoft 365 può contenere più piani di licenza.</span><span class="sxs-lookup"><span data-stu-id="c6585-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="c6585-109">Un piano di licenza di esempio è Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="c6585-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="c6585-110">**Servizi** Questi sono noti anche come piani di servizio.</span><span class="sxs-lookup"><span data-stu-id="c6585-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="c6585-111">I servizi sono Microsoft 365, funzionalità e funzionalità disponibili in ogni piano di gestione delle licenze, ad esempio Exchange Online e Microsoft 365 Apps for enterprise (in precedenza denominato Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="c6585-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="c6585-112">Gli utenti possono disporre di più licenze tramite diversi piani di licenza che garantiscono l'accesso ai diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="c6585-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="c6585-113">**Licenze** Ogni piano di licenze contiene il numero di licenze acquistate.</span><span class="sxs-lookup"><span data-stu-id="c6585-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="c6585-114">Le licenze vengono assegnate agli utenti in modo che possano usare i servizi Microsoft 365 definiti dal piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="c6585-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="c6585-115">Ogni account utente richiede almeno una licenza di un piano di licenza in modo che possa accedere a Microsoft 365 e usare i servizi.</span><span class="sxs-lookup"><span data-stu-id="c6585-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="c6585-116">È possibile usare PowerShell per Microsoft 365 per visualizzare i dettagli sui piani di licenza, sulle licenze e sui servizi disponibili nell'organizzazione Microsoft 365 locale.</span><span class="sxs-lookup"><span data-stu-id="c6585-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="c6585-117">Per ulteriori informazioni sui prodotti, le funzionalità e i servizi disponibili in diverse sottoscrizioni Office 365, vedere Office 365 [Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span><span class="sxs-lookup"><span data-stu-id="c6585-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c6585-118">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="c6585-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c6585-119">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="c6585-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="c6585-120">Per visualizzare informazioni di riepilogo sui piani di licenza correnti e sulle licenze disponibili per ogni piano, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="c6585-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="c6585-121">I risultati contengono:</span><span class="sxs-lookup"><span data-stu-id="c6585-121">The results contain:</span></span>
  
- <span data-ttu-id="c6585-122">**SkuPartNumber:** Mostra i piani di licenza disponibili per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c6585-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="c6585-123">Ad esempio, `ENTERPRISEPACK` è il nome del piano di licenza per Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="c6585-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="c6585-124">**Abilitato:** Numero di licenze acquistate per un piano di licenze specifico.</span><span class="sxs-lookup"><span data-stu-id="c6585-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="c6585-125">**ConsumedUnits:** Numero di licenze assegnate agli utenti da un piano di licenze specifico.</span><span class="sxs-lookup"><span data-stu-id="c6585-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="c6585-126">Per visualizzare i dettagli sui Microsoft 365 disponibili in tutti i piani di licenza, visualizzare innanzitutto un elenco dei piani di licenza.</span><span class="sxs-lookup"><span data-stu-id="c6585-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="c6585-127">Archiviare quindi le informazioni sui piani di licenza in una variabile.</span><span class="sxs-lookup"><span data-stu-id="c6585-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="c6585-128">Successivamente, visualizzare i servizi in un piano di licenza specifico.</span><span class="sxs-lookup"><span data-stu-id="c6585-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="c6585-129">\<index> è un numero intero che specifica il numero di riga del piano di licenza dalla visualizzazione del `Get-AzureADSubscribedSku | Select SkuPartNumber` comando, meno 1.</span><span class="sxs-lookup"><span data-stu-id="c6585-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="c6585-130">Ad esempio, se la visualizzazione del `Get-AzureADSubscribedSku | Select SkuPartNumber` comando è la seguente:</span><span class="sxs-lookup"><span data-stu-id="c6585-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="c6585-131">Il comando per visualizzare i servizi per il piano di licenza ENTERPRISEPREMIUM è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c6585-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="c6585-132">ENTERPRISEPREMIUM è la terza riga.</span><span class="sxs-lookup"><span data-stu-id="c6585-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="c6585-133">Di conseguenza, il valore di indice è (3 - 1) o 2.</span><span class="sxs-lookup"><span data-stu-id="c6585-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="c6585-134">Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), dei piani di servizio inclusi e dei nomi descrittivi corrispondenti, vedere Nomi dei prodotti e identificatori del piano di servizio [per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="c6585-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="c6585-135">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6585-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="c6585-136">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="c6585-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="c6585-137">Uno script PowerShell è disponibile per rendere automatiche le procedure descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c6585-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="c6585-138">In particolare, lo script consente di visualizzare e disabilitare i servizi nell'organizzazione Microsoft 365, incluso Sway.</span><span class="sxs-lookup"><span data-stu-id="c6585-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="c6585-139">Per ulteriori informazioni, vedere [Disabilitare l'accesso a Sway con PowerShell.](disable-access-to-sway-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="c6585-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="c6585-140">Per visualizzare informazioni di riepilogo sui piani di licenza correnti e sulle licenze disponibili per ogni piano, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c6585-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="c6585-141">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="c6585-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="c6585-142">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6585-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="c6585-143">I risultati contengono le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="c6585-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="c6585-144">**AccountSkuId:** Visualizzare i piani di licenza disponibili per l'organizzazione utilizzando la sintassi `<CompanyName>:<LicensingPlan>` .</span><span class="sxs-lookup"><span data-stu-id="c6585-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="c6585-145">_\<CompanyName>_ è il valore specificato al momento della registrazione a Microsoft 365 ed è univoco per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c6585-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="c6585-146">Il _\<LicensingPlan>_ valore è lo stesso per tutti.</span><span class="sxs-lookup"><span data-stu-id="c6585-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="c6585-147">Ad esempio, nel valore , il nome della società è e il nome del piano di licenza , che è il nome di sistema per Office 365 Enterprise `litwareinc:ENTERPRISEPACK` `litwareinc` `ENTERPRISEPACK` E3.</span><span class="sxs-lookup"><span data-stu-id="c6585-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="c6585-148">**ActiveUnits:** Numero di licenze acquistate per un piano di licenze specifico.</span><span class="sxs-lookup"><span data-stu-id="c6585-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="c6585-149">**WarningUnits:** Numero di licenze in un piano di licenze non rinnovate e che scadranno dopo il periodo di tolleranza di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="c6585-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="c6585-150">**ConsumedUnits:** Numero di licenze assegnate agli utenti da un piano di licenze specifico.</span><span class="sxs-lookup"><span data-stu-id="c6585-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="c6585-151">Per visualizzare i dettagli sui Microsoft 365 disponibili in tutti i piani di licenza, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c6585-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="c6585-152">Nella tabella seguente vengono illustrati i Microsoft 365 e i relativi nomi descrittivi per i servizi più comuni.</span><span class="sxs-lookup"><span data-stu-id="c6585-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="c6585-153">L'elenco dei piani di servizio degli utenti potrebbe essere diverso.</span><span class="sxs-lookup"><span data-stu-id="c6585-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="c6585-154">**Piano di servizio**</span><span class="sxs-lookup"><span data-stu-id="c6585-154">**Service plan**</span></span>|<span data-ttu-id="c6585-155">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c6585-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="c6585-156">Sway</span><span class="sxs-lookup"><span data-stu-id="c6585-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="c6585-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6585-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="c6585-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="c6585-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="c6585-159">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="c6585-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="c6585-160">Microsoft 365 Apps for enterprise *(precedentemente denominato Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="c6585-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="c6585-161">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c6585-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="c6585-162">Office</span><span class="sxs-lookup"><span data-stu-id="c6585-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="c6585-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c6585-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="c6585-164">Exchange Online, piano 2</span><span class="sxs-lookup"><span data-stu-id="c6585-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="c6585-165">Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), dei piani di servizio inclusi e dei nomi descrittivi corrispondenti, vedere Nomi dei prodotti e identificatori del piano di servizio [per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="c6585-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="c6585-166">Per visualizzare i dettagli sui Microsoft 365 disponibili in un piano di gestione delle licenze specifico, utilizzare la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="c6585-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="c6585-167">Questo esempio mostra i servizi disponibili nel piano di licenza litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="c6585-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="c6585-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6585-168">See also</span></span>

[<span data-ttu-id="c6585-169">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6585-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c6585-170">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6585-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c6585-171">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c6585-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)