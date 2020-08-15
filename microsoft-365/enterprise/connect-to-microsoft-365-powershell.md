---
title: Collegare Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Connettersi al tenant di Microsoft 365 con PowerShell per Microsoft 365 per eseguire attività dell'interfaccia di amministrazione tramite riga di comando.
ms.openlocfilehash: d1e347a13ca5c587fa544ef80a8e289a8dec0a59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691306"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="5df66-103">Collegare Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5df66-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="5df66-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="5df66-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5df66-105">PowerShell per Microsoft 365 consente di gestire le impostazioni di Microsoft 365 tramite riga di comando.</span><span class="sxs-lookup"><span data-stu-id="5df66-105">PowerShell for Microsoft 365 lets you manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="5df66-106">La connessione a PowerShell è una semplice procedura che prevede di installare il software richiesto e quindi connettersi alla propria organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5df66-106">Connecting to PowerShell is a simple process where you install the required software and then connect to your Microsoft 365 organization.</span></span> 

<span data-ttu-id="5df66-107">Sono disponibili due versioni del modulo di PowerShell da utilizzare per connettersi a Microsoft 365 e gestire gli account utente, i gruppi e le licenze:</span><span class="sxs-lookup"><span data-stu-id="5df66-107">There are two versions of the PowerShell module that you use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="5df66-108">Azure Active Directory PowerShell per Graph (i cmdlet includono **AzureAD** nel nome)</span><span class="sxs-lookup"><span data-stu-id="5df66-108">Azure Active Directory PowerShell for Graph (cmdlets include **AzureAD** in their name)</span></span>
- <span data-ttu-id="5df66-109">Modulo di Microsoft Azure Active Directory per Windows PowerShell (i cmdlet includono **MSol** nel nome)</span><span class="sxs-lookup"><span data-stu-id="5df66-109">Microsoft Azure Active Directory Module for Windows PowerShell (cmdlets include **MSol** in their name)</span></span> 

<span data-ttu-id="5df66-110">A partire dalla data di pubblicazione di questo articolo, il modulo di Azure Active Directory PowerShell per Graph non sostituisce completamente le funzionalità nei cmdlet del Modulo di Microsoft Azure Active Directory per Windows PowerShell per l'amministrazione di utenti, gruppi e licenze.</span><span class="sxs-lookup"><span data-stu-id="5df66-110">As of the date of this article, the Azure Active Directory PowerShell for Graph module does not completely replace the functionality in the cmdlets of Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="5df66-111">In alcuni casi, è necessario usare entrambe le versioni.</span><span class="sxs-lookup"><span data-stu-id="5df66-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="5df66-112">È possibile installare tranquillamente entrambe le versioni nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="5df66-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5df66-113">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5df66-113">What do you need to know before you begin?</span></span>

<span data-ttu-id="5df66-114">È possibile utilizzare le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="5df66-114">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="5df66-115">Windows 10, Windows 8.1, Windows 8 o Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="5df66-115">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="5df66-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="5df66-116">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

    > [!NOTE]
    > <span data-ttu-id="5df66-117">Per il modulo Azure Active Directory PowerShell per Graph, è necessario usare PowerShell versione 5.1 o successive.</span><span class="sxs-lookup"><span data-stu-id="5df66-117">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span> <span data-ttu-id="5df66-118">Per il modulo di Microsoft Azure Active Directory per Windows PowerShell, è necessario usare PowerShell versione 5.1 o successive fino alla versione 6.</span><span class="sxs-lookup"><span data-stu-id="5df66-118">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later up to PowerShell version 6.</span></span> <span data-ttu-id="5df66-119">Non è possibile usare la versione 7 di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5df66-119">You cannot use PowerShell version 7.</span></span> <span data-ttu-id="5df66-120">Per Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 e Windows Server 2008 R2 SP1, scaricare e installare [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="5df66-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5df66-p104">Usare una versione a 64 bit di Windows. A ottobre del 2014 è stato sospeso il supporto per la versione a 32 bit del Modulo di Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5df66-p104">Use a 64-bit version of Windows. Support for the 32-bit version the Microsoft Azure Active Directory Module for Windows PowerShell was discontinued in October of 2014.</span></span>
    
