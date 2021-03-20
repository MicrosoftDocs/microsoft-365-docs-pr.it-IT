---
title: Effettuare la connessione a tutti i servizi di Microsoft 365 in un'unica finestra di PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: "Riepilogo: Effettuare la connessione a tutti i servizi di Microsoft 365 in un'unica finestra di PowerShell."
ms.openlocfilehash: 18ff8e1789242b4dde3b4b31aaccf2462e4c5d74
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905129"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="1b661-103">Effettuare la connessione a tutti i servizi di Microsoft 365 in un'unica finestra di PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b661-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="1b661-104">Quando si usa PowerShell per gestire Microsoft 365, è possibile aprire contemporaneamente più sessioni di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b661-104">When you use PowerShell to manage Microsoft 365, you can have multiple PowerShell sessions open at the same time.</span></span> <span data-ttu-id="1b661-105">Si potrebbero avere finestre di PowerShell diverse per gestire gli account utente, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams e il Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="1b661-105">You might have different PowerShell windows to manage user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance center.</span></span>
  
<span data-ttu-id="1b661-106">Non si tratta di uno scenario ottimale per la gestione di Microsoft 365, poiché non è possibile gestire i servizi scambiando i dati tra le finestre.</span><span class="sxs-lookup"><span data-stu-id="1b661-106">This scenario isn't optimal for managing Microsoft 365, because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="1b661-107">Questo articolo descrive come usare una singola istanza di PowerShell per gestire gli account di Microsoft 365, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams e il Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="1b661-107">This article describes how to use a single instance of PowerShell to manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="1b661-108">Questo articolo contiene al momento solo i comandi per connettersi al cloud internazionale (+GCC).</span><span class="sxs-lookup"><span data-stu-id="1b661-108">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="1b661-109">Le note contengono collegamenti agli articoli con informazioni sulla connessione ad altri cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1b661-109">Notes provide links to articles about connecting to the other Microsoft 365 clouds.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1b661-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1b661-110">Before you begin</span></span>

