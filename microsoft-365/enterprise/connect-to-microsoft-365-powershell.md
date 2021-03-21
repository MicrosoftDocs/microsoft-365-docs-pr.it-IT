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
ms.openlocfilehash: 58af42958e9b50ee8e39cbd7bd5aab53812e444c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919177"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="42046-103">Collegare Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="42046-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="42046-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="42046-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="42046-105">PowerShell per Microsoft 365 consente di gestire le impostazioni di Microsoft 365 dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="42046-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="42046-106">Per connettersi PowerShell basta installare il software richiesto e quindi connettersi alla propria organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42046-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="42046-107">Sono disponibili due versioni del modulo PowerShell che è possibile usare per connettersi a Microsoft 365 e amministrare gli account utente, i gruppi e le licenze:</span><span class="sxs-lookup"><span data-stu-id="42046-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="42046-108">Azure Active Directory PowerShell per Graph, i cui cmdlet includono *AzureAD* nel nome</span><span class="sxs-lookup"><span data-stu-id="42046-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="42046-109">Modulo di Microsoft Azure Active Directory per Windows PowerShell, i cui cmdlet includono *MSol* nel nome.</span><span class="sxs-lookup"><span data-stu-id="42046-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="42046-110">Attualmente il modulo di Azure Active Directory PowerShell per Graph non sostituisce completamente le funzionalità del Modulo di Microsoft Azure Active Directory per Windows PowerShell per l'amministrazione di utenti, gruppi e licenze.</span><span class="sxs-lookup"><span data-stu-id="42046-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="42046-111">In alcuni casi, è necessario usare entrambe le versioni.</span><span class="sxs-lookup"><span data-stu-id="42046-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="42046-112">È possibile installare tranquillamente entrambe le versioni nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="42046-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="42046-113">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="42046-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="42046-114">**Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="42046-114">**Operating system**</span></span>