<span data-ttu-id="5df66-123">Queste procedure sono destinate agli utenti membri di un ruolo di amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5df66-123">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="5df66-124">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span><span class="sxs-lookup"><span data-stu-id="5df66-124">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="5df66-125">Connettersi con il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="5df66-125">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="5df66-126">I comandi nel modulo di Azure Active Directory PowerShell per Graph hanno **AzureAD** nel nome del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5df66-126">Commands in the Azure Active Directory PowerShell for Graph module have **AzureAD** in their cmdlet name.</span></span> <span data-ttu-id="5df66-127">È possibile installare il [modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) o [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1).</span><span class="sxs-lookup"><span data-stu-id="5df66-127">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-3.6.1).</span></span>

<span data-ttu-id="5df66-128">Per le procedure che necessitano di nuovi cmdlet nel modulo di Azure Active Directory PowerShell per Graph, eseguire questi passaggi per installare il modulo e connettersi alla sottoscrizione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5df66-128">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, use these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="5df66-129">Vedere [Modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) per informazioni sul supporto per le altre versioni di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="5df66-129">See [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory) for information about the support for different versions of Microsoft Windows.</span></span>
>

### <a name="step-1-install-required-software"></a><span data-ttu-id="5df66-130">Passaggio 1: installare il software necessario</span><span class="sxs-lookup"><span data-stu-id="5df66-130">Step 1: Install required software</span></span>

<span data-ttu-id="5df66-p107">È sufficiente effettuare questa procedura solo una volta, non ogni volta che ci si connette. Tuttavia, probabilmente sarà necessario installare periodicamente le versioni più recenti del software.</span><span class="sxs-lookup"><span data-stu-id="5df66-p107">These steps are required once on your computer, not every time you connect. However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1. <span data-ttu-id="5df66-133">Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore).</span><span class="sxs-lookup"><span data-stu-id="5df66-133">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="5df66-134">Nella finestra di comando **Amministratore: Windows PowerShell**, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5df66-134">In the **Administrator: Windows PowerShell** command window, run this command:</span></span>
    
  ```powershell
  Install-Module -Name AzureAD
  ```

<span data-ttu-id="5df66-135">Se viene richiesto di installare un modulo da un archivio non attendibile, digitare **Y** e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="5df66-135">If prompted about installing a module from an untrusted repository, type **Y** and press ENTER.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="5df66-136">Passaggio 2: connettersi ad Azure AD per abbonarsi a Office 365</span><span class="sxs-lookup"><span data-stu-id="5df66-136">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="5df66-137">Per connettersi ad Azure AD per la sottoscrizione a Microsoft 365 con un nome dell'account e una password o con l'autenticazione a più fattori (MFA), eseguire uno di questi comandi da un prompt dei comandi di Windows PowerShell (che non sia con privilegi elevati).</span><span class="sxs-lookup"><span data-stu-id="5df66-137">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="5df66-138">Cloud di Office 365</span><span class="sxs-lookup"><span data-stu-id="5df66-138">Office 365 cloud</span></span> | <span data-ttu-id="5df66-139">Comando</span><span class="sxs-lookup"><span data-stu-id="5df66-139">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="5df66-140">Office 365 internazionale (+GCC)</span><span class="sxs-lookup"><span data-stu-id="5df66-140">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="5df66-141">Office 365 gestito da 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="5df66-141">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="5df66-142">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="5df66-142">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="5df66-143">U.S. Government DoD di Office 365 e U.S. Government GCC High di Office 365</span><span class="sxs-lookup"><span data-stu-id="5df66-143">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="5df66-144">Nella finestra di dialogo per **accedere all'account**, digitare nome utente e password dell'account dell'istituto di istruzione o aziendale di Microsoft 365, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5df66-144">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="5df66-145">Se si utilizza l'autenticazione a più fattori, seguire le istruzioni nelle finestre di dialogo aggiuntive per fornire ulteriori informazioni di autenticazione, ad esempio un codice di verifica.</span><span class="sxs-lookup"><span data-stu-id="5df66-145">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

<span data-ttu-id="5df66-146">Dopo aver eseguito la connessione, è possibile utilizzare i cmdlet per il [modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span><span class="sxs-lookup"><span data-stu-id="5df66-146">After connecting, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azuread/v2/azureactivedirectory).</span></span>
  

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="5df66-147">Connettersi con il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5df66-147">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="5df66-148">I comandi nel Modulo di Microsoft Azure Active Directory per Windows PowerShell hanno **MSol** nel nome del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5df66-148">Commands in the Microsoft Azure Active Directory Module for Windows PowerShell have **Msol** in their cmdlet name.</span></span>

