---
title: Sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: "Riepilogo: configurare e illustrare la sincronizzazione hash delle password e l'accesso per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921505"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="76681-103">Sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="76681-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="76681-104">*Questa guida al laboratorio di testing può essere usata sia per gli ambienti Microsoft 365 aziendali che per Office 365 Enterprise test.*</span><span class="sxs-lookup"><span data-stu-id="76681-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="76681-105">Molte organizzazioni usano Azure AD Connect e la sincronizzazione hash delle password per sincronizzare il set di account della foresta Active Directory Domain Services (AD DS) locale con il set di account nel tenant di Azure AD dell'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76681-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="76681-106">In questo articolo viene descritto come aggiungere la sincronizzazione dell'hash delle password all'Microsoft 365 di test, che determina questa configurazione:</span><span class="sxs-lookup"><span data-stu-id="76681-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="76681-108">La configurazione di questo ambiente di testing prevede tre fasi:</span><span class="sxs-lookup"><span data-stu-id="76681-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="76681-109">Fase 1: creare l'ambiente di testing per l'organizzazione simulata di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76681-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="76681-110">Fase 2: creare e registrare il dominio per il test lab</span><span class="sxs-lookup"><span data-stu-id="76681-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="76681-111">Fase 3: installare Azure AD Connect su APP1</span><span class="sxs-lookup"><span data-stu-id="76681-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="76681-112">Per una mappa visiva a tutti gli articoli dello stack Microsoft 365 per enterprise Test Lab Guide, passare a [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="76681-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="76681-113">Fase 1: creare l'ambiente di testing per l'organizzazione simulata di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76681-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="76681-114">Seguire le istruzioni in [Configurazione di base aziendale simulata per Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="76681-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="76681-115">La configurazione risultante è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="76681-115">Your resulting configuration looks like this:</span></span>
  
