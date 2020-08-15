---
title: Visualizzare le licenze e i servizi di Microsoft 365 con PowerShell
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
description: Viene illustrato come utilizzare PowerShell per visualizzare informazioni sui piani di licenza, i servizi e le licenze disponibili nell'organizzazione Microsoft 365.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691194"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="b22d5-103">Visualizzare le licenze e i servizi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b22d5-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="b22d5-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b22d5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b22d5-105">Ogni sottoscrizione Microsoft 365 è costituita dai seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="b22d5-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="b22d5-106">**Piani di gestione delle licenze** Questi sono noti anche come piani di licenza o Microsoft 365 piani.</span><span class="sxs-lookup"><span data-stu-id="b22d5-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="b22d5-107">I piani di gestione delle licenze definiscono i servizi Microsoft 365 che sono disponibili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="b22d5-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="b22d5-108">La sottoscrizione Microsoft 365 potrebbe contenere più piani di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="b22d5-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="b22d5-109">Un esempio di piano di gestione delle licenze sarebbe Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="b22d5-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="b22d5-110">**Servizi offerti** Questi sono noti anche come piani di servizio.</span><span class="sxs-lookup"><span data-stu-id="b22d5-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="b22d5-111">Servizi sono i prodotti, le caratteristiche e le funzionalità di Microsoft 365 disponibili in ogni piano di gestione delle licenze, ad esempio, Exchange Online e Microsoft 365 Apps for Enterprise (in precedenza denominato Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="b22d5-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="b22d5-112">Gli utenti possono disporre di più licenze tramite diversi piani di licenza che garantiscono l'accesso ai diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="b22d5-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="b22d5-113">**Licenze** Ogni piano di gestione delle licenze contiene il numero di licenze acquistate.</span><span class="sxs-lookup"><span data-stu-id="b22d5-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="b22d5-114">È possibile assegnare licenze agli utenti in modo che possano utilizzare i servizi Microsoft 365 definiti dal piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="b22d5-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="b22d5-115">Ogni account utente richiede almeno una licenza da un piano di gestione delle licenze, in modo che possano accedere a Microsoft 365 e utilizzare i servizi.</span><span class="sxs-lookup"><span data-stu-id="b22d5-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="b22d5-116">È possibile utilizzare PowerShell per Microsoft 365 per visualizzare i dettagli sui piani, le licenze e i servizi di gestione delle licenze disponibili nell'organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b22d5-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="b22d5-117">Per ulteriori informazioni sui prodotti, le caratteristiche e i servizi disponibili in diverse sottoscrizioni di Office 365, vedere [office 365 Plan Options](https://go.microsoft.com/fwlink/p/?LinkId=691147).</span><span class="sxs-lookup"><span data-stu-id="b22d5-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](https://go.microsoft.com/fwlink/p/?LinkId=691147).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b22d5-118">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="b22d5-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="b22d5-119">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="b22d5-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="b22d5-120">Per visualizzare le informazioni di riepilogo sui piani di gestione delle licenze e sulle licenze disponibili per ogni piano, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b22d5-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="b22d5-121">I risultati contengono:</span><span class="sxs-lookup"><span data-stu-id="b22d5-121">The results contain:</span></span>
  
