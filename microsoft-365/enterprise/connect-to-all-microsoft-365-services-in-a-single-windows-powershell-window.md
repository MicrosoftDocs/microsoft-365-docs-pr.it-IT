---
title: Effettuare la connessione a tutti i servizi Microsoft 365 in un'unica finestra di Windows PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/10/2020
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
description: "Riepilogo: effettuare la connessione di Windows PowerShell a tutti i servizi Microsoft 365 in un'unica finestra di Windows PowerShell."
ms.openlocfilehash: d4e4bf6ec07ee4a0a5b2f8cb1c83ffacd221eaa0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691308"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window"></a><span data-ttu-id="155cf-103">Effettuare la connessione a tutti i servizi Microsoft 365 in un'unica finestra di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="155cf-103">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>

<span data-ttu-id="155cf-104">Se si usa PowerShell per gestire Microsoft 365, è possibile avere fino a cinque diverse sessioni di Windows PowerShell aperte contemporaneamente, ossia l'interfaccia di amministrazione di Microsoft 365, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams e il Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="155cf-104">When you use PowerShell to manage Microsoft 365, it is possible to have up to five different Windows PowerShell sessions open at the same time corresponding to Microsoft 365 admin center, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="155cf-105">Con cinque metodi di connessione differenti in sessioni separate di Windows PowerShell, il desktop può essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="155cf-105">With five different connection methods in separate Windows PowerShell sessions, your desktop could look like this:</span></span>
  
![Cinque console di Windows PowerShell in esecuzione contemporaneamente](../media/a1a852c2-89ea-4e8e-8d8b-dcdf596763d1.png)
  
<span data-ttu-id="155cf-107">Non si tratta di una condizione ottimale per la gestione di Microsoft 365, poiché non è possibile scambiare dati tra le cinque finestre per la gestione dei diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="155cf-107">This is not optimal for managing Microsoft 365 because you can't exchange data among those five windows for cross-service management.</span></span> <span data-ttu-id="155cf-108">Questo argomento descrive come usare una singola istanza di Windows PowerShell da cui gestire gli account di Microsoft 365, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams e il Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="155cf-108">This topic describes how to use a single instance of Windows PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="155cf-109">Contiene al momento solo i comandi per connettersi al cloud internazionale (+GCC).</span><span class="sxs-lookup"><span data-stu-id="155cf-109">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="155cf-110">Note aggiuntive forniscono collegamenti agli articoli con informazioni sulla connessione ad altri cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="155cf-110">Additional notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="155cf-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="155cf-111">Before you begin</span></span>