<span data-ttu-id="1b661-111">Per poter gestire tutti i servizi di Microsoft 365 da una singola istanza di PowerShell, prendere in considerazione i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b661-111">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="1b661-112">L'account aziendale o dell'istituto di istruzione di Microsoft 365 usato per queste procedure deve avere un ruolo di amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1b661-112">The Microsoft 365 work or school account that you use must be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="1b661-113">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1b661-113">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span> <span data-ttu-id="1b661-114">Questo è un requisito per PowerShell per Microsoft 365, ma non necessariamente per tutti gli altri servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1b661-114">This is a requirement for PowerShell for Microsoft 365, but not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="1b661-115">È possibile usare le seguenti versioni a 64 bit di Windows:</span><span class="sxs-lookup"><span data-stu-id="1b661-115">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="1b661-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1b661-116">Windows 10</span></span>
    
  - <span data-ttu-id="1b661-117">Windows 8.1 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="1b661-117">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="1b661-118">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="1b661-118">Windows Server 2019</span></span>
    
  - <span data-ttu-id="1b661-119">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="1b661-119">Windows Server 2016</span></span>
    
  - <span data-ttu-id="1b661-120">Windows Server 2012 R2 o Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1b661-120">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="1b661-121">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="1b661-121">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="1b661-122">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="1b661-122">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="1b661-123">\* È necessario installare Microsoft .NET Framework 4.5.*x* e quindi Windows Management Framework 3.0 o 4.0.</span><span class="sxs-lookup"><span data-stu-id="1b661-123">\* You need to install Microsoft .NET Framework 4.5.*x* and then Windows Management Framework 3.0 or 4.0.</span></span> <span data-ttu-id="1b661-124">Per altre informazioni, vedere [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).</span><span class="sxs-lookup"><span data-stu-id="1b661-124">For more information, see [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).</span></span>
    
    <span data-ttu-id="1b661-125">È necessario utilizzare una versione a 64 bit di Windows, a causa dei requisiti, per il modulo di Skype for Business Online e una per moduli di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1b661-125">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="1b661-126">È necessario installare i moduli necessari per Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online e Teams:</span><span class="sxs-lookup"><span data-stu-id="1b661-126">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
  - [<span data-ttu-id="1b661-127">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="1b661-127">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [<span data-ttu-id="1b661-128">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="1b661-128">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [<span data-ttu-id="1b661-129">Skype for Business Online, moduli PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b661-129">Skype for Business Online, PowerShell Module</span></span>](/microsoftteams/teams-powershell-overview)
  - [<span data-ttu-id="1b661-130">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="1b661-130">Exchange Online PowerShell V2</span></span>](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [<span data-ttu-id="1b661-131">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="1b661-131">Teams PowerShell Overview</span></span>](/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="1b661-132">PowerShell deve essere configurato per l'esecuzione di script firmati per Skype for Business Online e il Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="1b661-132">PowerShell must be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="1b661-133">Eseguire il comando seguente in una sessione di PowerShell con privilegi elevati, ossia una sessione di PowerShell aperta usando **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="1b661-133">Run the following command in an elevated PowerShell session (a PowerShell session that you **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="1b661-134">Procedura di connessione se si usa solo una password</span><span class="sxs-lookup"><span data-stu-id="1b661-134">Connection steps when using just a password</span></span>

<span data-ttu-id="1b661-135">Seguire questa procedura per connettersi a tutti i servizi in una singola finestra di PowerShell se si usa solo una password per accedere.</span><span class="sxs-lookup"><span data-stu-id="1b661-135">Follow these steps to connect to all the services in a single PowerShell window when you're using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="1b661-136">Aprire Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b661-136">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="1b661-137">Eseguire il comando seguente e immettere le credenziali dell'account aziendale o dell'Istituto di istruzione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1b661-137">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="1b661-138">Eseguire questo comando per connettersi ad Azure AD tramite il modulo di Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="1b661-138">Run this command to connect to Azure AD by using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="1b661-139">In alternativa, se si usa il Modulo di Microsoft Azure Active Directory per Windows PowerShell, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="1b661-139">Or if you're using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="1b661-140">PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="1b661-140">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="1b661-141">È necessario eseguire questi cmdlet da PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b661-141">You must run these cmdlets from PowerShell.</span></span>

4. <span data-ttu-id="1b661-142">Eseguire i comandi seguenti per la connessione a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1b661-142">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="1b661-143">Specificare il nome dell'organizzazione per il dominio.</span><span class="sxs-lookup"><span data-stu-id="1b661-143">Specify the organization name for your domain.</span></span> <span data-ttu-id="1b661-144">Ad esempio, per "litwareinc\.onmicrosoft.com", il valore del nome dell'organizzazione è "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="1b661-144">For example, for "litwareinc\.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. <span data-ttu-id="1b661-145">Eseguire questi comandi per connettersi a Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="1b661-145">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="1b661-146">La prima volta che ci si connette, verrà visualizzato un messaggio di avviso relativo all'aumento del valore `WSMan NetworkDelayms`.</span><span class="sxs-lookup"><span data-stu-id="1b661-146">A warning about increasing the `WSMan NetworkDelayms` value will appear the first time that you connect.</span></span> <span data-ttu-id="1b661-147">Ignorarlo.</span><span class="sxs-lookup"><span data-stu-id="1b661-147">Ignore it.</span></span>
     
   > [!Note]
   > <span data-ttu-id="1b661-148">Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente.</span><span class="sxs-lookup"><span data-stu-id="1b661-148">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="1b661-149">Se si usa la versione pubblica di PowerShell di Teams più recente, non è necessario installare il connettore di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="1b661-149">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

6. <span data-ttu-id="1b661-150">Eseguire i comandi seguenti per la connessione a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1b661-150">Run these commands to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="1b661-151">Per connettersi a Exchange Online per i cloud di Microsoft 365 diversi da quello internazionale, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1b661-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="1b661-152">Eseguire i comandi seguenti per connettersi al Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="1b661-152">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="1b661-153">Per connettersi al Centro sicurezza &amp; conformità per i cloud di Microsoft 365 diversi da quello internazionale, vedere [Connettersi al Centro sicurezza e conformità di PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="1b661-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="1b661-154">Eseguire i comandi seguenti per connettersi a PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="1b661-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="1b661-155">Per connettersi a cloud di Microsoft Teams diversi da quello \*\* internazionale, vedere [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="1b661-155">To connect to Microsoft Teams clouds other than *Worldwide*, see [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).</span></span>
  



### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1b661-156">Modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="1b661-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1b661-157">Di seguito sono elencati i comandi per tutti i servizi in un unico blocco quando si usa il modulo di Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="1b661-157">Here are the commands for all the services in a single block when you use the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="1b661-158">Specificare il nome dell'host del dominio e l'UPN per l'accesso, quindi eseguirli tutti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="1b661-158">Specify the name of your domain host and the UPN for the sign-in and run them all at the same time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="1b661-159">Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b661-159">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="1b661-160">Di seguito sono elencati i comandi per tutti i servizi in un unico blocco, quando si usa il Modulo di Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b661-160">Here are the commands for all the services in a single block when you use the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="1b661-161">Specificare il nome dell'host del dominio e l'UPN per l'accesso ed eseguirli tutti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="1b661-161">Specify the name of your domain host and the UPN for the sign-in and run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="1b661-162">Procedura di connessione quando si usa l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="1b661-162">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1b661-163">Modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="1b661-163">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1b661-164">Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 quando si usa l'autenticazione a più fattori con il modulo di Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="1b661-164">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="1b661-165">Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b661-165">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="1b661-166">Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 quando si usa l'autenticazione a più fattori con il Modulo di Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b661-166">Here are all the commands in a single block to connect to multiple Microsoft 365 services when you use multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="1b661-167">Chiudere la finestra di PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b661-167">Close the PowerShell window</span></span>

<span data-ttu-id="1b661-168">Per chiudere la finestra di PowerShell, eseguire questo comando per rimuovere le sessioni attive verso Skype for Business Online, SharePoint Online e Teams:</span><span class="sxs-lookup"><span data-stu-id="1b661-168">To close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a><span data-ttu-id="1b661-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b661-169">See also</span></span>

- [<span data-ttu-id="1b661-170">Collegarsi a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b661-170">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="1b661-171">Gestire SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b661-171">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1b661-172">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b661-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)