- <span data-ttu-id="b22d5-122">**SkuPartNumber:** Visualizza i piani di gestione delle licenze disponibili per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b22d5-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="b22d5-123">Ad esempio, `ENTERPRISEPACK` è il nome del piano di licenza per Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="b22d5-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="b22d5-124">**Attivato:** Il numero di licenze acquistate per uno specifico piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="b22d5-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="b22d5-125">**ConsumedUnits:** Il numero di licenze assegnate agli utenti da uno specifico piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="b22d5-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="b22d5-126">Per visualizzare i dettagli sui servizi Microsoft 365 disponibili in tutti i piani di licenza, è necessario innanzitutto visualizzare un elenco dei piani di licenza.</span><span class="sxs-lookup"><span data-stu-id="b22d5-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="b22d5-127">Successivamente, archiviare le informazioni relative ai piani di licenza in una variabile.</span><span class="sxs-lookup"><span data-stu-id="b22d5-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="b22d5-128">Successivamente, visualizzare i servizi in un piano di licenza specifico.</span><span class="sxs-lookup"><span data-stu-id="b22d5-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="b22d5-129">\<index> è un valore integer che specifica il numero di riga del piano di licenza dalla visualizzazione del `Get-AzureADSubscribedSku | Select SkuPartNumber` comando (-1).</span><span class="sxs-lookup"><span data-stu-id="b22d5-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="b22d5-130">Ad esempio, se la visualizzazione del `Get-AzureADSubscribedSku | Select SkuPartNumber` comando è la seguente:</span><span class="sxs-lookup"><span data-stu-id="b22d5-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="b22d5-131">Successivamente, il comando per visualizzare i servizi per il piano di licenza di ENTERPRISEPREMIUM è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b22d5-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="b22d5-132">ENTERPRISEPREMIUM è la terza riga.</span><span class="sxs-lookup"><span data-stu-id="b22d5-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="b22d5-133">Pertanto, il valore di indice è (3-1) oppure 2.</span><span class="sxs-lookup"><span data-stu-id="b22d5-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="b22d5-134">Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), per i piani di servizio inclusi e per i nomi descrittivi corrispondenti, vedere [nomi di prodotti e identificatori di piani di servizio per la gestione delle licenze](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="b22d5-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="b22d5-135">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b22d5-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="b22d5-136">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b22d5-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="b22d5-137">Uno script PowerShell è disponibile per rendere automatiche le procedure descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b22d5-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="b22d5-138">Nello specifico, lo script consente di visualizzare e disabilitare i servizi nell'organizzazione Microsoft 365, tra cui Sway.</span><span class="sxs-lookup"><span data-stu-id="b22d5-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="b22d5-139">Per ulteriori informazioni, vedere [disabilitare l'accesso a Sway con PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b22d5-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="b22d5-140">Per visualizzare informazioni di riepilogo sui piani di gestione delle licenze e sulle licenze disponibili per ogni piano, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b22d5-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="b22d5-141">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="b22d5-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="b22d5-142">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b22d5-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="b22d5-143">I risultati contengono le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="b22d5-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="b22d5-144">**AccountSkuId:** Visualizzare i piani di gestione delle licenze disponibili per l'organizzazione utilizzando la sintassi `<CompanyName>:<LicensingPlan>` .</span><span class="sxs-lookup"><span data-stu-id="b22d5-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="b22d5-145">_\<CompanyName>_ è il valore specificato quando si è registrato Microsoft 365 ed è univoco per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b22d5-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="b22d5-146">Il _\<LicensingPlan>_ valore è lo stesso per tutti.</span><span class="sxs-lookup"><span data-stu-id="b22d5-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="b22d5-147">Ad esempio, nel valore `litwareinc:ENTERPRISEPACK` , il nome della società è  `litwareinc` e il nome del piano di gestione delle licenze  `ENTERPRISEPACK` , che è il nome di sistema per Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="b22d5-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="b22d5-148">**ActiveUnits:** Il numero di licenze acquistate per uno specifico piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="b22d5-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="b22d5-149">**WarningUnits:** Il numero di licenze in un piano di gestione delle licenze che non sono state rinnovate e che scadranno dopo il periodo di tolleranza di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="b22d5-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="b22d5-150">**ConsumedUnits:** Il numero di licenze assegnate agli utenti da uno specifico piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="b22d5-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="b22d5-151">Per visualizzare i dettagli sui servizi Microsoft 365 disponibili in tutti i piani di licenza, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b22d5-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="b22d5-152">Nella tabella seguente vengono illustrati i piani di servizio Microsoft 365 e i relativi nomi descrittivi per i servizi più comuni.</span><span class="sxs-lookup"><span data-stu-id="b22d5-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="b22d5-153">L'elenco dei piani di servizio degli utenti potrebbe essere diverso.</span><span class="sxs-lookup"><span data-stu-id="b22d5-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="b22d5-154">**Piano di servizio**</span><span class="sxs-lookup"><span data-stu-id="b22d5-154">**Service plan**</span></span>|<span data-ttu-id="b22d5-155">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b22d5-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="b22d5-156">Sway</span><span class="sxs-lookup"><span data-stu-id="b22d5-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="b22d5-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b22d5-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="b22d5-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="b22d5-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="b22d5-159">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="b22d5-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="b22d5-160">Microsoft 365 Apps for Enterprise *(in precedenza denominato Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="b22d5-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="b22d5-161">Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="b22d5-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="b22d5-162">Ufficio</span><span class="sxs-lookup"><span data-stu-id="b22d5-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="b22d5-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b22d5-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="b22d5-164">Exchange Online, piano 2</span><span class="sxs-lookup"><span data-stu-id="b22d5-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="b22d5-165">Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), per i piani di servizio inclusi e per i nomi descrittivi corrispondenti, vedere [nomi di prodotti e identificatori di piani di servizio per la gestione delle licenze](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="b22d5-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="b22d5-166">Per visualizzare i dettagli sui servizi Microsoft 365 disponibili in uno specifico piano di gestione delle licenze, utilizzare la seguente sintassi.</span><span class="sxs-lookup"><span data-stu-id="b22d5-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="b22d5-167">In questo esempio vengono illustrati i servizi disponibili nel piano di gestione delle licenze litwareinc: ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="b22d5-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="b22d5-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b22d5-168">See also</span></span>

[<span data-ttu-id="b22d5-169">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b22d5-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b22d5-170">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b22d5-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b22d5-171">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b22d5-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