<span data-ttu-id="155cf-112">Per poter gestire tutti i servizi di Microsoft 365 da una singola istanza di Windows PowerShell, prendere in considerazione i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="155cf-112">Before you can manage all of Microsoft 365 from a single instance of Windows PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="155cf-113">L'account aziendale o dell'Istituto di istruzione di Microsoft 365 usato per queste procedure deve avere un ruolo di amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="155cf-113">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="155cf-114">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="155cf-114">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).</span></span> <span data-ttu-id="155cf-115">Questo è un requisito per PowerShell per Microsoft 365, quindi non necessariamente per tutti gli altri servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="155cf-115">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="155cf-116">È possibile usare le seguenti versioni a 64 bit di Windows:</span><span class="sxs-lookup"><span data-stu-id="155cf-116">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="155cf-117">Windows 10</span><span class="sxs-lookup"><span data-stu-id="155cf-117">Windows 10</span></span>
    
  - <span data-ttu-id="155cf-118">Windows 8.1 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="155cf-118">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="155cf-119">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="155cf-119">Windows Server 2019</span></span>
    
  - <span data-ttu-id="155cf-120">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="155cf-120">Windows Server 2016</span></span>
    
  - <span data-ttu-id="155cf-121">Windows Server 2012 R2 o Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="155cf-121">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="155cf-122">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="155cf-122">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="155cf-123">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="155cf-123">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="155cf-124">\*È necessario installare Microsoft .NET Framework 4.5*x* e poi Windows Management Framework 3.0 o Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="155cf-124">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="155cf-125">Per altre informazioni, vedere [Installazione di .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) o [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span><span class="sxs-lookup"><span data-stu-id="155cf-125">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="155cf-126">È necessario utilizzare una versione a 64 bit di Windows, a causa dei requisiti, per il modulo di Skype for Business Online e una per moduli di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="155cf-126">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="155cf-127">È necessario installare i moduli necessari per Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online e Teams:</span><span class="sxs-lookup"><span data-stu-id="155cf-127">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="155cf-128">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="155cf-128">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="155cf-129">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="155cf-129">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="155cf-130">Modulo Windows PowerShell per Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="155cf-130">Skype for Business Online, Windows PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="155cf-131">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="155cf-131">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="155cf-132">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="155cf-132">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="155cf-133">Windows PowerShell deve essere configurato per l'esecuzione di script firmati per Skype for Business Online e il Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="155cf-133">Windows PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="155cf-134">A tale scopo, eseguire il comando seguente in una sessione di Windows PowerShell con privilegi elevati (una finestra Windows PowerShell che si apre selezionando **Esegui come amministratore**).</span><span class="sxs-lookup"><span data-stu-id="155cf-134">To do this, run the following command in an elevated Windows PowerShell session (a Windows PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="155cf-135">Procedura di connessione se si usa solo una password</span><span class="sxs-lookup"><span data-stu-id="155cf-135">Connection steps when using just a password</span></span>

<span data-ttu-id="155cf-136">Ecco la procedura per connettersi a tutti i servizi in una singola finestra di PowerShell se si usa solo una password per accedere.</span><span class="sxs-lookup"><span data-stu-id="155cf-136">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="155cf-137">Aprire Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="155cf-137">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="155cf-138">Eseguire il comando seguente e immettere le credenziali dell'account aziendale o dell'Istituto di istruzione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="155cf-138">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="155cf-139">Eseguire il comando seguente per connettersi ad Azure AD tramite il modulo Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="155cf-139">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="155cf-140">In alternativa, se si usa il Modulo di Microsoft Azure Active Directory per Windows PowerShell, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="155cf-140">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="155cf-141">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="155cf-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="155cf-142">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="155cf-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>

4. <span data-ttu-id="155cf-143">Eseguire i comandi seguenti per la connessione a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="155cf-143">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="155cf-144">Specificare il nome dell'organizzazione per il dominio.</span><span class="sxs-lookup"><span data-stu-id="155cf-144">Specify the organization name for your domain.</span></span> <span data-ttu-id="155cf-145">Ad esempio, per "litwareinc.onmicrosoft.com", il valore del nome dell’organizzazione è "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="155cf-145">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="155cf-146">Per connettersi a Skype for Business Online eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="155cf-146">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="155cf-147">Alla prima connessione verrà visualizzato l’avviso relativo all’aumento del valore `WSMan NetworkDelayms`, che deve essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="155cf-147">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="155cf-148">Eseguire il comando seguente per connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="155cf-148">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="155cf-149">Per connettersi a Exchange Online per i cloud di Microsoft 365 diversi da quello internazionale, usare il parametro **ExchangeEnvironmentName**.</span><span class="sxs-lookup"><span data-stu-id="155cf-149">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, use the **-ExchangeEnvironmentName** parameter.</span></span> <span data-ttu-id="155cf-150">Per altre informazioni, vedere [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="155cf-150">See [Connect-ExchangeOnline](https://docs.microsoft.com/powershell/module/exchange/powershell-v2-module/connect-exchangeonline?view=exchange-ps) for more information.</span></span>

7. <span data-ttu-id="155cf-151">Eseguire i comandi seguenti per connettersi a PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="155cf-151">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="155cf-152">Per connettersi ai cloud di Microsoft Teams diversi da quello internazionale, vedere [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="155cf-152">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps).</span></span>

8. <span data-ttu-id="155cf-153">Eseguire i comandi seguenti per connettersi al Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="155cf-153">Run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
   Import-PSSession $SccSession -Prefix cc
   ```

   > [!Note]
   > <span data-ttu-id="155cf-154">Per connettersi al Centro sicurezza &amp; conformità per i cloud Microsoft 365 diversi da quello internazionale, vedere [Connettersi a PowerShell per Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="155cf-154">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="155cf-155">Qui sono riportati tutti i comandi in un unico blocco se si usa il modulo di Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="155cf-155">Here are all the commands in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="155cf-156">Specificare il nome dell’host del dominio e poi eseguirli tutti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="155cf-156">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="155cf-157">In alternativa, di seguito sono riportati tutti i comandi in un singolo blocco se si usa il Modulo di Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="155cf-157">Alternately, here are all the commands in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="155cf-158">Specificare il nome dell’host del dominio e poi eseguirli tutti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="155cf-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
$SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $credential -Authentication "Basic" -AllowRedirection
Import-PSSession $SccSession -Prefix cc
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="155cf-159">Quando è tutto pronto per chiudere la finestra di Windows PowerShell, eseguire il comando seguente per rimuovere tutte le sessioni attive in Skype for Business Online, SharePoint Online, il Centro sicurezza &amp; conformità e Teams:</span><span class="sxs-lookup"><span data-stu-id="155cf-159">When you are ready to close down the Windows PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, the Security &amp; Compliance Center, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Remove-PSSession $SccSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="155cf-160">Procedura di connessione quando si usa l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="155cf-160">Connection steps when using multi-factor authentication</span></span>

<span data-ttu-id="155cf-161">Di seguito sono elencati tutti i comandi di un singolo blocco per connettersi ad Azure AD, SharePoint Online, Skype for Business, Exchange Online e Teams tramite l'autenticazione a più fattori in una singola finestra usando il modulo di Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="155cf-161">Here are all the commands in a single block to connect to Azure AD, SharePoint Online, Skype for Business, Exchange Online, and Teams using multi-factor authentication in a single window using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="155cf-162">Specificare il nome entità utente (UPN) per l’account utente e il nome dell’host del dominio, poi eseguirli tutti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="155cf-162">Specify the user principal name (UPN) name of a user account and your domain host name, and then run them all at one time.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="155cf-163">In alternativa, di seguito sono riportati tutti i comandi quando si usa il Modulo di Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="155cf-163">Alternately, here are all the commands when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

<span data-ttu-id="155cf-164">Per il Centro sicurezza &amp; conformità, vedere [Connettersi a PowerShell per Centro sicurezza e conformità con l'autenticazione a più fattori](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) per connettersi usando l'autenticazione a più fattori:</span><span class="sxs-lookup"><span data-stu-id="155cf-164">For the Security &amp; Compliance Center, see [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) to connect using multi-factor authentication:</span></span>

## <a name="see-also"></a><span data-ttu-id="155cf-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="155cf-165">See also</span></span>

- [<span data-ttu-id="155cf-166">Collegarsi a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="155cf-166">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="155cf-167">Gestire SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="155cf-167">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="155cf-168">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="155cf-168">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="155cf-169">Usare Windows PowerShell per creare report in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="155cf-169">Use Windows PowerShell to create reports in Microsoft 365</span></span>](use-windows-powershell-to-create-reports-in-microsoft-365.md)