<span data-ttu-id="42046-115">È necessario usare versione a 64 bit di Windows.</span><span class="sxs-lookup"><span data-stu-id="42046-115">You must use a 64-bit version of Windows.</span></span> <span data-ttu-id="42046-116">Il supporto della versione a 32 bit del Modulo di Microsoft Azure Active Directory per Windows PowerShell è terminato nel 2014.</span><span class="sxs-lookup"><span data-stu-id="42046-116">Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="42046-117">È possibile utilizzare le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="42046-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="42046-118">Windows 10, Windows 8.1, Windows 8 o Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="42046-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="42046-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="42046-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="42046-120">Per Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 e Windows Server 2008 R2 SP1, scaricare e installare [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="42046-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="42046-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="42046-121">**PowerShell**</span></span>

- <span data-ttu-id="42046-122">Per il modulo di Azure Active Directory PowerShell per Graph, è necessario usare PowerShell versione 5.1 o successive.</span><span class="sxs-lookup"><span data-stu-id="42046-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="42046-123">Per il Modulo di Microsoft Azure Active Directory per Windows PowerShell, è necessario usare PowerShell versione 5.1 o successive fino alla versione 6.</span><span class="sxs-lookup"><span data-stu-id="42046-123">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6.</span></span> <span data-ttu-id="42046-124">Non è possibile usare la versione 7 di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42046-124">You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="42046-125">Queste procedure sono destinate agli utenti membri di un ruolo di amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42046-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="42046-126">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="42046-126">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="42046-127">Connettersi con il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="42046-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="42046-128">I comandi nel modulo di Azure Active Directory PowerShell per Graph hanno *AzureAD* nel nome del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="42046-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="42046-129">È possibile installare il [modulo di Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2) o [Azure PowerShell](/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="42046-129">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="42046-130">Per le procedure che richiedono i nuovi cmdlet nel modulo di Azure Active Directory PowerShell per Graph, seguire questi passaggi per installare il modulo e connettersi alla sottoscrizione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42046-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="42046-131">Per informazioni sul supporto per le altre versioni di Windows, vedere [Modulo di Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="42046-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="42046-132">Passaggio 1: installare il software necessario</span><span class="sxs-lookup"><span data-stu-id="42046-132">Step 1: Install the required software</span></span>

<span data-ttu-id="42046-133">È necessario eseguire questi passaggi nel computer una sola volta.</span><span class="sxs-lookup"><span data-stu-id="42046-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="42046-134">Tuttavia, è probabile che sia necessario aggiornare periodicamente il software.</span><span class="sxs-lookup"><span data-stu-id="42046-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="42046-135">Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore).</span><span class="sxs-lookup"><span data-stu-id="42046-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="42046-136">Eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="42046-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   <span data-ttu-id="42046-137">Se viene richiesto di installare un modulo da un archivio non attendibile, digitare **Y** e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="42046-137">If you're prompted to install a module from an untrusted repository, type **Y** and press Enter.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="42046-138">Passaggio 2: connettersi ad Azure AD per l'abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="42046-138">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="42046-139">Per connettersi ad Azure Active Directory (Azure AD) per l'abbonamento a Microsoft 365 con un nome account e una password oppure con l'autenticazione a più fattori (MFA), eseguire uno di questi comandi da un prompt dei comandi di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42046-139">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="42046-140">(non necessariamente con privilegi elevati).</span><span class="sxs-lookup"><span data-stu-id="42046-140">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="42046-141">Cloud di Office 365</span><span class="sxs-lookup"><span data-stu-id="42046-141">Office 365 cloud</span></span> | <span data-ttu-id="42046-142">Comando</span><span class="sxs-lookup"><span data-stu-id="42046-142">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="42046-143">Office 365 internazionale (+GCC)</span><span class="sxs-lookup"><span data-stu-id="42046-143">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="42046-144">Office 365 gestito da 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="42046-144">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="42046-145">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="42046-145">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="42046-146">U.S. Government DoD di Office 365 e U.S. Government GCC High di Office 365</span><span class="sxs-lookup"><span data-stu-id="42046-146">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="42046-147">Nella finestra di dialogo per **accedere all'account**, digitare nome utente e password dell'account aziendale o dell'istituto di istruzione di Microsoft 365, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="42046-147">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="42046-148">Se si utilizza l'autenticazione a più fattori, seguire le istruzioni per fornire ulteriori informazioni di autenticazione, ad esempio un codice di verifica.</span><span class="sxs-lookup"><span data-stu-id="42046-148">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="42046-149">Dopo aver eseguito la connessione, è possibile usare i cmdlet per il [modulo di Azure Active Directory PowerShell per Graph](/powershell/module/azuread).</span><span class="sxs-lookup"><span data-stu-id="42046-149">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="42046-150">Connettersi con il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42046-150">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="42046-151">I cmdlet nel Modulo di Microsoft Azure Active Directory per Windows PowerShell hanno *MSol* nel nome.</span><span class="sxs-lookup"><span data-stu-id="42046-151">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="42046-152">PowerShell versione 7 e successive non supportano il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="42046-152">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="42046-153">Per PowerShell versione 7 e successive, è necessario usare il modulo di Azure Active Directory PowerShell per Graph o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42046-153">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="42046-154">PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="42046-154">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="42046-155">Eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42046-155">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="42046-156">Passaggio 1: installare il software necessario</span><span class="sxs-lookup"><span data-stu-id="42046-156">Step 1: Install the required software</span></span>

<span data-ttu-id="42046-157">È necessario eseguire questi passaggi nel computer una sola volta.</span><span class="sxs-lookup"><span data-stu-id="42046-157">These steps are required only one time on your computer.</span></span> <span data-ttu-id="42046-158">Tuttavia, è probabile che sia necessario aggiornare periodicamente il software.</span><span class="sxs-lookup"><span data-stu-id="42046-158">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="42046-159">Se non si esegue Windows 10, installare la versione a 64 bit dell'Assistente per l'accesso a Microsoft Online Services: [Assistente per l'accesso a Microsoft Online Services per professionisti IT - RTW](https://www.microsoft.com/Download/details.aspx?id=28177).</span><span class="sxs-lookup"><span data-stu-id="42046-159">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://www.microsoft.com/Download/details.aspx?id=28177).</span></span>
    
2. <span data-ttu-id="42046-160">Seguire questa procedura per installare il Modulo di Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="42046-160">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="42046-161">Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore).</span><span class="sxs-lookup"><span data-stu-id="42046-161">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="42046-162">Eseguire il comando **Install-Module MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="42046-162">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="42046-163">Se viene richiesto di installare il provider NuGet, digitare **Y** e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="42046-163">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="42046-164">Se viene richiesto di installare il modulo da PSGallery, digitare **Y** e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="42046-164">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="42046-165">Passaggio 2: connettersi ad Azure AD per l'abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="42046-165">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="42046-166">Per connettersi ad Azure AD per l'abbonamento a Microsoft 365 con un nome account e una password oppure con l'autenticazione a più fattori (MFA), eseguire uno di questi comandi da un prompt dei comandi di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42046-166">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="42046-167">(non necessariamente con privilegi elevati).</span><span class="sxs-lookup"><span data-stu-id="42046-167">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="42046-168">Cloud di Office 365</span><span class="sxs-lookup"><span data-stu-id="42046-168">Office 365 cloud</span></span> | <span data-ttu-id="42046-169">Comando</span><span class="sxs-lookup"><span data-stu-id="42046-169">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="42046-170">Office 365 internazionale (+GCC)</span><span class="sxs-lookup"><span data-stu-id="42046-170">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="42046-171">Office 365 gestito da 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="42046-171">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="42046-172">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="42046-172">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="42046-173">U.S. Government DoD di Office 365 e U.S. Government GCC High di Office 365</span><span class="sxs-lookup"><span data-stu-id="42046-173">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="42046-174">Nella finestra di dialogo per **accedere all'account**, digitare nome utente e password dell'account aziendale o dell'istituto di istruzione di Microsoft 365, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="42046-174">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="42046-175">Se si utilizza l'autenticazione a più fattori, seguire le istruzioni per fornire ulteriori informazioni di autenticazione, ad esempio un codice di verifica.</span><span class="sxs-lookup"><span data-stu-id="42046-175">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="42046-176">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="42046-176">How do you know it worked?</span></span>

<span data-ttu-id="42046-177">Se non viene visualizzato un messaggio di errore, la connessione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="42046-177">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="42046-178">Per un rapido test, eseguire un cmdlet di Microsoft 365, ad esempio, **Get-MsolUser** e vedere i risultati.</span><span class="sxs-lookup"><span data-stu-id="42046-178">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="42046-179">Se viene visualizzato un messaggio di errore, controllare i problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="42046-179">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="42046-180">**Un problema comune è l'uso di una password errata**.</span><span class="sxs-lookup"><span data-stu-id="42046-180">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="42046-181">Eseguire di nuovo il [Passaggio 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) e prestare particolare attenzione al nome utente e alla password immessi.</span><span class="sxs-lookup"><span data-stu-id="42046-181">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="42046-182">**Il Modulo di Microsoft Azure Active Directory per Windows PowerShell richiede che Microsoft .NET Framework 3.5.* x* sia abilitato nel computer**. È probabile che nel computer sia installata una versione più recente, ad esempio 4 o 4.5.* x*.</span><span class="sxs-lookup"><span data-stu-id="42046-182">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="42046-183">La compatibilità con le versioni precedenti di .NET Framework può però essere abilitata o disabilitata.</span><span class="sxs-lookup"><span data-stu-id="42046-183">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="42046-184">Per altre informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="42046-184">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="42046-185">Per Windows Server 2012 o Windows Server 2012 R2, vedere [Abilitare .NET Framework 3.5 con Aggiunta guidata ruoli e funzionalità](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="42046-185">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="42046-186">Per Windows 7 o Windows Server 2008 R2, vedere [Impossibile aprire il Modulo di Azure Active Directory per Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span><span class="sxs-lookup"><span data-stu-id="42046-186">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="42046-187">Per Windows 10, Windows 8.1 e Windows 8, vedere [Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span><span class="sxs-lookup"><span data-stu-id="42046-187">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="42046-188">**La versione di Microsoft Azure Active Directory Module per Windows PowerShell in uso potrebbe essere obsoleta.**</span><span class="sxs-lookup"><span data-stu-id="42046-188">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="42046-189">Per verificarlo, eseguire il seguente comando in PowerShell per Microsoft 365 o il modulo di Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="42046-189">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="42046-190">Se il numero di versione restituito è inferiore a *1.0.8070.2*, disinstallare il Modulo di Microsoft Azure Active Directory per Windows PowerShell e ripetere l'installazione dal [Passaggio 1](#step-1-install-the-required-software).</span><span class="sxs-lookup"><span data-stu-id="42046-190">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="42046-191">**Se viene visualizzato un errore di connessione**, vedere [Errore "Connect-MsolService: si è verificata un'eccezione di tipo"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span><span class="sxs-lookup"><span data-stu-id="42046-191">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="42046-192">**Se viene visualizzato un messaggio di errore "Get-Item: impossibile trovare il percorso", eseguire questo comando:**</span><span class="sxs-lookup"><span data-stu-id="42046-192">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="42046-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42046-193">See also</span></span>

- [<span data-ttu-id="42046-194">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="42046-194">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="42046-195">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="42046-195">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="42046-196">Effettuare la connessione a tutti i servizi Office 365 in un'unica finestra di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42046-196">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)