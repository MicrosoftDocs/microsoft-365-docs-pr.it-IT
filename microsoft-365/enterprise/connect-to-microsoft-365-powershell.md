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
ms.openlocfilehash: 70d6aa1373daf2322319d21e385fc1498af3351e
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782802"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="724e4-103">Collegare Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="724e4-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="724e4-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="724e4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="724e4-105">PowerShell per Microsoft 365 consente di gestire le impostazioni di Microsoft 365 dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="724e4-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="724e4-106">Per connettersi PowerShell basta installare il software richiesto e quindi connettersi alla propria organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="724e4-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="724e4-107">Sono disponibili due versioni del modulo PowerShell che è possibile usare per connettersi a Microsoft 365 e amministrare gli account utente, i gruppi e le licenze:</span><span class="sxs-lookup"><span data-stu-id="724e4-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="724e4-108">Azure Active Directory PowerShell per Graph, i cui cmdlet includono *AzureAD* nel nome</span><span class="sxs-lookup"><span data-stu-id="724e4-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="724e4-109">Modulo di Microsoft Azure Active Directory per Windows PowerShell, i cui cmdlet includono *MSol* nel nome.</span><span class="sxs-lookup"><span data-stu-id="724e4-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="724e4-p102">Attualmente, il modulo di Azure Active Directory PowerShell per Graph non sostituisce completamente le funzionalità del Modulo di Microsoft Azure Active Directory per Windows PowerShell per l'amministrazione utenti, gruppi e licenze. In alcuni casi, è necessario usare entrambe le versioni. Puoi installare in modo sicuro entrambe le versioni sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="724e4-p102">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration. In some cases, you need to use both versions. You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="724e4-113">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="724e4-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="724e4-114">**Sistema operativo**</span><span class="sxs-lookup"><span data-stu-id="724e4-114">**Operating system**</span></span>

