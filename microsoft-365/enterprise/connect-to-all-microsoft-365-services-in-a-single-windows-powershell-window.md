---
title: Effettuare la connessione a tutti i servizi di Microsoft 365 in un'unica finestra di PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
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
ms.openlocfilehash: 08d2f4c6ce67aa9fea196d56b2eb5f36a36d7943
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430047"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a><span data-ttu-id="37948-103">Effettuare la connessione a tutti i servizi di Microsoft 365 in un'unica finestra di PowerShell</span><span class="sxs-lookup"><span data-stu-id="37948-103">Connect to all Microsoft 365 services in a single PowerShell window</span></span>

<span data-ttu-id="37948-104">Se si usa PowerShell per la gestione di Microsoft 365, è possibile avere più sessioni PowerShell aperte contemporaneamente in diverse finestre PowerShell corrispondenti alla gestione degli account utente, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams e il Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="37948-104">When you use PowerShell to manage Microsoft 365, it is possible to have multiple PowerShell sessions open at the same time in different PowerShell windows corresponding to managing user accounts, SharePoint Online, Exchange Online, Skype for Business Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="37948-105">Non si tratta di una condizione ottimale per la gestione di Microsoft 365, poiché non è possibile scambiare dati tra le finestre per la gestione dei diversi servizi.</span><span class="sxs-lookup"><span data-stu-id="37948-105">This is not optimal for managing Microsoft 365 because you can't exchange data among those windows for cross-service management.</span></span> <span data-ttu-id="37948-106">Questo argomento descrive come usare una singola istanza di PowerShell da cui gestire gli account di Microsoft 365, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams e il Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="37948-106">This topic describes how to use a single instance of PowerShell from which you can manage Microsoft 365 accounts, Skype for Business Online, Exchange Online, SharePoint Online, Microsoft Teams, and the Security &amp; Compliance Center.</span></span>

>[!Note]
><span data-ttu-id="37948-107">Questo articolo contiene al momento solo i comandi per connettersi al cloud internazionale (+GCC).</span><span class="sxs-lookup"><span data-stu-id="37948-107">This article currently only contains the commands to connect to the Worldwide (+GCC) cloud.</span></span> <span data-ttu-id="37948-108">Le note forniscono collegamenti agli articoli con informazioni sulla connessione ad altri cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37948-108">Notes provide links to articles with information about connecting to the other Microsoft 365 clouds.</span></span>
>

## <a name="before-you-begin"></a><span data-ttu-id="37948-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="37948-109">Before you begin</span></span>

<span data-ttu-id="37948-110">Per poter gestire tutti i servizi di Microsoft 365 da una singola istanza di PowerShell, prendere in considerazione i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="37948-110">Before you can manage all of Microsoft 365 from a single instance of PowerShell, consider the following prerequisites:</span></span>
  
- <span data-ttu-id="37948-111">L'account aziendale o dell'Istituto di istruzione di Microsoft 365 usato per queste procedure deve avere un ruolo di amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37948-111">The Microsoft 365 work or school account that you use for these procedures needs to be a member of a Microsoft 365 admin role.</span></span> <span data-ttu-id="37948-112">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="37948-112">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span> <span data-ttu-id="37948-113">Questo è un requisito per PowerShell per Microsoft 365, quindi non necessariamente per tutti gli altri servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37948-113">This a requirement for PowerShell for Microsoft 365, not necessarily for all other Microsoft 365 services.</span></span>
    