<span data-ttu-id="5df66-149">PowerShell versione 7 e successive non supportano il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="5df66-149">PowerShell version 7 and later do not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="5df66-150">Per PowerShell versione 7 e successive, è necessario usare il modulo Azure Active Directory PowerShell per Graph o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5df66-150">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="5df66-151">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="5df66-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="5df66-152">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5df66-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span> 
    
### <a name="step-1-install-required-software"></a><span data-ttu-id="5df66-153">Passaggio 1: installare il software necessario</span><span class="sxs-lookup"><span data-stu-id="5df66-153">Step 1: Install required software</span></span>

<span data-ttu-id="5df66-p110">È sufficiente effettuare questa procedura solo una volta, non ogni volta che ci si connette. Tuttavia, probabilmente sarà necessario installare periodicamente le versioni più recenti del software.</span><span class="sxs-lookup"><span data-stu-id="5df66-p110">These steps are required once on your computer, not every time you connect. However, you'll likely need to install newer versions of the software periodically.</span></span>
  
1.  <span data-ttu-id="5df66-156">Se non si sta eseguendo Windows 10, installare la versione a 64 bit dell'Assistente per l'accesso a Microsoft Online Services: [Assistente per l'accesso a Microsoft Online Services per professionisti IT - RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="5df66-156">If you are not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
    
2. <span data-ttu-id="5df66-157">Installare il Modulo di Microsoft Azure Active Directory per Windows PowerShell con la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="5df66-157">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
  - <span data-ttu-id="5df66-158">Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore).</span><span class="sxs-lookup"><span data-stu-id="5df66-158">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
  - <span data-ttu-id="5df66-159">Eseguire il comando **Install-Module MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="5df66-159">Run the **Install-Module MSOnline** command.</span></span>
  - <span data-ttu-id="5df66-160">Se viene richiesto di installare il provider NuGet, digitare **Y** e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="5df66-160">If prompted to install the NuGet provider, type **Y** and press ENTER.</span></span>
  - <span data-ttu-id="5df66-161">Se viene richiesto di installare il modulo da PSGallery, digitare **Y** e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="5df66-161">If prompted to install the module from PSGallery, type **Y** and press ENTER.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="5df66-162">Passaggio 2: connettersi ad Azure AD per abbonarsi a Office 365</span><span class="sxs-lookup"><span data-stu-id="5df66-162">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="5df66-163">Per connettersi ad Azure AD per la sottoscrizione a Microsoft 365 con un nome dell'account e una password o con l'autenticazione a più fattori (MFA), eseguire uno di questi comandi da un prompt dei comandi di Windows PowerShell (che non sia con privilegi elevati).</span><span class="sxs-lookup"><span data-stu-id="5df66-163">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication (MFA), run one of these commands from a Windows PowerShell command prompt (it does not have to be elevated).</span></span>

| <span data-ttu-id="5df66-164">Cloud di Office 365</span><span class="sxs-lookup"><span data-stu-id="5df66-164">Office 365 cloud</span></span> | <span data-ttu-id="5df66-165">Comando</span><span class="sxs-lookup"><span data-stu-id="5df66-165">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="5df66-166">Office 365 internazionale (+GCC)</span><span class="sxs-lookup"><span data-stu-id="5df66-166">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="5df66-167">Office 365 gestito da 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="5df66-167">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="5df66-168">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="5df66-168">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="5df66-169">U.S. Government DoD di Office 365 e U.S. Government GCC High di Office 365</span><span class="sxs-lookup"><span data-stu-id="5df66-169">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="5df66-170">Nella finestra di dialogo per **accedere all'account**, digitare nome utente e password dell'account dell'istituto di istruzione o aziendale di Microsoft 365, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5df66-170">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then click **OK**.</span></span>