![La configurazione di base per l'organizzazione simulata](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="76681-117">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="76681-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="76681-118">Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="76681-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="76681-119">Intranet dell'organizzazione semplificata connessa a Internet, costituita da macchine virtuali DC1, APP1 e CLIENT1 in una rete virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="76681-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="76681-120">DC1 è un controller di dominio per testlab.<*il nome di* dominio pubblico> dominio di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="76681-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="76681-121">Fase 2: creare e registrare il dominio per il test lab</span><span class="sxs-lookup"><span data-stu-id="76681-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="76681-122">In questa fase, aggiungere un dominio DNS pubblico e quindi aggiungerlo alla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="76681-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="76681-123">Innanzitutto, collaborare con il provider di registrazione DNS pubblico per creare un nuovo nome di dominio DNS pubblico basato sul nome di dominio corrente e quindi aggiungerlo alla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="76681-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="76681-124">È consigliabile utilizzare il nome **testlab.<*dominio pubblico.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="76681-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="76681-125">Ad esempio, se il nome di dominio pubblico **<span>è contoso</span>.com,** aggiungere il nome di dominio pubblico: **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="76681-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="76681-126">Successivamente, aggiungere **il file testlab.< >** dominio di dominio pubblico alla sottoscrizione Microsoft 365 di valutazione o a pagamento tramite il processo di registrazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="76681-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="76681-127">Ciò consiste nell'aggiungere ulteriori record DNS al **testlab.<*dominio pubblico.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="76681-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="76681-128">Per ulteriori informazioni, vedere [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="76681-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="76681-129">La configurazione risultante è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="76681-129">Your resulting configuration looks like this:</span></span>
  
![La registrazione del nome di dominio testlab](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="76681-131">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="76681-131">This configuration consists of:</span></span>

- <span data-ttu-id="76681-132">Una Microsoft 365 E5 di valutazione o a pagamento con il dominio DNS testlab.<il nome *di* dominio pubblico> registrato.</span><span class="sxs-lookup"><span data-stu-id="76681-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="76681-133">Intranet dell'organizzazione semplificata connessa a Internet, costituita da macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="76681-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="76681-134">Si noti come testlab.<*il nome di* dominio pubblico> ora è:</span><span class="sxs-lookup"><span data-stu-id="76681-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="76681-135">Ospitato da record DNS pubblici.</span><span class="sxs-lookup"><span data-stu-id="76681-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="76681-136">Registrato negli abbonamenti a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76681-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="76681-137">Il dominio di AD DS nella rete Intranet simulata.</span><span class="sxs-lookup"><span data-stu-id="76681-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="76681-138">Fase 3: installare Azure AD Connect su APP1</span><span class="sxs-lookup"><span data-stu-id="76681-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="76681-139">In questa fase, installare e configurare lo strumento azure AD Connessione in APP1 e quindi verificare che funzioni.</span><span class="sxs-lookup"><span data-stu-id="76681-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="76681-140">Innanzitutto, installare e configurare Azure AD Connessione in APP1.</span><span class="sxs-lookup"><span data-stu-id="76681-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="76681-141">Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="76681-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="76681-142">Dal desktop di APP1, aprire un prompt dei comandi di Windows PowerShell a livello di amministratore ed eseguire questi comandi per disabilitare Sicurezza avanzata di Internet Explorer:</span><span class="sxs-lookup"><span data-stu-id="76681-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="76681-143">Dalla barra delle applicazioni seleziona **Internet Explorer** e vai a [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="76681-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="76681-144">Nella pagina Microsoft Azure Active Directory Connessione selezionare **Scarica** e **quindi** Esegui.</span><span class="sxs-lookup"><span data-stu-id="76681-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="76681-145">Nella pagina **Benvenuto in Azure AD Connessione,** selezionare Accetto e quindi continua.  </span><span class="sxs-lookup"><span data-stu-id="76681-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="76681-146">Nella pagina **Express Impostazioni** selezionare **Usa impostazioni rapide.**</span><span class="sxs-lookup"><span data-stu-id="76681-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="76681-147">Nella pagina **Connessione ad Azure AD,** immettere il nome dell'account amministratore globale in Nome **utente,** immettere la password in **Password** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="76681-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="76681-148">Nella pagina **Connessione ad AD DS** immettere **TESTLAB \\ User1** in **Nome utente,** immettere la password in **Password** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="76681-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="76681-149">Nella pagina **Pronto per la configurazione** selezionare **Installa**.</span><span class="sxs-lookup"><span data-stu-id="76681-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="76681-150">Nella pagina **Configurazione completata** selezionare **Esci.**</span><span class="sxs-lookup"><span data-stu-id="76681-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="76681-151">In Internet Explorer, passare all'interfaccia di amministrazione di Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="76681-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="76681-152">Nel riquadro di spostamento sinistro selezionare **Utenti > utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="76681-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="76681-153">Si noti l'account denominato **User1**.</span><span class="sxs-lookup"><span data-stu-id="76681-153">Note the account named **User1**.</span></span> <span data-ttu-id="76681-154">Questo account deriva dal dominio TESTLAB AD DS ed è la prova che la sincronizzazione della directory ha funzionato.</span><span class="sxs-lookup"><span data-stu-id="76681-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="76681-155">Seleziona **l'account User1** e quindi **seleziona Licenze e app.**</span><span class="sxs-lookup"><span data-stu-id="76681-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="76681-156">In **Licenze prodotto** seleziona la tua posizione (se necessario), disabilita la licenza Office 365 **E5** e quindi abilita la licenza **Microsoft 365 E5** licenza.</span><span class="sxs-lookup"><span data-stu-id="76681-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="76681-157">Selezionare **Salva** nella parte inferiore della pagina e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="76681-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="76681-158">Testare quindi la possibilità di accedere all'abbonamento con il nome **user1@testlab.< >** nome di dominio dell'account User1:</span><span class="sxs-lookup"><span data-stu-id="76681-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="76681-159">Da APP1, disconnettersi e quindi accedere nuovamente specificando un account diverso.</span><span class="sxs-lookup"><span data-stu-id="76681-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="76681-160">Quando vengono richiesto un nome utente e una password, **specificare user1@testlab.<*il\* >*\* nome di dominio e la password User1.</span><span class="sxs-lookup"><span data-stu-id="76681-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="76681-161">Dovrebbe essere possibile accedere come User1.</span><span class="sxs-lookup"><span data-stu-id="76681-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="76681-162">Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB AD DS, non è un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="76681-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="76681-163">Di conseguenza, l'icona **Amministratore** non sarà visibile.</span><span class="sxs-lookup"><span data-stu-id="76681-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="76681-164">La configurazione risultante è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="76681-164">Your resulting configuration looks like this:</span></span>

![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="76681-166">Questa configurazione è costituita da:</span><span class="sxs-lookup"><span data-stu-id="76681-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="76681-167">Microsoft 365 E5 o Office 365 di valutazione E5 o a pagamento con il dominio DNS TESTLAB.<il nome *di* dominio> registrato.</span><span class="sxs-lookup"><span data-stu-id="76681-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="76681-168">Intranet dell'organizzazione semplificata connessa a Internet, costituita da macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="76681-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="76681-169">Azure AD Connessione viene eseguito su APP1 per sincronizzare periodicamente il dominio TESTLAB AD DS con il tenant di Azure AD della sottoscrizione Microsoft 365 sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="76681-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="76681-170">L'account User1 nel dominio TESTLAB AD DS è stato sincronizzato con il tenant Azure AD.</span><span class="sxs-lookup"><span data-stu-id="76681-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="76681-171">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="76681-171">Next step</span></span>

<span data-ttu-id="76681-172">Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="76681-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="76681-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76681-173">See also</span></span>

[<span data-ttu-id="76681-174">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="76681-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="76681-175">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="76681-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="76681-176">Documentazione di Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="76681-176">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)