- <span data-ttu-id="37948-114">È possibile usare le seguenti versioni a 64 bit di Windows:</span><span class="sxs-lookup"><span data-stu-id="37948-114">You can use the following 64-bit versions of Windows:</span></span>
    
  - <span data-ttu-id="37948-115">Windows 10</span><span class="sxs-lookup"><span data-stu-id="37948-115">Windows 10</span></span>
    
  - <span data-ttu-id="37948-116">Windows 8.1 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="37948-116">Windows 8.1 or Windows 8</span></span>
    
  - <span data-ttu-id="37948-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="37948-117">Windows Server 2019</span></span>
    
  - <span data-ttu-id="37948-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="37948-118">Windows Server 2016</span></span>
    
  - <span data-ttu-id="37948-119">Windows Server 2012 R2 o Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="37948-119">Windows Server 2012 R2 or Windows Server 2012</span></span>
    
  - <span data-ttu-id="37948-120">Windows 7 Service Pack 1 (SP1)\*</span><span class="sxs-lookup"><span data-stu-id="37948-120">Windows 7 Service Pack 1 (SP1)\*</span></span>
    
  - <span data-ttu-id="37948-121">Windows Server 2008 R2 SP1\*</span><span class="sxs-lookup"><span data-stu-id="37948-121">Windows Server 2008 R2 SP1\*</span></span>
    
    <span data-ttu-id="37948-122">\*È necessario installare Microsoft .NET Framework 4.5*x* e poi Windows Management Framework 3.0 o Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="37948-122">\* You need to install the Microsoft .NET Framework 4.5.*x* and then either the Windows Management Framework 3.0 or the Windows Management Framework 4.0.</span></span> <span data-ttu-id="37948-123">Per altre informazioni, vedere [Installazione di .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868), [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) o [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span><span class="sxs-lookup"><span data-stu-id="37948-123">For more information, see [Installing the .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) and [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) or [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).</span></span>
    
    <span data-ttu-id="37948-124">È necessario utilizzare una versione a 64 bit di Windows, a causa dei requisiti, per il modulo di Skype for Business Online e una per moduli di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37948-124">You need to use a 64-bit version of Windows because of the requirements for the Skype for Business Online module and one of the Microsoft 365 modules.</span></span>
    
- <span data-ttu-id="37948-125">È necessario installare i moduli necessari per Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online e Teams:</span><span class="sxs-lookup"><span data-stu-id="37948-125">You need to install the modules that are required for Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype for Business Online and Teams:</span></span>
    
   - [<span data-ttu-id="37948-126">Azure Active Directory V2</span><span class="sxs-lookup"><span data-stu-id="37948-126">Azure Active Directory V2</span></span>](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   - [<span data-ttu-id="37948-127">SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="37948-127">SharePoint Online Management Shell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=255251)
   - [<span data-ttu-id="37948-128">Skype for Business Online, moduli PowerShell</span><span class="sxs-lookup"><span data-stu-id="37948-128">Skype for Business Online, PowerShell Module</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=532439)
   - [<span data-ttu-id="37948-129">Exchange Online PowerShell V2</span><span class="sxs-lookup"><span data-stu-id="37948-129">Exchange Online PowerShell V2</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
   - [<span data-ttu-id="37948-130">Panoramica di PowerShell per Teams</span><span class="sxs-lookup"><span data-stu-id="37948-130">Teams PowerShell Overview</span></span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  <span data-ttu-id="37948-131">PowerShell deve essere configurato per l'esecuzione di script firmati per Skype for Business Online e il Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="37948-131">PowerShell needs to be configured to run signed scripts for Skype for Business Online and the Security &amp; Compliance Center.</span></span> <span data-ttu-id="37948-132">A tale scopo, eseguire il comando seguente in una sessione di PowerShell con privilegi elevati (una finestra PowerShell che si apre selezionando **Esegui come amministratore**).</span><span class="sxs-lookup"><span data-stu-id="37948-132">To do this, run the following command in an elevated PowerShell session (a PowerShell window you open by selecting **Run as administrator**).</span></span>
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a><span data-ttu-id="37948-133">Exchange Online e Centro sicurezza &amp; conformità con il modulo PowerShell V2 di Exchange Online </span><span class="sxs-lookup"><span data-stu-id="37948-133">Exchange Online and Security &amp; Compliance Center with the Exchange Online PowerShell V2 module</span></span>

<span data-ttu-id="37948-134">In questo articolo, si usa il modulo PowerShell V2 di Exchange Online per connettersi a Exchange Online e al Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="37948-134">This article uses the Exchange Online PowerShell V2 module to connect to both Exchange Online and Security &amp; Compliance Center.</span></span> <span data-ttu-id="37948-135">Al momento, tuttavia, non è possibile connettersi sia a Exchange Online che al Centro sicurezza &amp; conformità \*\* nella stessa finestra di PowerShell\*\*.</span><span class="sxs-lookup"><span data-stu-id="37948-135">However, at this time you cannot connect to both Exchange Online and the Security &amp; Compliance Center **in the same PowerShell window**.</span></span>

<span data-ttu-id="37948-136">Di conseguenza, è necessario scegliere una connessione con Exchange Online *o* il Centro sicurezza &amp; conformità durante la configurazione di una finestra di PowerShell per molteplici servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37948-136">Therefore, you must choose a connection with either Exchange Online *or* the Security &amp; Compliance Center when configuring a PowerShell window for multiple Microsoft 365 services.</span></span>

## <a name="connection-steps-when-using-just-a-password"></a><span data-ttu-id="37948-137">Procedura di connessione se si usa solo una password</span><span class="sxs-lookup"><span data-stu-id="37948-137">Connection steps when using just a password</span></span>

<span data-ttu-id="37948-138">Ecco la procedura per connettersi a tutti i servizi in una singola finestra di PowerShell se si usa solo una password per accedere.</span><span class="sxs-lookup"><span data-stu-id="37948-138">Here are the steps to connect to all the services in a single PowerShell window when you are using just a password for sign-in.</span></span>
  
1. <span data-ttu-id="37948-139">Aprire Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37948-139">Open Windows PowerShell.</span></span>
    
2. <span data-ttu-id="37948-140">Eseguire il comando seguente e immettere le credenziali dell'account aziendale o dell'Istituto di istruzione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="37948-140">Run this command and enter your Microsoft 365 work or school account credentials.</span></span>
    
   ```powershell
   $credential = Get-Credential
   ```

3. <span data-ttu-id="37948-141">Eseguire il comando seguente per connettersi ad Azure AD tramite il modulo Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="37948-141">Run this command to connect to Azure AD using the Azure Active Directory PowerShell for Graph module.</span></span>
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   <span data-ttu-id="37948-142">In alternativa, se si usa il Modulo di Microsoft Azure Active Directory per Windows PowerShell, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="37948-142">Alternately, if you are using the Microsoft Azure Active Directory Module for Windows PowerShell module, run this command.</span></span>
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > <span data-ttu-id="37948-143">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="37948-143">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="37948-144">Per continuare a usare i cmdlet, è necessario eseguirli in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37948-144">To continue using these cmdlets, you must run them from PowerShell.</span></span>

4. <span data-ttu-id="37948-145">Eseguire i comandi seguenti per la connessione a SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="37948-145">Run these commands to connect to SharePoint Online.</span></span> <span data-ttu-id="37948-146">Specificare il nome dell'organizzazione per il dominio.</span><span class="sxs-lookup"><span data-stu-id="37948-146">Specify the organization name for your domain.</span></span> <span data-ttu-id="37948-147">Ad esempio, per "litwareinc.onmicrosoft.com", il valore del nome dell’organizzazione è "litwareinc".</span><span class="sxs-lookup"><span data-stu-id="37948-147">For example, for "litwareinc.onmicrosoft.com", the  organization name value is "litwareinc".</span></span>
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. <span data-ttu-id="37948-148">Per connettersi a Skype for Business Online eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="37948-148">Run these commands to connect to Skype for Business Online.</span></span> <span data-ttu-id="37948-149">Alla prima connessione verrà visualizzato l’avviso relativo all’aumento del valore `WSMan NetworkDelayms`, che deve essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="37948-149">A warning about increasing the `WSMan NetworkDelayms` value is expected the first time you connect and should be ignored.</span></span>
     
   ```powershell
   Import-Module SkypeOnlineConnector
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. <span data-ttu-id="37948-150">Eseguire il comando seguente per connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="37948-150">Run this command to connect to Exchange Online.</span></span>
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > <span data-ttu-id="37948-151">Per connettersi a Exchange Online per i cloud di Microsoft 365 diversi da quello internazionale, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="37948-151">To connect to Exchange Online for Microsoft 365 clouds other than Worldwide, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

7. <span data-ttu-id="37948-152">In alternativa, eseguire i comandi seguenti per connettersi al Centro sicurezza &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="37948-152">Alternately, run these commands to connect to the Security &amp; Compliance Center.</span></span>
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > <span data-ttu-id="37948-153">Per connettersi al Centro sicurezza &amp; conformità per i cloud di Microsoft 365 diversi da quello internazionale, vedere [Connettersi al Centro sicurezza e conformità di PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="37948-153">To connect to the Security &amp; Compliance Center for Microsoft 365 clouds other than Worldwide, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

8. <span data-ttu-id="37948-154">Eseguire i comandi seguenti per connettersi a PowerShell di Teams.</span><span class="sxs-lookup"><span data-stu-id="37948-154">Run these commands to connect to Teams PowerShell.</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > <span data-ttu-id="37948-155">Per connettersi ai cloud di Microsoft Teams diversi da quello internazionale, vedere [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span><span class="sxs-lookup"><span data-stu-id="37948-155">To connect to Microsoft Teams clouds other than Worldwide, see [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).</span></span>


### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="37948-156">Modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="37948-156">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="37948-157">Di seguito sono elencati i comandi per tutti i servizi *ad eccezione del Centro sicurezza &amp; conformità* in un unico blocco, quando si usa il modulo di Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="37948-157">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="37948-158">Specificare il nome dell’host del dominio e poi eseguirli tutti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="37948-158">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="37948-159">Di seguito sono elencati i comandi per tutti i servizi *ad eccezione di Exchange Online* in un unico blocco, quando si usa il modulo di Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="37948-159">Here are the commands for all of the services *except Exchange Online* in a single block when using the Azure Active Directory PowerShell for Graph module.</span></span> <span data-ttu-id="37948-160">Specificare il nome dell’host del dominio e l’UPN per l’accesso, e poi eseguirli tutti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="37948-160">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="37948-161">Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="37948-161">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="37948-162">Di seguito sono elencati i comandi per tutti i servizi *ad eccezione del Centro sicurezza &amp; conformità* in un unico blocco, quando si usa il modulo di Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37948-162">Here are the commands for all of the services *except Security &amp; Compliance Center* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="37948-163">Specificare il nome dell’host del dominio e poi eseguirli tutti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="37948-163">Specify the name of your domain host, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="37948-164">Di seguito sono elencati i comandi per tutti i servizi *ad eccezione di Exchange Online* in un unico blocco, quando si usa il modulo di Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37948-164">Here are the commands for all of the services *except Exchange Online* in a single block when using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span> <span data-ttu-id="37948-165">Specificare il nome dell’host del dominio e l’UPN per l’accesso, e poi eseguirli tutti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="37948-165">Specify the name of your domain host and the UPN for the sign-in, and then run them all at one time.</span></span>
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a><span data-ttu-id="37948-166">Procedura di connessione quando si usa l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="37948-166">Connection steps when using multi-factor authentication</span></span>

### <a name="azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="37948-167">Modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="37948-167">Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="37948-168">Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 *ad eccezione del Centro sicurezza &amp; conformità* con l'autenticazione a più fattori tramite il modulo di Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="37948-168">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="37948-169">Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 *ad eccezione di Exchange Online* con l'autenticazione a più fattori tramite il modulo di Azure Active Directory PowerShell per Graph.</span><span class="sxs-lookup"><span data-stu-id="37948-169">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* with multi-factor authentication using the Azure Active Directory PowerShell for Graph module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a><span data-ttu-id="37948-170">Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="37948-170">Microsoft Azure Active Directory Module for Windows PowerShell module</span></span>

<span data-ttu-id="37948-171">Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 *ad eccezione del Centro sicurezza &amp; conformità* con l'autenticazione a più fattori tramite il modulo di Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37948-171">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Security &amp; Compliance Center* with multi-factor authentication using the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
<span data-ttu-id="37948-172">Di seguito sono elencati tutti i comandi in un singolo blocco per connettersi a più servizi di Microsoft 365 *ad eccezione di Exchange Online* usando l'autenticazione a più fattori tramite il modulo di Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37948-172">Here are all the commands in a single block to connect to multiple Microsoft 365 services *except Exchange Online* using multi-factor authentication with the Microsoft Azure Active Directory Module for Windows PowerShell module.</span></span>

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
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a><span data-ttu-id="37948-173">Chiudere la finestra di PowerShell</span><span class="sxs-lookup"><span data-stu-id="37948-173">Close the PowerShell window</span></span>

<span data-ttu-id="37948-174">Quando è tutto pronto per chiudere la finestra di PowerShell, eseguire il comando seguente per rimuovere tutte le sessioni attive in Skype for Business Online, SharePoint Online e Teams:</span><span class="sxs-lookup"><span data-stu-id="37948-174">When you are ready to close down the PowerShell window, run this command to remove the active sessions to Skype for Business Online, SharePoint Online, and Teams:</span></span>
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a><span data-ttu-id="37948-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37948-175">See also</span></span>

- [<span data-ttu-id="37948-176">Collegarsi a Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="37948-176">Connect to Microsoft 365 with PowerShell</span></span>](connect-to-microsoft-365-powershell.md)
- [<span data-ttu-id="37948-177">Gestire SharePoint Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="37948-177">Manage SharePoint Online with PowerShell</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [<span data-ttu-id="37948-178">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="37948-178">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