<span data-ttu-id="5df66-171">Se si utilizza l'autenticazione a più fattori, seguire le istruzioni nelle finestre di dialogo aggiuntive per fornire ulteriori informazioni di autenticazione, ad esempio un codice di verifica.</span><span class="sxs-lookup"><span data-stu-id="5df66-171">If you are using MFA, follow the instructions in the additional dialog boxes to provide more authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5df66-172">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="5df66-172">How do you know this worked?</span></span>

<span data-ttu-id="5df66-173">Se non vengono visualizzati errori, la connessione è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="5df66-173">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="5df66-174">Un breve test consiste nell'eseguire un cmdlet di Microsoft 365; ad esempio, **Get-MsolUser** e vedere i risultati.</span><span class="sxs-lookup"><span data-stu-id="5df66-174">A quick test is to run a Microsoft 365 cmdlet—for example, **Get-MsolUser** —and see the results.</span></span>
  
<span data-ttu-id="5df66-175">Se non vengono visualizzati errori, controllare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5df66-175">If you receive errors, check the following requirements:</span></span>
  
- <span data-ttu-id="5df66-p112">**Un problema comune è rappresentato da una password errata**. Ripetere il passaggio 2 e prestare particolare attenzione al nome utente e alla password immessi.</span><span class="sxs-lookup"><span data-stu-id="5df66-p112">**A common problem is an incorrect password**. Run Step 2 again. and pay close attention to the user name and password you enter.</span></span>
    
- <span data-ttu-id="5df66-p113">**Il Modulo di Microsoft Azure Active Directory per Windows PowerShell richiede che la funzione Microsoft .NET Framework 3.5.* x* sia attiva sul computer in uso. È probabile che il computer disponga di una versione più recente (ad esempio, 4 o 4.5.\* x\*), ma la compatibilità con le versioni precedenti di .NET Framework può essere abilitata o disabilitata. Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="5df66-p113">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that the Microsoft .NET Framework 3.5.* x* feature is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*), but backwards compatibility with older versions of the .NET Framework can be enabled or disabled. For more information, see the following topics:</span></span>
    
  - <span data-ttu-id="5df66-181">Per Windows Server 2012 o Windows Server 2012 R2, vedere [Abilitare .NET Framework 3.5 con Aggiunta guidata ruoli e funzionalità](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span><span class="sxs-lookup"><span data-stu-id="5df66-181">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368)</span></span>
    
  - <span data-ttu-id="5df66-182">Per Windows 7 o Windows Server 2008 R2, vedere [Impossibile aprire il Modulo di Azure Active Directory per Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span><span class="sxs-lookup"><span data-stu-id="5df66-182">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370)</span></span>

  - <span data-ttu-id="5df66-183">Per Windows 10, Windows 8.1 e Windows 8, vedere [Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span><span class="sxs-lookup"><span data-stu-id="5df66-183">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10)</span></span>

  
- <span data-ttu-id="5df66-184">**La versione di Microsoft Azure Active Directory Module per Windows PowerShell in uso potrebbe essere obsoleta.**</span><span class="sxs-lookup"><span data-stu-id="5df66-184">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="5df66-185">Per verificarlo, eseguire il seguente comando in PowerShell per Microsoft 365 o il modulo di Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5df66-185">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="5df66-186">Se il numero della versione restituito è inferiore al valore 1.0.8070.2, disinstallare il Modulo di Microsoft Azure Active Directory per Windows PowerShell e ripetere l'installazione dal Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="5df66-186">If the version number returned is lower than the value 1.0.8070.2, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from Step 1 above.</span></span>

- <span data-ttu-id="5df66-187">**Se viene visualizzato un errore di connessione, vedere l'argomento:** [Errore "La connessione-MsolService: eccezione di tipo"](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span><span class="sxs-lookup"><span data-stu-id="5df66-187">**If you receive a connection error, see this topic:** ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="5df66-188">**Se viene visualizzato un messaggio di errore "Get-Item: impossibile trovare il percorso", usare questo comando:**</span><span class="sxs-lookup"><span data-stu-id="5df66-188">**If you receive a "Get-Item : Cannot find path" error, use this command:**</span></span> 

```powershell
  (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
```

## <a name="see-also"></a><span data-ttu-id="5df66-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5df66-189">See also</span></span>

- [<span data-ttu-id="5df66-190">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5df66-190">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="5df66-191">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5df66-191">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="5df66-192">Effettuare la connessione a tutti i servizi Office 365 in un'unica finestra di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5df66-192">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