<span data-ttu-id="724e4-p103">Devi usare una versione a 64 bit di Windows. Nel 2014 è finito il supporto per la versione a 32 bit del Modulo di Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="724e4-p103">You must use a 64-bit version of Windows. Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="724e4-117">È possibile utilizzare le seguenti versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="724e4-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="724e4-118">Windows 10, Windows 8.1, Windows 8 o Windows 7 Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="724e4-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="724e4-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="724e4-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="724e4-120">Per Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 e Windows Server 2008 R2 SP1, scaricare e installare [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="724e4-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="724e4-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="724e4-121">**PowerShell**</span></span>

- <span data-ttu-id="724e4-122">Per il modulo di Azure Active Directory PowerShell per Graph, è necessario usare PowerShell versione 5.1 o successive.</span><span class="sxs-lookup"><span data-stu-id="724e4-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="724e4-p104">Per il Modulo di Microsoft Azure Active Directory per Windows PowerShell, è necessario usare PowerShell versione 5.1 o successive fino alla versione 6. Non puoi usare PowerShell versione 7.</span><span class="sxs-lookup"><span data-stu-id="724e4-p104">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6. You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="724e4-125">Queste procedure sono destinate agli utenti membri di un ruolo di amministratore di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="724e4-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="724e4-126">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="724e4-126">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="724e4-127">Connettersi con il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="724e4-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="724e4-128">I comandi nel modulo di Azure Active Directory PowerShell per Graph hanno *AzureAD* nel nome del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="724e4-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="724e4-129">È possibile installare il [modulo di Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2) o [Azure PowerShell](/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="724e4-129">You can install the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="724e4-130">Per le procedure che richiedono i nuovi cmdlet nel modulo di Azure Active Directory PowerShell per Graph, seguire questi passaggi per installare il modulo e connettersi alla sottoscrizione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="724e4-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="724e4-131">Per informazioni sul supporto per le altre versioni di Windows, vedere [Modulo di Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="724e4-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="724e4-132">Passaggio 1: installare il software necessario</span><span class="sxs-lookup"><span data-stu-id="724e4-132">Step 1: Install the required software</span></span>

<span data-ttu-id="724e4-133">È necessario eseguire questi passaggi nel computer una sola volta.</span><span class="sxs-lookup"><span data-stu-id="724e4-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="724e4-134">Tuttavia, è probabile che sia necessario aggiornare periodicamente il software.</span><span class="sxs-lookup"><span data-stu-id="724e4-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="724e4-135">Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore).</span><span class="sxs-lookup"><span data-stu-id="724e4-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="724e4-136">Eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="724e4-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  <span data-ttu-id="724e4-137">Per impostazione predefinita, PowerShell Gallery (PSGallery) non è configurata come repository affidabile per **PowerShellGet**.</span><span class="sxs-lookup"><span data-stu-id="724e4-137">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="724e4-138">Al primo utilizzo di PSGallery, verrà visualizzato il seguente messaggio:</span><span class="sxs-lookup"><span data-stu-id="724e4-138">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="724e4-139">Rispondere **Sì** o **Sì a tutto** per continuare con l'installazione.</span><span class="sxs-lookup"><span data-stu-id="724e4-139">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="724e4-140">Passaggio 2: connettersi ad Azure AD per l'abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="724e4-140">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="724e4-p109">Per connettersi ad Azure AD per l’abbonamento a Microsoft 365 con un nome account e una password oppure con l'autenticazione a più fattori (MFA), esegui uno di questi comandi da un prompt dei comandi di Windows PowerShell. (Non deve essere elevato).</span><span class="sxs-lookup"><span data-stu-id="724e4-p109">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="724e4-143">Cloud di Office 365</span><span class="sxs-lookup"><span data-stu-id="724e4-143">Office 365 cloud</span></span> | <span data-ttu-id="724e4-144">Comando</span><span class="sxs-lookup"><span data-stu-id="724e4-144">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="724e4-145">Office 365 internazionale (+GCC)</span><span class="sxs-lookup"><span data-stu-id="724e4-145">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="724e4-146">Office 365 gestito da 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="724e4-146">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="724e4-147">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="724e4-147">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="724e4-148">U.S. Government DoD di Office 365 e U.S. Government GCC High di Office 365</span><span class="sxs-lookup"><span data-stu-id="724e4-148">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="724e4-149">Nella finestra di dialogo per **accedere all'account**, digitare nome utente e password dell'account aziendale o dell'istituto di istruzione di Microsoft 365, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="724e4-149">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="724e4-150">Se si utilizza l'autenticazione a più fattori, seguire le istruzioni per fornire ulteriori informazioni di autenticazione, ad esempio un codice di verifica.</span><span class="sxs-lookup"><span data-stu-id="724e4-150">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="724e4-151">Dopo aver eseguito la connessione, è possibile usare i cmdlet per il [modulo di Azure Active Directory PowerShell per Graph](/powershell/module/azuread).</span><span class="sxs-lookup"><span data-stu-id="724e4-151">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="724e4-152">Connettersi con il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="724e4-152">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="724e4-153">I cmdlet nel Modulo di Microsoft Azure Active Directory per Windows PowerShell hanno *MSol* nel nome.</span><span class="sxs-lookup"><span data-stu-id="724e4-153">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="724e4-154">PowerShell versione 7 e successive non supportano il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="724e4-154">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="724e4-155">Per PowerShell versione 7 e successive, è necessario usare il modulo di Azure Active Directory PowerShell per Graph o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="724e4-155">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="724e4-156">PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="724e4-156">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="724e4-157">Eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="724e4-157">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="724e4-158">Passaggio 1: installare il software necessario</span><span class="sxs-lookup"><span data-stu-id="724e4-158">Step 1: Install the required software</span></span>

<span data-ttu-id="724e4-159">È necessario eseguire questi passaggi nel computer una sola volta.</span><span class="sxs-lookup"><span data-stu-id="724e4-159">These steps are required only one time on your computer.</span></span> <span data-ttu-id="724e4-160">Tuttavia, è probabile che sia necessario aggiornare periodicamente il software.</span><span class="sxs-lookup"><span data-stu-id="724e4-160">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="724e4-161">Se non si esegue Windows 10, installare la versione a 64 bit dell'Assistente per l'accesso a Microsoft Online Services: [Assistente per l'accesso a Microsoft Online Services per professionisti IT - RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span><span class="sxs-lookup"><span data-stu-id="724e4-161">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).</span></span>
    
2. <span data-ttu-id="724e4-162">Seguire questa procedura per installare il Modulo di Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="724e4-162">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="724e4-163">Aprire un prompt dei comandi di Windows PowerShell con privilegi elevati (eseguire Windows PowerShell come amministratore).</span><span class="sxs-lookup"><span data-stu-id="724e4-163">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="724e4-164">Eseguire il comando **Install-Module MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="724e4-164">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="724e4-165">Se viene richiesto di installare il provider NuGet, digitare **Y** e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="724e4-165">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="724e4-166">Se viene richiesto di installare il modulo da PSGallery, digitare **Y** e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="724e4-166">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="724e4-167">Passaggio 2: connettersi ad Azure AD per l'abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="724e4-167">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="724e4-p113">Per connetterti ad Azure AD per l’abbonamento a Microsoft 365 con un nome account e una password oppure con l'autenticazione a più fattori (MFA), esegui uno di questi comandi da un prompt dei comandi di Windows PowerShell. (Non deve essere elevato).</span><span class="sxs-lookup"><span data-stu-id="724e4-p113">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt. (It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="724e4-170">Cloud di Office 365</span><span class="sxs-lookup"><span data-stu-id="724e4-170">Office 365 cloud</span></span> | <span data-ttu-id="724e4-171">Comando</span><span class="sxs-lookup"><span data-stu-id="724e4-171">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="724e4-172">Office 365 internazionale (+GCC)</span><span class="sxs-lookup"><span data-stu-id="724e4-172">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="724e4-173">Office 365 gestito da 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="724e4-173">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="724e4-174">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="724e4-174">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="724e4-175">U.S. Government DoD di Office 365 e U.S. Government GCC High di Office 365</span><span class="sxs-lookup"><span data-stu-id="724e4-175">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="724e4-176">Nella finestra di dialogo per **accedere all'account**, digitare nome utente e password dell'account aziendale o dell'istituto di istruzione di Microsoft 365, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="724e4-176">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="724e4-177">Se si utilizza l'autenticazione a più fattori, seguire le istruzioni per fornire ulteriori informazioni di autenticazione, ad esempio un codice di verifica.</span><span class="sxs-lookup"><span data-stu-id="724e4-177">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="724e4-178">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="724e4-178">How do you know it worked?</span></span>

<span data-ttu-id="724e4-179">Se non viene visualizzato un messaggio di errore, la connessione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="724e4-179">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="724e4-180">Per un rapido test, eseguire un cmdlet di Microsoft 365, ad esempio, **Get-MsolUser** e vedere i risultati.</span><span class="sxs-lookup"><span data-stu-id="724e4-180">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="724e4-181">Se viene visualizzato un messaggio di errore, controllare i problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="724e4-181">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="724e4-182">**Un problema comune è l'uso di una password errata**.</span><span class="sxs-lookup"><span data-stu-id="724e4-182">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="724e4-183">Eseguire di nuovo il [Passaggio 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) e prestare particolare attenzione al nome utente e alla password immessi.</span><span class="sxs-lookup"><span data-stu-id="724e4-183">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="724e4-184">**Il Modulo di Microsoft Azure Active Directory per Windows PowerShell richiede che Microsoft .NET Framework 3.5.* x* sia abilitato nel computer**. È probabile che nel computer sia installata una versione più recente, ad esempio 4 o 4.5.* x*.</span><span class="sxs-lookup"><span data-stu-id="724e4-184">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="724e4-185">La compatibilità con le versioni precedenti di .NET Framework può però essere abilitata o disabilitata.</span><span class="sxs-lookup"><span data-stu-id="724e4-185">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="724e4-186">Per altre informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="724e4-186">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="724e4-187">Per Windows Server 2012 o Windows Server 2012 R2, vedere [Abilitare .NET Framework 3.5 con Aggiunta guidata ruoli e funzionalità](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span><span class="sxs-lookup"><span data-stu-id="724e4-187">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).</span></span>
    
  - <span data-ttu-id="724e4-188">Per Windows 7 o Windows Server 2008 R2, vedere [Impossibile aprire il Modulo di Azure Active Directory per Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span><span class="sxs-lookup"><span data-stu-id="724e4-188">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).</span></span>

  - <span data-ttu-id="724e4-189">Per Windows 10, Windows 8.1 e Windows 8, vedere [Installare .NET Framework 3.5 in Windows 10, Windows 8.1 e Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span><span class="sxs-lookup"><span data-stu-id="724e4-189">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="724e4-190">**La versione di Microsoft Azure Active Directory Module per Windows PowerShell in uso potrebbe essere obsoleta.**</span><span class="sxs-lookup"><span data-stu-id="724e4-190">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="724e4-191">Per verificarlo, eseguire il seguente comando in PowerShell per Microsoft 365 o il modulo di Microsoft Azure Active Directory per Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="724e4-191">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="724e4-192">Se il numero di versione restituito è inferiore a *1.0.8070.2*, disinstallare il Modulo di Microsoft Azure Active Directory per Windows PowerShell e ripetere l'installazione dal [Passaggio 1](#step-1-install-the-required-software).</span><span class="sxs-lookup"><span data-stu-id="724e4-192">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="724e4-193">**Se viene visualizzato un errore di connessione**, vedere [Errore "Connect-MsolService: si è verificata un'eccezione di tipo"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span><span class="sxs-lookup"><span data-stu-id="724e4-193">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).</span></span>
    
- <span data-ttu-id="724e4-194">**Se viene visualizzato un messaggio di errore "Get-Item: impossibile trovare il percorso", eseguire questo comando:**</span><span class="sxs-lookup"><span data-stu-id="724e4-194">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="724e4-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="724e4-195">See also</span></span>

- [<span data-ttu-id="724e4-196">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="724e4-196">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="724e4-197">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="724e4-197">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="724e4-198">Effettuare la connessione a tutti i servizi Office 365 in un'unica finestra di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="724e4-198">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
